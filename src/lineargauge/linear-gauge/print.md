# Print and Export in Blazor Linear Gauge Component

## Print

The rendered linear gauge can be printed directly from the browser by calling the method [`Print`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.LinearGauge.SfLinearGauge~Print.html). You can get the Linear Gauge component object using `@ref="Gauge"`

```csharp
<button @onclick="PrintGauge">Print</button>
<SfLinearGauge @ref="Gauge">
</SfLinearGauge>

@code {
    SfLinearGauge Gauge;
    void PrintGauge()
    {
        gauge.Print();
    }
}
```

![Linear Gauge Print Sample](images/print.png)

## Export

The rendered linear gauge can be exported to the following formats using the [`Export`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.LinearGauge.SfLinearGauge~Export.html) method. The input parameters for this method are export type for format and file name of result.

* JPEG
* PNG
* SVG
* PDF

```csharp
<button @onclick="ExportGauge">Export</button>
<SfLinearGauge @ref="Gauge">
</SfLinearGauge>

@code {
    SfLinearGauge Gauge;
    void ExportGauge()
    {
        gauge.Export(ExportType.PNG, "LinearGauge");
    }
}
```

![Linear Gauge Export Sample](images/export.png)