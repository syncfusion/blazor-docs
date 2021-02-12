---

component: "Chart"

---

# Axis Customization

## Axis Crossing

An axis can be positioned in the chart area using [`CrossesAt`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.AxisModel.html#Syncfusion_Blazor_Charts_AxisModel_CrossesAt) and [`CrossesInAxis`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.AxisModel.html#Syncfusion_Blazor_Charts_AxisModel_CrossesInAxis) properties. The `CrossesAt` property specifies the values (datetime, numeric, or logarithmic) at which the axis line has to be intersected with the vertical axis or vice-versa, and the `CrossesInAxis` property specifies the axis name with which the axis line has to be crossed.

{% aspTab template="chart/axis/category/axis-cross", sourceFiles="axis-cross.razor" %}

{% endaspTab %}

![Axis Crossing](images/axis-customization/axis-cross.png)

## Title

You can add a title to the axis using [`Title`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.AxisModel.html#Syncfusion_Blazor_Charts_AxisModel_Title) property to provide quick
information to the user about the data plotted in the axis. Title style can be customized using [`TitleStyle`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.AxisModel.html#Syncfusion_Blazor_Charts_AxisModel_TitleStyle) property of the axis.

{% aspTab template="chart/axis/category/title", sourceFiles="title.razor" %}

{% endaspTab %}

## Tick Lines Customization

You can customize the  Width, Color and Size of the minor and major tick lines, using
[`MajorTickLines`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.AxisModel.html#Syncfusion_Blazor_Charts_AxisModel_MajorTickLines) and
[`MinorTickLines`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.AxisModel.html#Syncfusion_Blazor_Charts_AxisModel_MinorTickLines) properties in the axis.

{% aspTab template="chart/axis/category/tick", sourceFiles="tick.razor" %}

{% endaspTab %}

![Tick Lines Customization](images/axis-customization/tick.png)

## Grid Lines Customization

You can customize the Width, Color and DashArray of the minor and major grid lines, using [`MajorGridLines`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.AxisModel.html#Syncfusion_Blazor_Charts_AxisModel_MajorGridLines)
and [`MinorGridLines`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.AxisModel.html#Syncfusion_Blazor_Charts_AxisModel_MinorGridLines) properties in the axis.

{% aspTab template="chart/axis/category/grid", sourceFiles="gridline.razor" %}

{% endaspTab %}

![Grid Lines Customization](images/axis-customization/gridline.png)

## Multiple Axis

In addition to primary X and Y axis, we can add n number of axis to the chart. Series can be associated with
this axis, by mapping with axis's unique name. See also

* [Mixed Chart](./chart-series)
* [Multiple Panes](./multiple-panes)

{% aspTab template="chart/axis/category/multiple", sourceFiles="multiple.razor" %}

{% endaspTab %}

![Multiple Axis](images/axis-customization/multiple.png)

## Inversed Axis

<!-- markdownlint-disable MD033 -->

When an axis is inversed, highest value of the axis comes closer to origin and vice versa. To place an axis in inversed manner set this property
 [`IsInversed`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.AxisModel.html#Syncfusion_Blazor_Charts_AxisModel_IsInversed) to true.

 {% aspTab template="chart/axis/category/inversed", sourceFiles="inversed.razor" %}

{% endaspTab %}

![Inversed Axis](images/axis-customization/inversed.png)

## Opposed Position

To place an axis opposite from its original position,
set [`OpposedPosition`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.AxisModel.html#Syncfusion_Blazor_Charts_AxisModel_OpposedPosition) property of the axis to true.

{% aspTab template="chart/axis/category/opposed", sourceFiles="opposed.razor" %}

{% endaspTab %}

![Opposed Position](images/axis-customization/opposed.png)

## See Also

* [Data label](./data-labels)
* [Tooltip](./tool-tip)
* [Marker](./data-markers)