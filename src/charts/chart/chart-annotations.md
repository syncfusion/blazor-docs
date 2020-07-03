---
title: " Chart Annotations | ASP.NET Core Blazor "

component: "Chart"

description: "Chart annotations are used to mark the specific area of interest in the chart area with texts, shapes or images."
---

# Annotation

Annotations are used to mark the specific area of interest in the chart area with texts, shapes or images.

<!-- markdownlint-disable MD033 -->

You can add annotations to the chart by using the <code>annotations</code> option. By using the
[`Content`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartAnnotation~Content.html) option of annotation , you can specify the id of the element that needs to be displayed in the chart area.

{% aspTab template="chart/series/column/annotation", sourceFiles="annotation.razor" %}

{% endaspTab %}

![Annotation](images/annotation/annotation-razor.png)

## Region

Annotations can be placed either with respect to `Series` or `Chart`. By default, it is placed with respect to `Chart`.

{% aspTab template="chart/series/column/region", sourceFiles="region.razor" %}

{% endaspTab %}

![Region](images/annotation/region-razor.png)

## Co-ordinate Units

The coordinate units of the annotation can be specified either in `Pixel` or `Point`.

{% aspTab template="chart/series/column/co-ordinate", sourceFiles="co-ordinate.razor" %}

{% endaspTab %}

![Co-ordinate Unit](images/annotation/co-ordinate-razor.png)

## Alignment

Annotation provides [`VerticalAlignment`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartAnnotation~VerticalAlignment.html) and [`HorizontalAlignment`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartAnnotation~HorizontalAlignment.html). The `VerticalAlignment` provides options to move the content to `Top`, `Bottom` or `Middle` position and the `HorizontalAlignment` mouses the content to `Near`, `Far` or `Center`.

{% aspTab template="chart/series/column/alignment", sourceFiles="alignment.razor" %}

{% endaspTab %}

## See Also

* [Tooltip](./tool-tip)
* [Legend](./legend)