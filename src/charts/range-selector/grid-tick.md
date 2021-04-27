---
title: " Grid and Ticklines in Blazor Range Selector component | Syncfusion "

component: "Range Selector"

description: "Learn here all about Grid and Ticklines of Syncfusion Blazor Range Selector (SfRangeNavigator) component and more."
---

# Grid and Ticklines in Blazor Range Selector (SfRangeNavigator)

## Gridline Customization

Gridlines indicate axis divisions by drawing the chart plot. Gridlines include helpful cues to the user, particularly for large or complicated charts. The [`Width`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartCommonMajorGridLines.html#Syncfusion_Blazor_Charts_ChartCommonMajorGridLines_Width), [`Color`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartCommonMajorGridLines.html#Syncfusion_Blazor_Charts_ChartCommonMajorGridLines_Color), and [`DashArray`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartCommonMajorGridLines.html#Syncfusion_Blazor_Charts_ChartCommonMajorGridLines_DashArray) of the major gridlines, can be customized by using the [`RangeNavigatorMajorGridLines`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.RangeNavigatorMajorGridLines.html) setting.

{% aspTab template="range-navigator/grid/grid", sourceFiles="grid.razor" %}

{% endaspTab %}

![Gridline customization](images/grid-tick/grid.png)

## Tickline Customization

Tick line are the small lines which is drawn on the axis line representing the axis labels. Tick lines will be drawn outside of the axis by default. The [`Width`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartCommonMajorTickLines.html#Syncfusion_Blazor_Charts_ChartCommonMajorTickLines_Width), [`Color`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartCommonMajorTickLines.html#Syncfusion_Blazor_Charts_ChartCommonMajorTickLines_Color), and [`Height`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartCommonMajorTickLines.html#Syncfusion_Blazor_Charts_ChartCommonMajorTickLines_Height) of the major ticklines, can be customized by using the [`RangeNavigatorMajorTickLines`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.RangeNavigatorMajorTickLines.html) setting.

{% aspTab template="range-navigator/grid/tick", sourceFiles="tick.razor" %}

{% endaspTab %}

![Tickline customization](images/grid-tick/tick.png)