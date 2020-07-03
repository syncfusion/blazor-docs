---
title: "Chart Axis Labels | ASP.NET Core Blazor"

component: "Chart"

description: "Chart contains smart axis labels, label positioning, multilevelabels, text customization and sorting properties "
---

# Axis Labels

## Smart Axis Labels

When the axis labels overlap with each other, you can use [`LabelIntersectAction`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AxisModel~LabelIntersectAction.html)
property in the axis, to place them smartly.

When setting [`LabelIntersectAction`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AxisModel~LabelIntersectAction.html) as `Hide`

{% aspTab template="chart/axis/multiple/hide", sourceFiles="hide.razor" %}

{% endaspTab %}

![Hide](images/axis-labels/hide.png)

When setting [`LabelIntersectAction`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AxisModel~LabelIntersectAction.html) as `Rotate45`

{% aspTab template="chart/axis/multiple/rotate45", sourceFiles="rotate45.razor" %}

{% endaspTab %}

![Rotate45](images/axis-labels/rotate45.png)

When setting [`LabelIntersectAction`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AxisModel~LabelIntersectAction.html) as `Rotate90`

{% aspTab template="chart/axis/multiple/rotate90", sourceFiles="rotate90.razor" %}

{% endaspTab %}

![Rotate90](images/axis-labels/rotate90.png)

## Axis Labels Positioning

By default, the axis labels can be placed `Outside` of the axis line and this also can be placed `Inside`
the axis line using the [`LabelPosition`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AxisModel~LabelPosition.html) property.

{% aspTab template="chart/axis/multiple/position", sourceFiles="position.razor" %}

{% endaspTab %}

![Axis Labels Positioning](images/axis-labels/position.png)

## Multilevel Labels

Any number of levels of labels can be added to an axis using the [`MultiLevelLabels`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AxisModel~MultiLevelLabels.html) property. This property can be configured using the following properties.

### Categories

Using the categories, you can configure the `Start`, `End`, `Text`, and `MaximumTextWidth` of multilevel labels.

### Overflow

Using the `Overflow` property, you can `Trim` or `Wrap` the multilevel labels.

### Alignment

The `Alignment` property provides option to position the multilevel labels at `Far`, `Center`, or `Near`.

### Text customization

The `TextStyle` property of multilevel labels provides options to customize the `Size`, `Color`, `FontFamily`,
`FontWeight`, `FontStyle`, `Opacity`, `TextAlignment` and `TextOverflow`.

### Border customization

Using the `Border` property, you can customize the `Width`, `Color`, and `Type`. The `Type` of border
are `Rectangle`, `Brace`, `WithoutBorder`, `WithoutTopBorder`, `WithoutTopandBottomBorder` and `CurlyBrace`.

## Edge Label Placement

Labels with long text at the edges of an axis may appear partially in the chart. To avoid this,
use [`EdgeLabelPlacement`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AxisModel~EdgeLabelPlacement.html) property in axis, which moves
the label inside the chart area for better appearance or hides it.

{% aspTab template="chart/axis/multiple/edge", sourceFiles="edge.razor" %}

{% endaspTab %}

## Labels Customization

The [`LabelStyle`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AxisModel~LineStyle.html) property of an axis provides options to customize the color and font of the axis labels.

{% aspTab template="chart/axis/multiple/labels-custom", sourceFiles="labels-custom.razor" %}

{% endaspTab %}

## Label Trim

You can trim the label using [`EnableTrim`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AxisModel~EnableTrim.html)  and width of the labels can also be customized using [`MaximumLabelWidth`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AxisModel~MaximumLabelWidth.html) property in the axis, by default maximum width of the label is `34px`.

{% aspTab template="chart/axis/multiple/labels-trim", sourceFiles="labels-trim.razor" %}

{% endaspTab %}

![Trim using maximum label width](images/axis-labels/labels-trim.png)

## Line break

Line break feature used to break the long axis label into multiple lines by using
`<br>` tag.

{% aspTab template="chart/axis/multiple/line-break", sourceFiles="line-break.razor" %}

{% endaspTab %}

![Line break support](images/axis-labels/line-break.png)

## Label Format

* [Numeric Label Format](./numeric-axis#label-format)
* [DateTime Label Format](./date-time-axis#label-format)
* [Custom Label Format](./date-time-axis#custom-label-format)

## See Also

* [Data label](./data-labels)
* [Tooltip](./tool-tip)
* [Marker](./data-markers)