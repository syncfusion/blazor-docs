---
component: "PDF Viewer"
---

# Customize the toolbar

The PDF Viewer provides API for user interactions options provided in it's built-in toolbar. Using this we can create our own User Interface for toolbar actions in application level by hiding the default toolbar. The following steps are used to create the custom toolbar for PDF Viewer,

**Step 1:** Follow the steps provided in the [link](https://ej2.syncfusion.com/aspnet-core-razor-components/documentation/pdfviewer/getting-started/) to create simple PDF Viewer sample.

**Step 2:** Now, add an HTML div element in template to act as the custom toolbar PDF Viewer using the following code.

```html
@{
    var template = "<div class=''><span class='e-pv-total-page-number' id='totalPage'>of 0</span></div>";
    var inputtemplate = "<div class=''><input type='text' class='e-input-group e-pv-current-page-number' id='currentPage' /></div>";
}
<div class="control-section">
    <Ejstoolbar id="topToolbar" height="56px" created="@created">
        <ToolBarItems>
            <ToolBarItem PrefixIcon="e-pv-open-document-icon" TooltipText="Open" id="openPage" Align=@Syncfusion.EJ2.RazorComponents.Navigations.ItemAlign.Left></ToolBarItem>
            <ToolBarItem PrefixIcon="e-pv-previous-page-navigation-icon" TooltipText="Previous Page" id="previousPage" Align=@Syncfusion.EJ2.RazorComponents.Navigations.ItemAlign.Center></ToolBarItem>
            <ToolBarItem PrefixIcon="e-pv-next-page-navigation-icon" TooltipText="Next Page" id="nextPage" Align=@Syncfusion.EJ2.RazorComponents.Navigations.ItemAlign.Center></ToolBarItem>
            <ToolBarItem template="@inputtemplate" TooltipText="Page Number" Align=@Syncfusion.EJ2.RazorComponents.Navigations.ItemAlign.Center></ToolBarItem>
            <ToolBarItem template="@template" TooltipText="Page Number" id="PageNumber" Align=@Syncfusion.EJ2.RazorComponents.Navigations.ItemAlign.Center></ToolBarItem>
            <ToolBarItem PrefixIcon="e-pv-print-document-icon" TooltipText="Print" id="print" Align=@Syncfusion.EJ2.RazorComponents.Navigations.ItemAlign.Right></ToolBarItem>
            <ToolBarItem PrefixIcon="e-pv-download-document-icon" TooltipText="Download" id="Download" Align=@Syncfusion.EJ2.RazorComponents.Navigations.ItemAlign.Right></ToolBarItem>
        </ToolBarItems>
    </Ejstoolbar>
    <EjsPdfViewer id="pdfviewer" enableToolbar="false" documentPath="Hive_Succinctly.pdf" serviceUrl="https://ej2services.syncfusion.com/production/web-services/api/pdfviewer" documentLoad="@documentLoad" pageChange="@pageChanged"></EjsPdfViewer>
    <input type="file" id="fileUpload" accept=".pdf" style="display:block;visibility:hidden;width:0;height:0;">
    <div id="magnificationToolbarItems">
        <Ejstoolbar id="magnificationToolbar">
            <ToolBarItems>
                <ToolBarItem PrefixIcon="e-pv-fit-page" TooltipText="Fit to page" id="fitPage"></ToolBarItem>
                <ToolBarItem PrefixIcon="e-pv-zoom-in-icon" TooltipText="Zoom in" id="zoomIn"></ToolBarItem>
                <ToolBarItem PrefixIcon="e-pv-zoom-out-icon" TooltipText="Zoom out" id="zoomOut"></ToolBarItem>
            </ToolBarItems>
        </Ejstoolbar>
    </div>
</div>
```

**Step 3:** Hide the default toolbar of PDF Viewer using below code snippet,

```html
    <EjsPdfViewer id="pdfviewer" enableToolbar="false" documentPath="Hive_Succinctly.pdf" serviceUrl="https://ej2services.syncfusion.com/production/web-services/api/pdfviewer"></EjsPdfViewer>
```

**Step 4:** Add the following style to achieve the custom toolbar styling,

```html
<style>
    #pdfviewer {
        height: 640px;
        width: 100%;
    }

    .content-wrapper {
        width: 95%;
        margin: auto;
        min-width: 85px;
    }

    #magnificationToolbar {
        background: transparent;
        height: auto;
        width: 200px;
        position: absolute;
        z-index: 1001;
        left: calc(100% - 120px);
        top: calc(100% - 110px);
        transform: rotate(90deg);
        border-width: 0px;
    }

    .e-pv-zoom-out-icon {
        transform: rotate(-90deg);
    }

    div#magnificationToolbar.e-toolbar .e-toolbar-items {
        background: transparent;
    }

    #magnificationToolbar.e-toolbar .e-tbar-btn {
        border-radius: 50%;
        min-height: 30px;
        min-width: 30px;
    }

    #topToolbar {
        top: 0px;
        z-index: 1001;
    }

    .material .e-pv-current-page-number {
        border-width: 1px;
    }

    .e-pv-current-page-number {
        width: 46px;
        height: 28px;
        text-align: center;
    }

    .e-icons {
        font-family: "e-icons";
        font-style: normal;
        font-variant: normal;
        font-weight: normal;
        line-height: 1;
        text-transform: none;
    }

    .e-pv-icon::before {
        font-family: 'e-icons';
    }

    .e-pv-icon-search::before {
        font-family: 'e-icons';
        font-size: 12px;
    }

    .e-pv-download-document-icon::before {
        content: '\e914';
    }

    .e-pv-print-document-icon::before {
        content: '\e917';
    }

    .e-pv-previous-page-navigation-icon::before {
        content: '\e910';
    }

    .e-pv-next-page-navigation-icon::before {
        content: '\e911';
    }

    .e-pv-zoom-out-icon::before {
        content: '\e912';
    }

    .e-pv-zoom-in-icon::before {
        content: '\e91d';
    }

    .e-pv-fit-page::before {
        content: '\e91b';
    }

    .e-pv-open-document-icon::before {
        content: '\e91c';
    }

    @@font-face {
        font-family: "e-icons";
        font-style: normal;
        font-weight: normal;
        src: url(data:application/x-font-ttf;charset=utf-8;base64,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ZWd1bGFyY3VzdG9tLXRvb2xiYXJbMTkwOF1jdXN0b20tdG9vbGJhclsxOTA4XVZlcnNpb24gMS4wY3VzdG9tLXRvb2xiYXJbMTkwOF1Gb250IGdlbmVyYXRlZCB1c2luZyBTeW5jZnVzaW9uIE1ldHJvIFN0dWRpb3d3dy5zeW5jZnVzaW9uLmNvbQAgAGMAdQBzAHQAbwBtAC0AdABvAG8AbABiAGEAcgBbADEAOQAwADgAXQBSAGUAZwB1AGwAYQByAGMAdQBzAHQAbwBtAC0AdABvAG8AbABiAGEAcgBbADEAOQAwADgAXQBjAHUAcwB0AG8AbQAtAHQAbwBvAGwAYgBhAHIAWwAxADkAMAA4AF0AVgBlAHIAcwBpAG8AbgAgADEALgAwAGMAdQBzAHQAbwBtAC0AdABvAG8AbABiAGEAcgBbADEAOQAwADgAXQBGAG8AbgB0ACAAZwBlAG4AZQByAGEAdABlAGQAIAB1AHMAaQBuAGcAIABTAHkAbgBjAGYAdQBzAGkAbwBuACAATQBlAHQAcgBvACAAUwB0AHUAZABpAG8AdwB3AHcALgBzAHkAbgBjAGYAdQBzAGkAbwBuAC4AYwBvAG0AAAAAAgAAAAAAAAAKAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAOAQIBAwEEAQUBBgEHAQgBCQEKAQsBDAENAQ4BDwAIVG9wLWljb24LZG93bi1hcnJvdzIKUFZfWm9vbW91dAlQVl9ab29taW4LUFZfRG93bmxvYWQLUFZfQm9va21hcmsJUFZfU2VhcmNoCFBWX1ByaW50C1BWX1ByZXZpb3VzB1BWX05leHQIUFZfQ2xvc2UMUFZfRml0VG9QYWdlB1BWX09wZW4AAA==) format('truetype');
    }
</style>
```

>The icons are embedded in the font file used in above code snippet.

**Step 5:** Add the following scripts for performing user interaction in PDF Viewer in code behind

```html
@functions{
    protected async void documentLoad(object args)
    {
    await JsRuntime.InvokeAsync<bool>
    ("documentLoaded");
    }
    protected async void created(object args)
    {
    await JsRuntime.InvokeAsync<bool>
        ("initialLoad");
    }
    protected async void pageChanged(object args)
    {
    await JsRuntime.InvokeAsync<bool>
        ("pageChanged");
    }
}
```

```javascript
var currentPageBox
var matchCase = false;
var filename;

function openPage() {
    document.getElementById('fileUpload').click();
}
function readFile(evt) {
    var upoadedFiles = evt.target.files;
    var uploadedFile = upoadedFiles[0];
    filename = upoadedFiles[0].name;
    var reader = new FileReader();
    reader.readAsDataURL(uploadedFile);
    reader.onload = function () {
        var obj = document.getElementById('pdfviewer').ej2_instances[0];
        var uploadedFileUrl = this.result;
        obj.load(uploadedFileUrl, null);
        obj.fileName = filename;
        currentPageBox = document.getElementById('currentPage');
        currentPageBox.value = '1';
        var pageCount = document.getElementById('totalPage');
        pageCount.textContent = 'of ' + obj.pageCount;
    }
}
function pageChanged() {
    var pdfViewer = document.getElementById('pdfviewer').ej2_instances[0];
    document.getElementById('currentPage').value = pdfViewer.currentPageNumber;
    updatePageNavigation();
}
function onCurrentPageBoxKeypress(event) {
    var pdfViewer = document.getElementById('pdfviewer').ej2_instances[0];
    var currentPageBox = document.getElementById('currentPage');
    if ((event.which < 48 || event.which > 57) && event.which !== 8 && event.which !== 13) {
        event.preventDefault();
        return false;
    }
    else {
        var currentPageNumber = parseInt(currentPageBox.value);
        if (event.which === 13) {
            if (currentPageNumber > 0 && currentPageNumber <= viewer.pageCount) {
                pdfViewer.navigation.goToPage(currentPageNumber);
            }
            else {
                currentPageBox.value = viewer.currentPageNumber.toString();
            }
        }
        return true;
    }
}
function initialLoad() {
    currentPageBox = document.getElementById('currentPage');
    currentPageBox.value = '1';
    document.getElementById('fileUpload').addEventListener('change', readFile, false);
    document.getElementById('openPage').addEventListener('click', openPage);
    currentPageBox.addEventListener('keypress', () => {
        var pdfViewer = document.getElementById('pdfviewer').ej2_instances[0];
        var currentPage = document.getElementById('currentPage');
        if ((event.which < 48 || event.which > 57) && event.which !== 8 && event.which !== 13) {
            event.preventDefault();
            return false;
        } else {
            var currentPageNumber = parseInt((currentPage).value);
            if (event.which === 13) {
                if (currentPageNumber > 0 && currentPageNumber <= pdfViewer.pageCount) {
                    pdfViewer.navigation.goToPage(currentPageNumber);
                } else {
                    (currentPage).value = pdfViewer.currentPageNumber.toString();
                }
            }
            return true;
        }
    });
}
function currentPageClicked() {
    var currentPage = document.getElementById('currentPage');
    (currentPage).select();
}
function documentLoaded() {
    document.getElementById('nextPage').addEventListener('click', nextClicked);
    document.getElementById('previousPage').addEventListener('click', previousClicked);
    document.getElementById('nextPage').addEventListener('click', nextClicked);
    document.getElementById('print').addEventListener('click', printClicked);
    document.getElementById('Download').addEventListener('click', downloadClicked);
    document.getElementById('fitPage').addEventListener('click', pageFitClicked);
    document.getElementById('zoomIn').addEventListener('click', zoomInClicked);
    document.getElementById('zoomOut').addEventListener('click', zoomOutClicked);
    var pdfViewer = document.getElementById('pdfviewer').ej2_instances[0];
    var pageCount = document.getElementById('totalPage');
    pageCount.textContent = 'of ' + pdfViewer.pageCount;
    updatePageNavigation();
}
function updatePageNavigation() {
    var toolbarObj = document.getElementById('topToolbar').ej2_instances[0];
    var pdfViewer = document.getElementById('pdfviewer').ej2_instances[0];
    if (pdfViewer.currentPageNumber === 1) {
        toolbarObj.enableItems(document.getElementById('previousPage'), false);
        toolbarObj.enableItems(document.getElementById('nextPage'), true);
    } else if (pdfViewer.currentPageNumber === pdfViewer.pageCount) {
        toolbarObj.enableItems(document.getElementById('previousPage'), true);
        toolbarObj.enableItems(document.getElementById('nextPage'), false);
    } else {
        toolbarObj.enableItems(document.getElementById('previousPage'), true);
        toolbarObj.enableItems(document.getElementById('nextPage'), true);
    }
}
function previousClicked() {
    var pdfViewer = document.getElementById('pdfviewer').ej2_instances[0];
    pdfViewer.navigation.goToPreviousPage();
}
function nextClicked() {
    var pdfViewer = document.getElementById('pdfviewer').ej2_instances[0];
    pdfViewer.navigation.goToNextPage();
}
function printClicked() {
    var pdfViewer = document.getElementById('pdfviewer').ej2_instances[0];
    pdfViewer.print.print();
}
function downloadClicked() {
    var pdfViewer = document.getElementById('pdfviewer').ej2_instances[0];
    pdfViewer.download();
}
function pageFitClicked() {
    var pdfViewer = document.getElementById('pdfviewer').ej2_instances[0];
    pdfViewer.magnification.fitToPage();
}
function zoomInClicked() {
    var pdfViewer = document.getElementById('pdfviewer').ej2_instances[0];
    pdfViewer.magnification.zoomIn();
}
function zoomOutClicked() {
    var pdfViewer = document.getElementById('pdfviewer').ej2_instances[0];
    pdfViewer.magnification.zoomOut();
}
```

Sample :
[https://ej2.syncfusion.com/aspnet-core-razor-components/Viewer/CustomToolbar](https://ej2.syncfusion.com/aspnet-core-razor-components/Viewer/CustomToolbar)