---
title: " Chart Print and Export | ASP.NET Core Blazor "

component: "Chart"

description: "The rendered chart can be printed or exported directly from the browser by calling the public method print and export."
---

# Print

## Print

The rendered chart can be printed directly from the browser by calling the public method [`Print`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.EjsChart~Print.html).
You can pass array of ID of elements or element to this method. By default it take element of the chart.

{% aspTab template="chart/getting-started/print", sourceFiles="print.razor" %}

{% endaspTab %}

## Export

The rendered chart can be exported to `JPEG`, `PNG`, `SVG`, or `PDF` format using the [`Export`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.EjsChart~Export.html) method in chart. The input parameters for this method are `Export Type` for format and `FileName` for result.

The optional parameters for this method are,
* `Orientation` - either portrait or landscape,
* `Controls` - pass collections of controls for multiple export,
* `Width` - width of chart export, and
* `Height` - height of chart export.

{% aspTab template="chart/getting-started/export", sourceFiles="export.razor" %}

{% endaspTab %}

## See Also

* [Data label](./data-labels)
* [Tooltip](./tool-tip)
* [Legend](./legend)