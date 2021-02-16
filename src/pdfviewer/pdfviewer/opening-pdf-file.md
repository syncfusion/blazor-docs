------
# Open PDF files in PDF Viewer for Blazor from various storage location

You might need to open and view the PDF files from various location. In this section, you can find information about how to open PDF files from URL, Cloud, database, local file system, and as base64 string.

## Opening a PDF from URL

If you have your PDF files in the web, you can open it in the viewer using URL. The following code example explains how to open PDF file from URL.

```csharp
@using Syncfusion.Blazor.PdfViewerServer

<SfPdfViewerServer DocumentPath="@DocumentPath" Width="1060px" Height="500px" />

@code {
    public string DocumentPath { get; set; }
    protected override void OnInitialized()
    {
        string Url = "https://s3.amazonaws.com/files2.syncfusion.com/dtsupport/directtrac/general/pd/HTTP_Succinctly-1719682472.pdf";
        System.Net.WebClient webClient = new System.Net.WebClient();
        byte[] byteArray = webClient.DownloadData(Url);
        DocumentPath = "data:application/pdf;base64," + Convert.ToBase64String(byteArray);
    }
}
```

## Opening a PDF from Cloud

You can open the PDF file from Cloud storage.

The following code example shows how to open and load the PDF file stored in Azure Blob Storage.

```csharp
@using Microsoft.Azure.Storage;
@using Microsoft.Azure.Storage.Blob;
@using System.IO;
@using Syncfusion.Blazor.PdfViewerServer

<SfPdfViewerServer DocumentPath="@DocumentPath" Width="1060px" Height="500px" />

@code {
    public string DocumentPath { get; set; }
    protected override void OnInitialized()
    {
        //Connection String of Storage Account
        string connectionString = "Here Place Your Connection string";
        //Container Name
        string containerName = "pdf";
        //File Name to be loaded into Syncfusion PDF Viewer
        string fileName = "PDF_Succinctly.pdf";
        CloudStorageAccount cloudStorageAccount = CloudStorageAccount.Parse(connectionString);
        CloudBlobClient cloudBlobClient = cloudStorageAccount.CreateCloudBlobClient();
        CloudBlobContainer cloudBlobContainer = cloudBlobClient.GetContainerReference(containerName);
        CloudBlockBlob cloudBlockBlob = cloudBlobContainer.GetBlockBlobReference(fileName);
        MemoryStream memoryStream = new MemoryStream();
        cloudBlockBlob.DownloadToStream(memoryStream);
        DocumentPath = "data:application/pdf;base64," + Convert.ToBase64String(memoryStream.ToArray());
    }
}
```

>Note: The **Microsoft.Azure.Storage.Blob** NuGet package must be installed in your application to use the previous code example.

You can open the PDF file from Azure File Storage using the following code example.

```csharp
@using Microsoft.Azure.Storage;
@using Microsoft.Azure.Storage.File;
@using System.IO;
@using Syncfusion.Blazor.PdfViewerServer

<SfPdfViewerServer DocumentPath="@DocumentPath" Width="1060px" Height="500px" />

@code {
    public string DocumentPath { get; set; }
    protected override void OnInitialized()
    {
        //Connection String of Storage Account
        string connectionString = "Here Place Your Connection string";
        string shareReference = "document";
        string directoryReference = "pdf";
        //File Name to be loaded into Syncfusion PDF Viewer
        string fileReference = "Python_Succinctly.pdf";
        CloudStorageAccount cloudStorageAccount = CloudStorageAccount.Parse(connectionString);
        CloudFileClient fileClient = cloudStorageAccount.CreateCloudFileClient();
        //Get File Share
        CloudFileShare cloudFileShare = fileClient.GetShareReference(shareReference);
        //Get the related directory
        CloudFileDirectory root = cloudFileShare.GetRootDirectoryReference();
        CloudFileDirectory dir = root.GetDirectoryReference(directoryReference);
        //Get the file reference
        CloudFile file = dir.GetFileReference(fileReference);
        MemoryStream memoryStream = new MemoryStream();
        //Download file to local disk
        file.DownloadToStream(memoryStream);
        DocumentPath = "data:application/pdf;base64," + Convert.ToBase64String(memoryStream.ToArray());
    }
}
```

>Note: The **Microsoft.Azure.Storage.File** NuGet package must be installed in your application to use the previous code example.

## Opening a PDF from database

The following code example shows how to open the PDF file in viewer from SQL Server database.

```csharp
@using Syncfusion.Blazor.PdfViewerServer

<SfPdfViewerServer DocumentPath="@DocumentPath" Width="1060px" Height="500px" />

@code {
    public string DocumentPath { get; set; }
    protected override void OnInitialized()
    {
        string documentID = "PDF Succinctly";
        string connectionString = "Data Source=(LocalDB)\\MSSQLLocalDB;AttachDbFilename=C:\\Database.mdf;";
        System.Data.SqlClient.SqlConnection connection = new System.Data.SqlClient.SqlConnection(connectionString);
        //Searches for the PDF document from the database
        string query = "select Data from Table where DocumentName = '" + documentID + "'";
        System.Data.SqlClient.SqlCommand command = new System.Data.SqlClient.SqlCommand(query, connection);
        connection.Open();
        System.Data.SqlClient.SqlDataReader read = command.ExecuteReader();
        read.Read();
        //Reads the PDF document data as byte array from the database
        byte[] byteArray = (byte[])read["Data"];
        DocumentPath = "data:application/pdf;base64," + Convert.ToBase64String(byteArray);
    }
}
```

>Note: The **System.Data.SqlClient** package must be installed in your application to use the previous code example. You need to modify the connectionString variable in the previous code example as per the connection string of your database.

## Opening a PDF from file system

There is an UI option in built-in toolbar to open the PDF file from local file system. If you want to achieve the same functionality when design your own toolbar, you can use the following code example to load and open the PDF file. In this sample, the Syncfusion’s Uploader control is used for Blazor.

```csharp
@using Syncfusion.Blazor.Inputs
@using Syncfusion.Blazor.PdfViewerServer

<SfUploader ID="UploadFiles" AllowedExtensions=".pdf,.PDF">
    <UploaderEvents FileSelected="onsuccess"></UploaderEvents>
</SfUploader>
<SfPdfViewerServer @ref="@Viewer" Width="1060px" Height="500px" />

@code {
    SfPdfViewerServer Viewer;
    public void onsuccess(SelectedEventArgs action)
    {
        string filePath = action.FilesData[0].RawFile.ToString();
        Viewer.Load(filePath, null);
    }
}
```

## Opening a PDF from base64 data

The following code snippet explains how the PDF file can be loaded in PDF Viewer as base64 string.

```csharp
@using Syncfusion.Blazor.PdfViewerServer

<SfPdfViewerServer ID="pdfviewer" DocumentPath="@DocumentPath" Width="1060px" Height="500px"/>

@code {
    static byte[] byteArray = System.IO.File.ReadAllBytes("wwwroot/data/PDF_Succinctly.pdf");
    static string base64String = Convert.ToBase64String(byteArray);
    public string DocumentPath { get; set; } = "data:application/pdf;base64," + base64String;
}
```