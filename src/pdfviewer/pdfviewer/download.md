---
component: "PDF Viewer"
---

# Download

The PDF Viewer supports downloading the loaded PDF file from the toolbar by default. You can enable or disable the download option by setting the `EnableDownload` API.

```csharp
@using Syncfusion.Blazor.PdfViewerServer

<SfPdfViewerServer Width="1060px" Height="500px" DocumentPath="@DocumentPath" EnableDownload="true"/>

@code{
    public string DocumentPath { get; set; } = "wwwroot/data/PDF_Succinctly.pdf";
}
```

![Download](../pdfviewer/images/download.png)

And, you can programmatically invoke download action as follows.

```csharp
@using Syncfusion.Blazor.PdfViewerServer
@using Syncfusion.Blazor.Buttons

<SfButton OnClick="OnClick">Download</SfButton>
<SfPdfViewerServer Width="1060px" Height="500px" DocumentPath="@DocumentPath" @ref="@Viewer"/>

@code{
    SfPdfViewerServer Viewer;
    public string DocumentPath { get; set; } = "wwwroot/data/PDF_Succinctly.pdf";
    public void OnClick(MouseEventArgs args)
    {
        Viewer.Download();
    }
}
```