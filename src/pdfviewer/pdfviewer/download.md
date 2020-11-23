---
title: "Download"
component: "PDF Viewer"
description: "Learn about download option in PDF Viewer to download the loaded document."
---
# Download

The PDF Viewer supports downloading the loaded PDF file. You can enable/disable the download using the following code snippet.

![Alt text](./images/download.png)

You can invoke download action using following code snippet.,

```html
    <button id="downloadBtn">Download</button>
    <div style="width:100%;height:600px">
        <EjsPdfViewer id="pdfviewer" documentPath="PDF_Succinctly.pdf" documentLoad="@documentLoad"
         serviceUrl="https://ej2services.syncfusion.com/production/web-services/api/pdfviewer" style="height: 640px;width: 100%" />
    </div>
    @functions{
    protected async void documentLoad(object args)
    {
    await JsRuntime.InvokeAsync<bool>
    ("documentLoaded");
    }
    }
```

```javascript
    function documentLoaded() {
        var pdfViewer = document.getElementById('pdfviewer').ej2_instances[0];
        document.getElementById('downloadBtn').addEventListener('click', function() {
            pdfViewer.download();
        });
    }
```

## See also

* [Toolbar items](./toolbar)
* [Feature Modules](./feature-module)