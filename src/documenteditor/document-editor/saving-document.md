---
title: "Save document through Blazor Word processor"
component: "Word processor"
description: "Learn how to save the composed or edited document through Blazor Word processor to server, database, and local file system."
---

# Save documents to server, database and local file system

After composing or editing the document, you will need to save the document to the server, database, or local file system.

## Save document to server

You might need to save the document back to the server. The following code example shows how to save the composed document to server.

```csharp
@using Syncfusion.Blazor.DocumentEditor
@using  System.IO

<button @onclick="OnSave">Save</button>

<SfDocumentEditorContainer @ref="container" EnableToolbar=true></SfDocumentEditorContainer>

@code {

    SfDocumentEditorContainer container;

    public async void OnSave()
    {
        DocumentEditorModule editor = container.GetDocumentEditor();
        object base64Data = await editor.SaveAsBlob(FormatType.Docx);
        Dictionary<string, string> documentContent = Newtonsoft.Json.JsonConvert.DeserializeObject<Dictionary<string, string>>(base64Data.ToString());
        byte[] data = Convert.FromBase64String(documentContent["data"]);
        //Word document file stream
        Stream stream = new MemoryStream(data);
        using (var fileStream = new FileStream(@"wwwroot\data\GettingStarted.docx", FileMode.Create, FileAccess.Write))
        {
            //Saving the new file in root path of application
            stream.CopyTo(fileStream);
            fileStream.Close();
        }
        stream.Close();
    }
}

```

## Save document to database

If you have plenty of documents stored in database and you want to save the composed or updated document back to the database, use the following code example.

```csharp
@using Syncfusion.Blazor.DocumentEditor
@using System.Data.SqlClient

<button @onclick="OnSave">Save</button>

<SfDocumentEditorContainer @ref="container" EnableToolbar="true"></SfDocumentEditorContainer>

@code {

    SfDocumentEditorContainer container;

    public async void OnSave()
    {
        string documentID = "Getting_Started.docx";
        DocumentEditorModule editor = container.GetDocumentEditor();
        object base64Data = await editor.SaveAsBlob(FormatType.Docx);
        Dictionary<string, string>
        documentContent = Newtonsoft.Json.JsonConvert.DeserializeObject<Dictionary<string, string>>(base64Data.ToString());
        byte[] data = Convert.FromBase64String(documentContent["data"]);
        string connectionString = "Data Source=(LocalDB)\\MSSQLLocalDB;AttachDbFilename=C:\\database.mdf;";
        string queryStmt = "Update DocumentsTable SET Data = @Content where DocumentName = '" + documentID + "'";
        using (SqlConnection con = new SqlConnection(connectionString))
        using (SqlCommand cmd = new SqlCommand(queryStmt, con))
        {
            SqlParameter param = cmd.Parameters.Add("@Content", System.Data.SqlDbType.VarBinary);
            param.Value = data;
            con.Open();
            cmd.ExecuteNonQuery();
            con.Close();
        }
    }
}
```

## Download document as a copy

You can also save or download the document in local file system.

```csharp
@using Syncfusion.Blazor.DocumentEditor

<button @onclick="OnDownload">Download</button>

<SfDocumentEditorContainer @ref="container" EnableToolbar="true"></SfDocumentEditorContainer>

@code {
    SfDocumentEditorContainer container;
    public void OnDownload()
    {
        DocumentEditorModule editor = container.GetDocumentEditor();
        editor.Save("sample", FormatType.Docx);
    }
}
```