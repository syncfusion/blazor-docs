---
title: " RangeNavigator Labels | ASP.NET Core Blazor "

component: "RangeNavigator"

description: "RangeNavigator supports Multilevel label and enable grouping properties to customize axis labels."
---

# Labels

## Multilevel labels

The second level labels for the range navigator can be enabled by setting the [`EnableGrouping`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.RangeNavigatorModel~EnableGrouping.html) property to true. This is restricted to date-time axis alone.

{% aspTab template="range-navigator/label/multi", sourceFiles="multi.razor" %}

{% endaspTab %}

![Multilevel labels](images/labels/multi.png)

## Grouping

The second level axis labels can be grouped by using [`GroupBy`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.RangeNavigatorModel~GroupBy.html) property with the following interval types:

* Auto
* Years
* Quarter
* Months
* Weeks
* Days
* Hours
* Minutes
* Seconds

{% aspTab template="range-navigator/label/group", sourceFiles="group.razor" %}

{% endaspTab %}

![Grouping](images/labels/group.png)

## Smart labels

The [`LabelIntersectAction`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.RangeNavigatorModel~LabelIntersectAction.html) property is used to avoid overlapping of labels.

The following code sample shows setting the `LabelIntersectAction` property to Hide.

{% aspTab template="range-navigator/label/smart", sourceFiles="smart.razor" %}

{% endaspTab %}

![Smart labels](images/labels/smart.png)

## Position

By default, the labels can be placed at outside of the range navigator. You can place the labels inside the range navigator
using the [`LabelPosition`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.RangeNavigatorModel~LabelPosition.html) property.

{% aspTab template="range-navigator/label/position", sourceFiles="position.razor" %}

{% endaspTab %}

![Label positioning](images/labels/position.png)

## Labels customization

The font size, color, family, etc. can be customized using the [`LabelStyle`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.EjsRangeNavigator~LabelStyle.html) property.

{% aspTab template="range-navigator/label/custom", sourceFiles="custom.razor" %}

{% endaspTab %}

![Labels customization](images/labels/custom.png)