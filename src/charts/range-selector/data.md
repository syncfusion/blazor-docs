---
title: " RangeNavigator Data | ASP.NET Core Blazor "

component: "RangeNavigator"

description: "Range navigator supports double, datetime and logarithmic data values for rendering.Also supports labels and range Customization."
---

<!-- markdownlint-disable MD036 -->

# Types of data

## Numeric

Numeric scale is used to represent the numeric values of data in a range navigator. By default, the [`ValueType`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.EjsRangeNavigator~ValueType.html) of a range navigator is `Double`.

{% aspTab template="range-navigator/data/double", sourceFiles="double.razor" %}

{% endaspTab %}

![Numeric](images/data/double.png)

### Range

Minimum and maximum of the scale will be calculated automatically based on the provided data. You can also customize the range using the [`Minimum`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.EjsRangeNavigator~Minimum.html), [`Maximum`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.EjsRangeNavigator~Maximum.html), and [`Interval`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.EjsRangeNavigator~Interval.html) properties.

{% aspTab template="range-navigator/data/range", sourceFiles="range.razor" %}

{% endaspTab %}

![Numeric Range](images/data/numeric-range.png)

### Label Format

Numeric labels can be formatted using the [`LabelFormat`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.EjsRangeNavigator~LabelFormat.html) property and it supports all globalized formats.

{% aspTab template="range-navigator/data/format", sourceFiles="format.razor" %}

{% endaspTab %}

![Numeric Label Format](images/data/format.png)

The following table describes the result of applying some commonly used label formats on numeric values.

<!-- markdownlint-disable MD033 -->
<table>
<tr>
<td><b>Label Value</b></td>
<td><b>Label Format property value</b></td>
<td><b>Result </b></td>
<td><b>Description </b></td>
</tr>
<tr>
<td>1000</td>
<td>n1</td>
<td>1000.0</td>
<td>The Number is rounded to 1 decimal place</td>
</tr>
<tr>
<td>1000</td>
<td>n2</td>
<td>1000.00</td>
<td>The Number is rounded to 2 decimal place</td>
</tr>
<tr>
<td>1000</td>
<td>n3</td>
<td>1000.000</td>
<td>The Number is rounded to 3 decimal place</td>
</tr>
<tr>
<td>0.01</td>
<td>p1</td>
<td>1.0%</td>
<td>The Number is converted to percentage with 1 decimal place</td>
</tr>
<tr>
<td>0.01</td>
<td>p2</td>
<td>1.00%</td>
<td>The Number is converted to percentage with 2 decimal place</td>
</tr>
<tr>
<td>0.01</td>
<td>p3</td>
<td>1.000%</td>
<td>The Number is converted to percentage with 3 decimal place</td>
</tr>
<tr>
<td>1000</td>
<td>c1</td>
<td>$1,000.0</td>
<td>The Currency symbol is appended to number and number is rounded to 1 decimal place</td>
</tr>
<tr>
<td>1000</td>
<td>c2</td>
<td>$1,000.00</td>
<td>The Currency symbol is appended to number and number is rounded to 2 decimal place</td>
</tr>
</table>

### Custom Label Format

The range navigator also supports custom label formats using placeholders such as {value}$, in which, the value represent the axis label, e.g. 20$.

{% aspTab template="range-navigator/data/custom-format", sourceFiles="custom-format.razor" %}

{% endaspTab %}

![Custom Label Format](images/data/custom-format.png)

## Logarithmic Axis

<!-- markdownlint-disable MD033 -->

Logarithmic supports logarithmic scale, and it is used to visualize data when the Range navigator has numerical values in both lower (e.g.: 10-6) and higher (e.g.: 106) orders of magnitude.

{% aspTab template="range-navigator/data/log", sourceFiles="log.razor" %}

{% endaspTab %}

![Logarithmic](images/data/log.png)

**Range**

Minimum and maximum of the Range navigator will be calculated automatically based on the provided data. You can also customize the range using the Minimum, Maximum, and Interval properties.

{% aspTab template="range-navigator/data/log-range", sourceFiles="log-range.razor" %}

{% endaspTab %}

![Logarithmic Range](images/data/log-range.png)

### Logarithmic Base

Logarithmic base can be customized using the [`LogBase`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.EjsRangeNavigator~LogBase.html) property. The default value of the LogBase property is 10.

{% aspTab template="range-navigator/data/log-base", sourceFiles="log-base.razor" %}

{% endaspTab %}

![Logarithmic Base](images/data/log-base.png)

## Date-time

Range navigator supports date-time scale and displays date-time values as a labels in the specified format.

{% aspTab template="range-navigator/data/date-time", sourceFiles="date-time.razor" %}

{% endaspTab %}

![Datetime](images/data/datetime.png)

### Interval Customization

Date-time Intervals can be customized using the [`Interval`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.EjsRangeNavigator~Interval.html) and [`IntervalType`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.EjsRangeNavigator~IntervalType.html) properties of the range navigator.
For example, when you set Interval as 2 and IntervalType as years, the interval will be considered as 2 years.
Date-time supports the following Interval types:
* Auto
* Years
* Quarter
* Months
* Weeks
* Days
* Hours
* Minutes

{% aspTab template="range-navigator/data/date-time-interval", sourceFiles="date-time-interval.razor" %}

{% endaspTab %}

![Datetime Interval](images/data/datetime-interval.png)

**Label Format**

You can format and parse the date to all globalize format using [`LabelFormat`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.EjsRangeNavigator~LabelFormat.html) property.

{% aspTab template="range-navigator/data/date-time-format", sourceFiles="date-time-format.razor" %}

{% endaspTab %}

![Datetime Label Format](images/data/datetime-format.png)

The following table describes the result of applying some common date time formats to the `LabelFormat` property

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
