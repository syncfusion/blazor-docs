---
title: " RangeNavigator Period Selector | ASP.NET Core Blazor "

component: "RangeNavigator"

description: "The period selector allows to select a range with specified periods."
---

# Period selector

The period selector allows to select a range with specified periods.

## Periods

An array of objects that allows users to specify a predefined periods. The [`Interval`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.PeriodsModel~Interval.html) property specifies the count value of the button, and the [`Text`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.PeriodsModel~Text.html) property specifies the text to be displayed on button. The [`IntervalType`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.PeriodsModel~IntervalType.html) property allows users to customize the type of the interval. The `IntervalType` property supports the following interval types:

* Auto
* Years
* Quarter
* Months
* Weeks
* Days
* Hours
* Minutes
* Seconds

{% aspTab template="range-navigator/period/periods", sourceFiles="periods.razor" %}

{% endaspTab %}

![Periods](images/period-selector/periods.png)

## Position

The [`Position`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.RangeNavigatorPeriodSelectorSettings~Position.html) property allows users to position the period selector either at the `Top` or `Bottom`.

{% aspTab template="range-navigator/period/position", sourceFiles="position.razor" %}

{% endaspTab %}

![Positioning](images/period-selector/position.png)

## Height

The [`Height`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.RangeNavigatorPeriodSelectorSettings~Height.html) property allows users to specify the height for period selector. The default value of the height property is 43px.

{% aspTab template="range-navigator/period/height", sourceFiles="height.razor" %}

{% endaspTab %}

![Height](images/period-selector/height.png)

## Visibility

[`DisableRangeSelector`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.RangeNavigatorModel~DisableRangeSelector.html) property allows users to render the period selector without range navigator.

{% aspTab template="range-navigator/period/visible", sourceFiles="visible.razor" %}

{% endaspTab %}

## See Also

* [LightWeight](./light-weight/)