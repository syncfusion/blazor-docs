---
title: " Chart Datetime Axis | ASP.NET Core Blazorss "

component: "Chart"

description: "Date time axis uses date time scale and displays the date time values as axis labels in the specified format."
---

<!-- markdownlint-disable MD036 -->

# DateTime and DateTimeCategory Axis

## DateTime Axis

 Date time axis uses date time scale and displays the date time values as axis labels in the specified format.

{% aspTab template="chart/axis/datetime/dateTime", sourceFiles="datetime.razor" %}

{% endaspTab %}

![DateTime Axis](images/datetime/datetime.png)

## DateTimeCategory Axis

Date-time category axis is used to display the date-time values with non-linear intervals. For example, the business days alone can been depicted in a week here.

{% aspTab template="chart/axis/datetime/datetimeCategory", sourceFiles="dateCategory.razor" %}

{% endaspTab %}

### Range

Range for an axis, will be calculated automatically based on the provided data, you can also customize the range
of the axis using [`Minimum`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AxisModel~Minimum.html),
[`Maximum`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AxisModel~Maximum.html) and [`Interval`](https://help.syncfusion.com/cr/cref_files/aspnetmvc-js2/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartAxis~Interval.html) property of the axis.

{% aspTab template="chart/axis/datetime/range", sourceFiles="range.razor" %}

{% endaspTab %}

![Range](images/datetime/range.png)

### Interval Customization

Date time intervals can be customized by using the [`Interval`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AxisModel~Interval.html) and
[`IntervalType`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AxisModel~IntervalType.html) properties of the axis.
For example, when you set Interval as 2 and IntervalType as years, it considers 2 years as Interval.
DateTime axis supports following Interval types,

* Auto
* Years
* Months
* Days
* Hours
* Minutes
* Seconds

{% aspTab template="chart/axis/datetime/interval", sourceFiles="interval.razor" %}

{% endaspTab %}

**Applying Padding to the Range**

Padding can be applied to the Minimum and Maximum extremes of the range by using the
[`RangePadding`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AxisModel~RangePadding.html) property. Date time axis supports the following types
of padding,

* None
* Round
* Additional

**DateTime - None**

When the [`RangePadding`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AxisModel~RangePadding.html) is set to `None`, Minimum and Maximum of the axis is based on the data.

{% aspTab template="chart/axis/datetime/none", sourceFiles="none.razor" %}

{% endaspTab %}

**DateTime - Round**

When the [`RangePadding`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AxisModel~RangePadding.html) is set to `Round`, Minimum and Maximum will be
rounded to the nearest possible value divisible by Interval. For example, when the Minimum is 15th Jan, Interval is
1 and the Interval type is ‘month’, then the axis Minimum will be Jan 1st.

{% aspTab template="chart/axis/datetime/round", sourceFiles="round.razor" %}

{% endaspTab %}

**DateTime - Additional**

When the [`RangePadding`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AxisModel~RangePadding.html) is set to `Additional`, Interval of an axis will
be padded to the Minimum and Maximum of the axis.

{% aspTab template="chart/axis/datetime/additional", sourceFiles="additional.razor" %}

{% endaspTab %}

## Label Format

You can format and parse the date to all globalize format using [`LabelFormat`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.AxisModel~LabelFormat.html) property in an axis.

{% aspTab template="chart/axis/datetime/label-format", sourceFiles="label-format.razor" %}

{% endaspTab %}

The following table describes the result of applying some common date time formats to the labelFormat property

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

<!-- markdownlint-disable MD033 -->

## Custom Label Format

Axis also supports custom label format using placeholder like {value}°C, in which the value represent the axis
label e.g 20°C.

{% aspTab template="chart/axis/datetime/custom", sourceFiles="custom.razor" %}

{% endaspTab %}

## See Also

* [Data label](./data-labels)
* [Tooltip](./tool-tip)
* [Marker](./data-markers)