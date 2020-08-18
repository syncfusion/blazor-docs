# Print and Export in Blazor Circular Gauge

## Print

To use the print functionality, we should set the [`AllowPrint`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.CircularGauge.CircularGaugeModel~AllowPrint.html) property to **true**. The rendered circular gauge can be printed directly from the browser by calling the method [`print`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.CircularGauge.SfCircularGauge~Print.html). You can get the Circular Gauge component object using `@ref="Gauge"`

```csharp
@using Syncfusion.Blazor.CircularGauge

<button @onclick="PrintGauge">Print</button>
<SfCircularGauge @ref="Gauge" AllowPrint="true">
</SfCircularGauge>

@code {
    SfCircularGauge Gauge;
    void PrintGauge()
    {
        this.Gauge.Print();
    }
}
```

![Circular Gauge with print Sample](./images/print.png)

## Export

### Image Export

To use the image export functionality, we should set the [`AllowImageExport`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.CircularGauge.CircularGaugeModel~AllowImageExport.html) property to **true**. The rendered circular gauge can be exported as an image using the [`export`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.CircularGauge.SfCircularGauge~Export.html) method. The method requires two parameters: image type and file name. The circular gauge can be exported as an image in the following formats.

* JPEG
* PNG
* SVG

```csharp
@using Syncfusion.Blazor.CircularGauge

<button @onclick="ExportGauge">Export</button>
<SfCircularGauge @ref="Gauge" AllowImageExport="true">
</SfCircularGauge>

@code {
    SfCircularGauge Gauge;
    void ExportGauge()
    {
        this.Gauge.Export(ExportType.PNG, "CircularGauge");
    }
}
```

![Circular Gauge with export Sample](./images/export.png)

### PDF Export

To use the PDF export functionality, we should set the [`AllowPdfExport`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.CircularGauge.CircularGaugeModel~AllowPdfExport.html) property to **true**. The rendered circular gauge can be exported as PDF using the [`export`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.CircularGauge.SfCircularGauge~Export.html) method. The [`export`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.CircularGauge.SfCircularGauge~Export.html) method requires three parameters: file type, file name and orientation of the PDF document. The orientation setting is optional and "0" indicates portrait and "1" indicates landscape.

```csharp
@using Syncfusion.Blazor.CircularGauge

<button @onclick="ExportGauge">Export</button>
<SfCircularGauge @ref="Gauge" AllowPdfExport="true">
</SfCircularGauge>

@code {
    SfCircularGauge Gauge;
    void ExportGauge()
    {
        this.Gauge.Export(ExportType.PDF, "CircularGauge", 0);
    }
}
```

![Circular Gauge with export Sample](./images/export.png)