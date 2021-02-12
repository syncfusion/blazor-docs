---

component: "Chart"

---

# Tooltip

<!-- markdownlint-disable MD036 -->

Chart will display details about the points through tooltip, when the mouse is moved over the point.

## Enable Tooltip

The tooltip is useful when you cannot display information by using the data labels due to space constraints.
You can enable tooltip by setting the [`Enable`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartTooltipSettings.html#Syncfusion_Blazor_Charts_ChartTooltipSettings_Enable) property as true
in [`Tooltip`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SfChart.html#Syncfusion_Blazor_Charts_SfChart_Border) object.

{% aspTab template="chart/user-interaction/tooltip/default", sourceFiles="default.razor" %}

{% endaspTab %}

![Enable Tooltip](images/tooltip/default-razor.png)

## Format the Tooltip

<!-- markdownlint-disable MD013 -->

By default, tooltip shows information of x and y value in points. In addition to that, you can show more
information in tooltip. For example the format '${series.name} ${point.x}' shows series name and point x
value.

{% aspTab template="chart/user-interaction/tooltip/format", sourceFiles="format.razor" %}

{% endaspTab %}

![Format the Tooltip](images/tooltip/format-razor.png)

<!-- markdownlint-disable MD013 -->

## Customize the Appearance of Tooltip

The [`Fill`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartTooltipSettings.html#Syncfusion_Blazor_Charts_ChartTooltipSettings_Fill)
and [`Border`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartTooltipSettings.html#Syncfusion_Blazor_Charts_ChartTooltipSettings_Border)
properties are used to customize the background color and border of the tooltip respectively.
The [`TextStyle`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartTooltipSettings.html#Syncfusion_Blazor_Charts_ChartTooltipSettings_TextStyle)
property in the tooltip is used to customize the font of the tooltip text.

{% aspTab template="chart/user-interaction/tooltip/appearance", sourceFiles="appearance.razor" %}

{% endaspTab %}

![Customize the Appearance of Tooltip](images/tooltip/appearance-razor.png)

## See Also

* [Data label](./data-labels)
* [Marker](./data-markers)