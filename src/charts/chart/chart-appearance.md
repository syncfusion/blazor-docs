# Appearance

## Custom Color Palette

You can customize the default color of series or points by providing a custom color palette of your choice by
using the [`Palettes`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Grids.SfGrid-1.html#Syncfusion_Blazor_Grids_SfGrid_1_TextWrapSettings) property.

{% aspTab template="chart/series/column/custom", sourceFiles="custom.razor" %}

{% endaspTab %}

![Custom Color Palette](images/appearance/custom-razor.png)

<!-- markdownlint-disable MD036 -->

## Chart Area Customization

<!-- markdownlint-disable MD036 -->

**Customize the Chart Background**

<!-- markdownlint-disable MD013 -->
Using [`Background`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Grids.GridColumn.html#Syncfusion_Blazor_Grids_GridColumn_Field) and [`Border`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Grids.SfGrid-1.html#Syncfusion_Blazor_Grids_SfGrid_1_ShowColumnChooser) properties, you can change the background color and border of the chart.

{% aspTab template="chart/series/column/area", sourceFiles="area.razor" %}

{% endaspTab %}

![Customize the Chart Background](images/appearance/area-razor.png)

**Chart Margin**

You can set margin for chart from its container through [`Margin`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Grids.SfGrid-1.html#Syncfusion_Blazor_Grids_SfGrid_1_ShowColumnChooser) property.

{% aspTab template="chart/series/column/margin", sourceFiles="margin.razor" %}

{% endaspTab %}

**Chart Area Background**

The chart area background can be customized by using the [`Background`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartAreaModel.html#Syncfusion_Blazor_Charts_ChartAreaModel_Background)
property in the [`ChartArea`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Grids.SfGrid-1.html#Syncfusion_Blazor_Grids_SfGrid_1_ColumnMenuItems).

{% aspTab template="chart/series/column/background", sourceFiles="background.razor" %}

{% endaspTab %}

## Animation

You can customize animation for a particular series using [`Animation`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartSeries.html#Syncfusion_Blazor_Charts_ChartSeries_Animation) property. You can enable or disable animation of the series using [`Enable`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.AnimationModel.html#Syncfusion_Blazor_Charts_AnimationModel_Enable) property. [`Duration`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.AnimationModel.html#Syncfusion_Blazor_Charts_AnimationModel_Duration) specifies the duration of an animation and [`Delay`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.AnimationModel.html#Syncfusion_Blazor_Charts_AnimationModel_Duration) allows us to start the animation at desire time.

{% aspTab template="chart/series/column/animation", sourceFiles="animation.razor" %}

{% endaspTab %}

## Chart Title

Chart can be given a title using [`Title`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Grids.SfGrid-1.html#Syncfusion_Blazor_Grids_SfGrid_1_ColumnMenuItems) property, to show the information about the data plotted.

{% aspTab template="chart/series/column/title", sourceFiles="title.razor" %}

{% endaspTab %}

![Chart Title](images/appearance/title-razor.png)

## Chart SubTitle

Chart can be given a subtitle using [`SubTitle`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Grids.SfGrid-1.html#Syncfusion_Blazor_Grids_SfGrid_1_ContextMenuItems) property, to show the information about the data plotted.

{% aspTab template="chart/series/column/subtitle", sourceFiles="subtitle.razor" %}

{% endaspTab %}

![Chart SubTitle](images/appearance/subtitle-razor.png)

**Note:** You can refer to our [`Blazor Charts`](https://www.syncfusion.com/blazor-components/blazor-charts) feature tour page for its groundbreaking feature representations. You can also explore our [`Blazor Chart example`](https://blazor.syncfusion.com/demos/chart/line?theme=bootstrap4) to knows various chart types and how to represent time-dependent data, showing trends in data at equal intervals.

## See Also

* [Data label](./data-labels)
* [Tooltip](./tool-tip)