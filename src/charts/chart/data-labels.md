---
title: " Chart DataLabel | ASP.NET Core Blazor "

component: "Chart"

description: "Data labels are names of the data points that are displayed on the x-axis of a chart and also used to highlight important data points"
---

# Data Labels

Data label can be added to a chart series by enabling the `Visible` option in the data label. By default, the labels will arrange smartly without overlapping.

{% aspTab template="chart/datalabels/datalabel", sourceFiles="datalabel.razor" %}

{% endaspTab %}

![Data Labels](images/data-label/datalabel-razor.png)

## Position

Using `Position` property, you can place the label either on `Top`, `Middle`,`Bottom` or `Outer` (outer is applicable for column and bar type series).

{% aspTab template="chart/datalabels/position", sourceFiles="position.razor" %}

{% endaspTab %}

![Position](images/data-label/position-razor.png)

>Note: The position `Outer` is applicable for column and bar type series.

## Data label template

Label content can be formatted by using the template option. Inside the template, you can add the placeholder text `${point.x}` and `${point.y}` to display corresponding data points x & y value.
Using `Template` property, you can set data label template
in chart.

## Text Mapping

Text from the data source can be mapped using `Name` property.

{% aspTab template="chart/datalabels/mapping", sourceFiles="mapping.razor" %}

{% endaspTab %}

![Text Mapping](images/data-label/mapping-razor.png)

## Margin

`Margin` for data label can be applied to using `Left`, `Right`, `Bottom` and `Top` properties.

{% aspTab template="chart/datalabels/margin", sourceFiles="margin.razor" %}

{% endaspTab %}

![Margin](images/data-label/margin-razor.png)

## Customization

`Stroke` and `Border` of data label can be customized using `Fill` and `Border` properties. Rounded corners can be customized using `Rx` and `Ry` properties.

{% aspTab template="chart/datalabels/custom", sourceFiles="custom.razor" %}

{% endaspTab %}

![Customization](images/data-label/custom-razor.png)

>Note: `Rx` and `Ry` properties requires `Border` values not to be null.

## See Also

* [Tooltip](./tool-tip)
* [Legend](./legend)