---
component: "BarcodeGenerator"
---

# Export

## Export

Barcode provides support to export its content as an image in the specified image type and downloads it in the browser.

```csharp
@using Syncfusion.Blazor.BarcodeGenerator

<input type="button" value="Export" @onclick="@OnExport" />
<SfQRCodeGenerator Width="200px" Height="150px" Value="Syncfusion" @ref="@QRcode" >
    <QRCodeGeneratorDisplayText text="Text"></QRCodeGeneratorDisplayText>
</SfQRCodeGenerator>
@code{
    SfQRCodeGenerator QRcode;
    private void OnExport() {
        QRcode.Export("fileName", BarcodeExportType.JPG);
    }
}

 ```

### ExportAsBaseImage

Barcode provides support to export as an image in the specified image type and returns it as base64 string.

```csharp
@using Syncfusion.Blazor.BarcodeGenerator

<input type="button" value="Export" @onclick="@OnExport" />
<SfQRCodeGenerator Width="200px" Height="150px" Value="Syncfusion" @ref="@QRcode" >
    <QRCodeGeneratorDisplayText text="Text"></QRCodeGeneratorDisplayText>
</SfQRCodeGenerator>
@code{
    SfQRCodeGenerator QRcode;
    private async void OnExport() {
        await QRcode.ExportAsBase64Image(BarcodeExportType.JPG);
    }
}

```

>**Note:**
>Format is to specify the type/format of the exported file. You can export Barcode to the following formats:
>* JPG.
>* PNG.
