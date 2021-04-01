# Print

## Print

Rendered chart can be printed directly from the browser by calling [`Print`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SfChart.html#Syncfusion_Blazor_Charts_SfChart_Print) method.
You can pass array of elements ID or element to this method. By default it take element of the chart.

{% aspTab template="chart/getting-started/print", sourceFiles="print.razor" %}

{% endaspTab %}

## Export

The rendered chart can be exported to `JPEG`, `PNG`, `SVG`, or `PDF` format using the [`Export`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SfChart.html#Syncfusion_Blazor_Charts_SfChart_Export_Syncfusion_Blazor_Charts_ExportType_System_String_System_Nullable_Syncfusion_PdfExport_PdfPageOrientation__System_Boolean_) method in chart. The input parameters for this method are `Export Type` for format and `FileName` for result.

The optional parameters for this method are,
* `Orientation` - Portrait or landscape,
* `Controls` - Collections of controls for multiple export,
* `Width` - Width of chart export, and
* `Height` - Height of chart export.

{% aspTab template="chart/getting-started/export", sourceFiles="export.razor" %}

{% endaspTab %}

> Note: You can refer to our [`Blazor Charts`](https://www.syncfusion.com/blazor-components/blazor-charts) feature tour page for its groundbreaking feature representations. You can also explore our [`Blazor Chart example`](https://blazor.syncfusion.com/demos/chart/line?theme=bootstrap4) to knows various chart types and how to represent time-dependent data, showing trends in data at equal intervals.

## See Also

* [Data label](./data-labels)
* [Tooltip](./tool-tip)
* [Legend](./legend)