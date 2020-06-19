---
title: " Accumulation Chart Annotation | ASP.NET Core Blazor "

component: "Accumulation Chart"

description: "The annotations are used to mark the specific area of interest in the chart area with texts, shapes or images"
---

# Annotation

The annotations are used to mark the specific area of interest in the chart  with texts, shapes or images. By using the `content` option of annotation property, you can specify the Id of the HTML element that needs to be displayed in the chart.

{% aspTab template="chart/accumulation-charts/annotation/annotation", sourceFiles="annotation.razor" %}

{% endaspTab %}

![Annotation](images/annotation/annotation-razor.png)

## Region

The annotation can be placed with respect to `Series` or `Chart`.

{% aspTab template="chart/accumulation-charts/annotation/region", sourceFiles="region.razor" %}

{% endaspTab %}

![Region](images/annotation/region-razor.png)

## Co-ordinate Units

Specifies the coordinate units of an annotation either in `Pixel` or `Point`.

{% aspTab template="chart/accumulation-charts/annotation/co-ordinate", sourceFiles="co-ordinate.razor" %}

{% endaspTab %}

![Co-ordinate Units](images/annotation/co-ordinate-razor.png)

## Alignment

The annotations can be moved vertically and horizontally from its default position by using [`VerticalAlignment`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AccumulationAnnotationSettingsModel.html) or [`HorizontalAlignment`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AccumulationAnnotationSettingsModel.html) properties. The `VerticalAlignment` provides options to move the content to `Top`, `Bottom` or `Middle` and the `HorizontalAlignment` mouses the content to `Near`, `Far` or `Center`.

{% aspTab template="chart/accumulation-charts/annotation/alignment", sourceFiles="alignment.razor" %}

{% endaspTab %}