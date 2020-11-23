---
title: "Print"
component: "PDF Viewer"
description: "Learn about print option in PDF Viewer to print the document."
---
# Print

The PDF Viewer supports printing the loaded PDF file. You can enable/disable the print using the following code snippet.

```html
    <div style="width:100%;height:600px">
        <EjsPdfViewer id="pdfviewer" documentPath="PDF_Succinctly.pdf" enablePrint="true"
         serviceUrl="https://ej2services.syncfusion.com/production/web-services/api/pdfviewer" style="height: 640px;width: 100%" />
    </div>
    @functions{
    }
```

![Alt text](./images/print.png)

You can invoke print action using the following code snippet.,

```html
    <button id="printBtn">Print</button>
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
        document.getElementById('printBtn').addEventListener('click', function() {
            pdfViewer.print();
        });
    }
```

## See also

* [Toolbar items](./toolbar)
* [Feature Modules](./feature-module)