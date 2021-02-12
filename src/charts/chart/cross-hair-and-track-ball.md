---

component: "Chart"

---

# Crosshair

Crosshair has a vertical and horizontal line to view the value of the axis at mouse or touch position.

Crosshair lines can be enabled by using [`Enable`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartCrosshairSettings.html#Syncfusion_Blazor_Charts_ChartCrosshairSettings_Enable)
property in the [`Crosshair`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Grids.GridEvents-1.html#Syncfusion_Blazor_Grids_GridEvents_1_OnActionFailure).

{% aspTab template="chart/user-interaction/crosshair-trackball/crosshair", sourceFiles="crosshair.razor" %}

{% endaspTab %}

![Crosshair](images/crosshair/crosshair-razor.png)

## Tooltip for axis

Tooltip label for an axis can be enabled by using `Enable` property of `CrosshairTooltip` in the corresponding axis.

{% aspTab template="chart/user-interaction/crosshair-trackball/axis-tooltip", sourceFiles="axis-tooltip.razor" %}

{% endaspTab %}

## Customization

The `Fill` and `TextStyle` property of the `CrosshairTooltip` is used to customize the background color and font style of the crosshair label respectively. Color and width of the crosshair line can be customized by using the
[`Line`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartCrosshairSettings.html#Syncfusion_Blazor_Charts_ChartCrosshairSettings_Line) property in the crosshair.

{% aspTab template="chart/user-interaction/crosshair-trackball/custom", sourceFiles="custom.razor" %}

{% endaspTab %}

## Trackball

Trackball is used to track a data point closest to the mouse or touch position. Trackball marker indicates the
closest point and trackball tooltip displays the information about the point.

Trackball can be enabled by setting the [`Enable`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartCrosshairSettings.html#Syncfusion_Blazor_Charts_ChartCrosshairSettings_Enable) property of the crosshair to true and
[`Shared`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartTooltipSettings.html#Syncfusion_Blazor_Charts_ChartTooltipSettings_Shared) property in `Tooltip` to true in chart.

{% aspTab template="chart/user-interaction/crosshair-trackball/trackball", sourceFiles="trackball.razor" %}

{% endaspTab %}

![Trackball](images/crosshair/trackball-razor.png)

## See Also

* [Data label](./data-labels)
* [Tooltip](./tool-tip)
* [Marker](./data-markers)