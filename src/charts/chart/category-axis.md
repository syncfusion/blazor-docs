---
title: " Chart Category Axis | ASP.NET Core Blazor "

component: "Chart"

description: "Category axis are used to represent, the string values instead of numbers.It contains range, label placement customizations."
---

# Category Axis

<!-- markdownlint-disable MD036 -->

Category axis are used to represent the string values instead of numbers.

{% aspTab template="chart/axis/category/column", sourceFiles="column.razor" %}

{% endaspTab %}

<!-- markdownlint-disable MD036 -->

## Labels Placement

<!-- markdownlint-disable MD036 -->

By default, category labels are placed between the ticks in an axis, this can also be placed on ticks
using [`LabelPlacement`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AxisModel~LabelPlacement.html) property.

{% aspTab template="chart/axis/category/placement", sourceFiles="placement.razor" %}

{% endaspTab %}

![Labels Placement](images/category-axis/placement.png)

## Range and Interval

Range of the category axis can be customized using [`Minimum`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AxisModel~Minimum.html),
[`Maximum`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AxisModel~Maximum.html) and [`Interval`](https://help.syncfusion.com/cr/cref_files/aspnetmvc-js2/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartAxis~Interval.html) property of
the axis.

{% aspTab template="chart/axis/category/range", sourceFiles="range.razor" %}

{% endaspTab %}

![Range](images/category-axis/range.png)

## Indexed category axis

Category axis also can be rendered based on the index values of data source. This can be achieved by defining the
[`IsIndexed`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AxisModel~IsIndexed.html) property to `true` in the axis.

{% aspTab template="chart/axis/category/index", sourceFiles="index.razor" %}

{% endaspTab %}

![Indexed category axis](images/category-axis/index-category.png)

## See Also

* [Data label](./data-labels)
* [Tooltip](./tool-tip)
* [Marker](./data-markers)