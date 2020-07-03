---
title: "Pie and Doughnut | ASP.NET Core Blazor "

component: "Accumulation Chart"

description: "Pie and doughnut charts are used to presents the relationship of different parts of data and also known biggest data easily"
---

# Pie & Doughnut

## Pie Chart

To render a pie series, use the series [`Type`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AccumulationChartSeries~Type.html)
as `Pie`.

{% aspTab template="chart/accumulation-charts/pie_doughnut/pie", sourceFiles="pie.razor" %}

{% endaspTab %}

![Pie Chart](../images/pie-dough-nut/pie-razor.png)

## Radius Customization

By default, radius of the pie series will be 80% of the size (minimum of chart width and height).
You can customize this using [`Radius`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AccumulationChartSeries~Radius.html)
property of the series.

{% aspTab template="chart/accumulation-charts/pie_doughnut/radius", sourceFiles="radius.razor" %}

{% endaspTab %}

![Radius Customization](../images/pie-dough-nut/radius-razor.png)

## Pie Center

The center position of the pie can be changed by Center X and Center Y. By default, center x and center y of the pie series are 50%. You can customize this using [`Center`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AccumulationChartModel~Center.html) property of the series.

{% aspTab template="chart/accumulation-charts/pie_doughnut/piecenter", sourceFiles="piecenter.razor" %}

{% endaspTab %}

![Pie Center](../images/pie-dough-nut/piecenter-razor.png)

## Various Radius Pie Chart

You can use radius mapping to render the slice with different [`Radius`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AccumulationChartSeries~Radius.html) and also use border, fill properties to customize the point.

{% aspTab template="chart/accumulation-charts/pie_doughnut/various-radius", sourceFiles="various-radius.razor" %}

{% endaspTab %}

![Various Radius Pie Chart](../images/pie-dough-nut/various-radius-razor.png)

## Doughnut Chart

To achieve a doughnut in pie series, customize the [`InnerRadius`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AccumulationChartSeries~InnerRadius.html)
property of the series. By setting value greater than 0%, a doughnut will appear.
The InnerRadius property takes value from 0% to 100% of the pie radius.

{% aspTab template="chart/accumulation-charts/pie_doughnut/doughnut", sourceFiles="doughnut.razor" %}

{% endaspTab %}

![Doughnut Chart](../images/pie-dough-nut/doughnut-razor.png)

## Start and End angles

You can customize the start and end angle of the pie series using the
[`StartAngle`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AccumulationChartSeries~StartAngle.html) and
[`EndAngle`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AccumulationChartSeries~EndAngle.htmls)
properties. The default value of  StartAngle is 0 degree, and EndAngle is 360 degrees. By customizing this,
you can achieve a semi pie series.

{% aspTab template="chart/accumulation-charts/pie_doughnut/start-angle", sourceFiles="start-angle.razor" %}

{% endaspTab %}

![Start and End angles](../images/pie-dough-nut/start-angle-razor.png)

## Color and Text Mapping

The fill color and the text in the data source can be mapped to the chart using [`PointColorMapping`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AccumulationChartSeries~PointColorMapping.html) in series and [`Name`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AccumulationChartSeries~Name.html) in datalabel respectively.

{% aspTab template="chart/accumulation-charts/pie_doughnut/map", sourceFiles="map.razor" %}

{% endaspTab %}

![Color Mapping](../images/pie-dough-nut/map-razor.png)

## Hide pie or doughnut border

By default, the border will appear in the pie/doughnut chart while mouse hover on the chart. You can disable the the border by setting [`EnableBorderOnMouseMove`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AccumulationChartModel~EnableBorderOnMouseMove.html)
property is `false`.

{% aspTab template="chart/accumulation-charts/pie_doughnut/boder", sourceFiles="boder.razor" %}

{% endaspTab %}

![Pie Chart](../images/pie-dough-nut/pie-razor.png)

## See Also

* [Data label](../data-label/)
* [Grouping](../grouping/)