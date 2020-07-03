# Print and Export in Blazor Circular Gauge

## Print

The rendered circular gauge can be printed directly from the browser by calling the method [`Print`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.CircularGauge.SfCircularGauge~Print.html). You can get the Circular Gauge component object using `@ref="Gauge"`

```csharp
@using Syncfusion.Blazor.CircularGauge

<button @onclick="PrintGauge">Print</button>
<SfCircularGauge @ref="Gauge">
</SfCircularGauge>

@code {
    SfCircularGauge Gauge;
    void PrintGauge()
    {
        gauge.Print();
    }
}
```

![Circular Gauge with print Sample](./images/print.png)

## Export

The rendered circular gauge can be exported to the following formats using the [`Export`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.CircularGauge.SfCircularGauge~Export.html) method. The input parameters for this method are export type for format and file name of result.

* JPEG
* PNG
* SVG
* PDF

```csharp
@using Syncfusion.Blazor.CircularGauge

<button @onclick="ExportGauge">Export</button>
<SfCircularGauge @ref="Gauge">
</SfCircularGauge>

@code {
    SfCircularGauge Gauge;
    void ExportGauge()
    {
        gauge.Export(ExportType.PNG, "CircularGauge");
    }
}
```

![Circular Gauge with export Sample](./images/export.png)