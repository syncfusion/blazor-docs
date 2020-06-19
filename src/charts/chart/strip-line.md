---
title: " Chart Strip-lines | ASP.NET Core Blazor "

component: "Chart"

description: "Strip Lines are vertical or horizontal lines used to highlight/mark a certain region on the plot area."
---

<!-- markdownlint-disable MD036 -->

# Striplines

<!-- markdownlint-disable MD036 -->

Blazor chart supports horizontal and vertical strip lines and customization of stripline in both orientation.

## Horizontal Striplines

You can create Horizontal stripline by adding the [`StripLine`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AxisModel~StripLines.html) in the vertical axis.
Striplines are rendered in the specified start to end range and you can add more than one stripline for an axis.

{% aspTab template="chart/axis/strip-line/horizontal", sourceFiles="horizontal.razor" %}

{% endaspTab %}

![Horizontal Strip lines](images/strip-line/horizontal.png)

## Vertical Striplines

You can create vertical stripline by adding the [`StripLine`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AxisModel~StripLines.html) in the horizontal axis. Striplines are rendered in the specified start to end range and you can add more than one stripline for an axis.

{% aspTab template="chart/axis/strip-line/vertical", sourceFiles="vertical.razor" %}

{% endaspTab %}

![Vertical Striplines](images/strip-line/vertical.png)

## Customize the strip line

Starting value in specific strip line can be customized by [`Start`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartStripLine~Start.html) property in strip line. Similarly, ending value
is customized by `End`. It can also set to start from the origin of the axis by `StartFromOrigin`.
Size of the strip line can be customized by [`Size`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartStripLine~Size.html) property. Border for the stripline can be customized by [`Border`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartStripLine~Border.html) property.
Order of the strip line such that whether it should be rendered  behind or over the series elements
can be customized by [`ZIndex`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartStripLine~ZIndex.html) property.

{% aspTab template="chart/axis/strip-line/custom-stripline", sourceFiles="custom-stripline.razor" %}

{% endaspTab %}

![Customize the strip line](images/strip-line/custom-stripline.png)

## Customize the stripline text

You can customize the text rendered in stripline by [`TextStyle`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartStripLine~TextStyle.html) property. Rotation of the  text can be changed by [`Rotation`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartStripLine~Rotation.html) property.
Horizontal and Vertical alignment of stripline text can be changed by [`HorizontalAlignment`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartStripLine~HorizontalAlignment.html) and [`VerticalAlignment`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartStripLine~VerticalAlignment.html) property.

{% aspTab template="chart/axis/strip-line/custom-striptext", sourceFiles="custom-striptext.razor" %}

{% endaspTab %}

![Customize the strip line](images/strip-line/custom-striptext.png)

## See Also

* [Data label](./data-labels)
* [Tooltip](./tool-tip)
* [Marker](./data-markers)