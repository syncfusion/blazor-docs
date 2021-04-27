# Chart Dimensions

> * When no size is specified, the default height and width are 450px and 600px, respectively.
>
> * To avoid delayed rendering, architectural changes were made to the Chart when the width/height were specified [`in percentages`](#In-Percentage) or [`through style settings`](#Size-for-Container) applied in the component's parent. As a result, the Chart is initially rendered with the default width and height and then redrawn by adjusting only the size of the Chart in a responsive manner. By including the following script in the header tag, the redrawn scenario can now be avoided.

```html
<head>
    ...
    ...
   <script src="https://cdnjs.cloudflare.com/ajax/libs/lodash.js/4.17.20/lodash.min.js"></script>
   <!--- To avoid the redraw scenario, add the CDN link below. --->
   <script src="https://cdn.syncfusion.com/blazor/syncfusion-blazor-base.min.js"></script>
</head>
```

## Size for Container

Chart can be rendered to the size of the container. You can set the size through inline or CSS as shown below.

{% aspTab template="chart/getting-started/size", sourceFiles="size.razor" %}

{% endaspTab %}

## Size for Chart

You can set size for chart directly through [`Width`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SfChart.html#Syncfusion_Blazor_Charts_SfChart_Width) and
[`Height`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SfChart.html#Syncfusion_Blazor_Charts_SfChart_Height) properties.

### In Pixel

You can set the size of chart in pixel as shown below.

{% aspTab template="chart/getting-started/pixel", sourceFiles="pixel.razor" %}

{% endaspTab %}

![Size for Chart](images/chart-dimensions/pixel.png)

### In Percentage

By setting the value in percentage, the chart has its dimension with respect to its container. For example, when the height is **50%**, the chart is half the height of the container.

{% aspTab template="chart/getting-started/percentage", sourceFiles="percentage.razor" %}

{% endaspTab %}

>Note:  You can refer to our [`Blazor Charts`](https://www.syncfusion.com/blazor-components/blazor-charts) feature tour page for its groundbreaking feature representations. You can also explore our [`Blazor Chart example`](https://blazor.syncfusion.com/demos/chart/line?theme=bootstrap4) to knows various chart types and how to represent time-dependent data, showing trends in data at equal intervals.

## See Also

* [Data label](./data-labels)
* [Tooltip](./tool-tip)
* [Marker](./data-markers)