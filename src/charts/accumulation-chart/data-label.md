---
title: " Accumulation Chart Data Label | ASP.NET Core Blazor "

component: "Accumulation Chart"

description: "Data labels are names of the data points that are displayed on the x-axis of a chart and also used to highlight important data points"
---

# Data Label

Data label can be added to a point by enabling the [`Visible`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2~Syncfusion.EJ2.Charts.AccumulationDataLabelSettings~Visible.html)
option in the DataLabel property.

{% aspTab template="chart/accumulation-charts/datalabel/default", sourceFiles="default.razor" %}

{% endaspTab %}

![Data Label](images/data-label/default-razor.png)

## Position

Accumulation chart provides support for placing the data label either `Inside` or `Outside` of the chart by using [`Position`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2~Syncfusion.EJ2.Charts.AccumulationDataLabelSettings~Position.html) property.

{% aspTab template="chart/accumulation-charts/datalabel/position", sourceFiles="position.razor" %}

{% endaspTab %}

![Positioning](images/data-label/position-razor.png)

## Smart Labels

Datalabels will be arranged smartly without overlapping with each other. You can enable or disable this feature using
the [`EnableSmartLabels`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AccumulationChartModel~EnableSmartLabels.html)
property.

{% aspTab template="chart/accumulation-charts/datalabel/smartlabels", sourceFiles="smartlabels.razor" %}

{% endaspTab %}

![Smart Labels](images/data-label/smartlabels-razor.png)

## Connector Line

Connector line will be visible when the data label is placed `Outside` the chart.
The connector line can be customized using the [`Type`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AccumulationChartConnector~Type.html), [`Color`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AccumulationChartConnector~Color.html), [`Width`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AccumulationChartConnector~Width.html), [`Length`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AccumulationChartConnector~Length.html) and [`DashArray`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AccumulationChartConnector~DashArray.html) properties

{% aspTab template="chart/accumulation-charts/datalabel/connector", sourceFiles="connector.razor" %}

{% endaspTab %}

![Connector Line](images/data-label/connector-razor.png)

## Text Mapping

Text from the data source can be mapped to data label using `Name` property.

{% aspTab template="chart/accumulation-charts/datalabel/map", sourceFiles="map.razor" %}

{% endaspTab %}

![Text Mapping](images/data-label/map-razor.png)

## See Also

* [Tooltip](./tool-tip/)
* [Legend](./legend/)