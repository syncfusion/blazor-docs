# Tooltip

Tooltip for the accumulation chart can be enabled by using the [`Enable`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.AccumulationChartTooltipSettings.html#Syncfusion_Blazor_Charts_AccumulationChartTooltipSettings_Enable) property.

{% aspTab template="chart/accumulation-charts/tooltip/default", sourceFiles="default.razor" %}

{% endaspTab %}

![Tooltip](images/tool-tip/default-razor.png)

## Header

We can specify header for the tooltip using [`Header`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.AccumulationChartTooltipSettings.html#Syncfusion_Blazor_Charts_AccumulationChartTooltipSettings_Header) property.

{% aspTab template="chart/accumulation-charts/tooltip/header", sourceFiles="header.razor" %}

{% endaspTab %}

![Header](images/tool-tip/header-razor.png)

## Format

By default, tooltip shows information about x and y value in points. In addition to that, you can show more
information in tooltip. For example the format `${point.x} : <b>${point.y}%</b>` shows series name and point x value.

{% aspTab template="chart/accumulation-charts/tooltip/format", sourceFiles="format.razor" %}

{% endaspTab %}

![Format](images/tool-tip/format-razor.png)

## Customization

The [`Fill`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.AccumulationChartTooltipSettings.html#Syncfusion_Blazor_Charts_AccumulationChartTooltipSettings_Fill) and
[`Border`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.AccumulationChartTooltipSettings.html#Syncfusion_Blazor_Charts_AccumulationChartTooltipSettings_Border)
properties are used to customize the background color and border of the tooltip respectively.
The [`TextStyle`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.AccumulationChartTooltipSettings.html#Syncfusion_Blazor_Charts_AccumulationChartTooltipSettings_TextStyle)
property in the tooltip is used to customize the font of the tooltip text.

{% aspTab template="chart/accumulation-charts/tooltip/custom", sourceFiles="custom.razor" %}

{% endaspTab %}

![Customization](images/tool-tip/custom-razor.png)

## Tooltip Text Mapping

By default, tooltip shows information of x and y value in points. You can show more information from datasource in tooltip by using the [`TooltipMappingName`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.AccumulationChartSeries.html#Syncfusion_Blazor_Charts_AccumulationChartSeries_TooltipMappingName) . You can use the `${point.tooltip}` as place holders to display the specified tooltip content.

{% aspTab template="chart/accumulation-charts/tooltip/mapping", sourceFiles="mapping.razor" %}

{% endaspTab %}

![mapping](images/tool-tip/mapping-razor.png)

* [Grouping](./grouping/)
* [Datalabel](./data-label/)

**New Note:** You can refer to our [`Blazor Charts`](https://www.syncfusion.com/blazor-components/blazor-charts) feature tour page for its groundbreaking feature representations. You can also explore our [`Blazor Chart example`](https://blazor.syncfusion.com/demos/chart/line?theme=bootstrap4) to knows various chart types and how to represent time-dependent data, showing trends in data at equal intervals.