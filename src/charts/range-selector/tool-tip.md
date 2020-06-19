---
title: " RangeNavigator Tooltip | ASP.NET Core Blazor "

component: "RangeNavigator"

description: "The range navigator supports tooltips for sliders.Tooltips  display the selected start and end values."
---

# Tooltip

<!-- markdownlint-disable MD036 -->

The range navigator supports tooltips for sliders. Sliders are used to select data at a range in the range navigator.
Tooltips  display the selected start and end values.

<!-- markdownlint-disable MD013 -->

## Enable Tooltip

The tooltip is useful to show the selected data. You can enable tooltip by setting the [`Enable`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.RangeNavigatorRangeTooltipSettings~Enable.html) property as true in tooltip object.

{% aspTab template="range-navigator/tooltip/tooltip", sourceFiles="tooltip.razor" %}

{% endaspTab %}

![Enable Tooltip](images/tooltip/tooltip.png)

## Customization

Tooltips can be [customized](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.RangeNavigatorRangeTooltipSettings.html)  using the following properties:

* [`Enable`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.RangeNavigatorRangeTooltipSettings~Enable.html): Customizes the visibility of the tooltip.
* [`DisplayMode`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.RangeNavigatorRangeTooltipSettings~TextStyle.html): Customizes the display mode of the tooltip.
* [`Fill`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.RangeNavigatorRangeTooltipSettings~Fill.html): Customizes the background color of the tooltip.
* [`Opacity`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.RangeNavigatorRangeTooltipSettings~Opacity.html): Customizes the opacity of the tooltip.
* [`TextStyle`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.RangeNavigatorRangeTooltipSettings~TextStyle.html): Customizes the `Size`, `Color`, `FontFamily`, `FontStyle`, `FontWeight`, `TextAlignment` and `TextOverflow` of the tooltip text.

{% aspTab template="range-navigator/tooltip/tooltip-custom", sourceFiles="tooltip-custom.razor" %}

{% endaspTab %}

![Customization](images/tooltip/tooltip-custom.png)

## Label Format

You can format and parse the date to all globalize format using [`LabelFormat`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.RangeNavigatorModel~LabelFormat.html) property in an axis.

{% aspTab template="range-navigator/tooltip/format", sourceFiles="format.razor" %}

{% endaspTab %}

![Label Format](images/tooltip/tooltip-format.png)

The following table describes the result of applying some common date time formats to the [`LabelFormat`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.RangeNavigatorModel~LabelFormat.html) property

<!-- markdownlint-disable MD033 -->
<table>
<tr>
<td><b>Label Value</b></td>
<td><b>Label Format Property Value</b></td>
<td><b>Result </b></td>
<td><b>Description </b></td>
</tr>
<tr>
<td>new Date(2000, 03, 10)</td>
<td>EEEE</td>
<td>Monday</td>
<td>The Date is displayed in day format</td>
</tr>
<tr>
<td>new Date(2000, 03, 10)</td>
<td>yMd</td>
<td>04/10/2000</td>
<td>The Date is displayed in month/date/year format</td>
</tr>
<tr>
<td>new Date(2000, 03, 10)</td>
<td> MMM </td>
<td>Apr</td>
<td>The Shorthand month for the date is displayed</td>
</tr>
<tr>
<td>new Date(2000, 03, 10)</td>
<td>hm</td>
<td>12:00 AM</td>
<td>Time of the date value is displayed as label</td>
</tr>
<tr>
<td>new Date(2000, 03, 10)</td>
<td>hms</td>
<td>12:00:00 AM</td>
<td>The Label is displayed in hours:minutes:seconds format</td>
</tr>
</table>