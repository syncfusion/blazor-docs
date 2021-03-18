# Chart Dimensions

## Size for Container

Chart can be rendered to the size of the container. You can set the size inline or CSS as shown below.

{% aspTab template="chart/getting-started/size", sourceFiles="size.razor" %}

{% endaspTab %}

## Size for Chart

You can also set size for chart directly through `Width` and
`Height` properties.

<!-- markdownlint-disable MD036 -->
**In Pixel**
<!-- markdownlint-disable MD036 -->

You can set the size of chart in pixel as shown below.

{% aspTab template="chart/getting-started/pixel", sourceFiles="pixel.razor" %}

{% endaspTab %}

![Size for Chart](images/chart-dimensions/pixel.png)

**In Percentage**

By setting the value in percentage, the chart has its dimension with respect to its container. For example, when the height is ‘50%’, the chart is half the height of the container.

{% aspTab template="chart/getting-started/percentage", sourceFiles="percentage.razor" %}

{% endaspTab %}

> Note:  When you do not specify the size, it takes `450px` as the height and the size of the window as the width.

**New Note:** You can refer to our [`Blazor Charts`](https://www.syncfusion.com/blazor-components/blazor-charts) feature tour page for its groundbreaking feature representations. You can also explore our [`Blazor Chart example`](https://blazor.syncfusion.com/demos/chart/line?theme=bootstrap4) to knows various chart types and how to represent time-dependent data, showing trends in data at equal intervals.

## See Also

* [Data label](./data-labels)
* [Tooltip](./tool-tip)
* [Marker](./data-markers)