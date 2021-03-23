# Category Axis

<!-- markdownlint-disable MD036 -->

Category axis is used to represent string values instead of numbers.

{% aspTab template="chart/axis/category/column", sourceFiles="column.razor" %}

{% endaspTab %}

<!-- markdownlint-disable MD036 -->

## Labels Placement

<!-- markdownlint-disable MD036 -->

By default, the category labels are placed between the ticks, which can also be placed on the ticks using the [`LabelPlacement`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.AxisModel.html#Syncfusion_Blazor_Charts_AxisModel_LabelPlacement) property.

{% aspTab template="chart/axis/category/placement", sourceFiles="placement.razor" %}

{% endaspTab %}

![Labels Placement](images/category-axis/placement.png)

## Range and Interval

Range of the category axis can be customized using the [`Minimum`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.AxisModel.html#Syncfusion_Blazor_Charts_AxisModel_Minimum),
[`Maximum`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.AxisModel.html#Syncfusion_Blazor_Charts_AxisModel_Maximum) and [`Interval`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AxisModel~Interval.html) properties of
the axis.

{% aspTab template="chart/axis/category/range", sourceFiles="range.razor" %}

{% endaspTab %}

![Range](images/category-axis/range.png)

## Indexed category axis

The category axis can also be rendered on the basis of data source index values. This can be achieved by defining the
[`IsIndexed`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.AxisModel.html#Syncfusion_Blazor_Charts_AxisModel_IsIndexed) property as **true** in the axis.

{% aspTab template="chart/axis/category/index", sourceFiles="index.razor" %}

{% endaspTab %}

![Indexed category axis](images/category-axis/index-category.png)

**Note:** You can refer to our [`Blazor Charts`](https://www.syncfusion.com/blazor-components/blazor-charts) feature tour page for its groundbreaking feature representations. You can also explore our [`Blazor Chart example`](https://blazor.syncfusion.com/demos/chart/line?theme=bootstrap4) to knows various chart types and how to represent time-dependent data, showing trends in data at equal intervals.

## See Also

* [Data label](./data-labels)
* [Tooltip](./tool-tip)
* [Marker](./data-markers)