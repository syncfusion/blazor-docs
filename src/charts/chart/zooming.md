---
title: " Chart Zooming | ASP.NET Core Blazor "

component: "Chart"

description: "Chart have zooming and panning properties. Chart contains different  zoom modes, zoom toolbar items, scrollbar and auto interval zooming. "
---

# Zooming  and Panning

## Enable Zooming

Chart can be zoomed in three ways.

* Selection - By setting [`EnableSelectionZooming`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartZoomSettings~EnableSelectionZooming.html) property to true
  in [`ZoomSettings`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.EjsChart~ZoomSettings.html), you can zoom the chart by using the rubber band selection.
* MouseWheel - By setting [`EnableMouseWheelZooming`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartZoomSettings~EnableMouseWheelZooming.html) property to true
  in [`ZoomSettings`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.EjsChart~ZoomSettings.html), you can zoomin and zoomout the chart by scrolling the mouse wheel.
* Pinch - By setting  [`EnablePinchZooming`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartZoomSettings~EnablePinchZooming.html) property to true in [`ZoomSettings`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.EjsChart~ZoomSettings.html),
  you can zoom the chart through pinch gesture in touch enabled devices.

 >Pinch zooming is supported only in browsers that support multi-touch gestures. Currently IE11, Chrome and Opera browsers support multi-touch in desktop devices.

{% aspTab template="chart/user-interaction/zoom/default", sourceFiles="default.razor" %}

{% endaspTab %}

![Enable Zooming](images/zoom/default-razor.png)

After zooming the chart, a zooming toolbar will appear with `Zoom`,`ZoomIn`, `ZoomOut`, `Pan` and `Reset` buttons.
Selecting the Pan option will allow to pan the chart and selecting the Reset option will reset the zoomed chart.

## Modes

The [`Mode`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartZoomSettings~Mode.html) property in ZoomSettings specifies whether the chart is
allowed to scale along the horizontal axis or vertical axis. The default value of the mode is XY (both axis).

There are three types of mode.

* X - Allows us to zoom the chart horizontally.
* Y - Allows us to zoom the chart vertically.
* XY - Allows us to zoom the chart both vertically and horizontally.

{% aspTab template="chart/user-interaction/zoom/mode", sourceFiles="mode.razor" %}

{% endaspTab %}

## Toolbar

By default, zoomin, zoomout, pan and reset buttons will be displayed for zoomed chart. You can customize to show your desire tools in the toolbar using [`ToolbarItems`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartZoomSettings~ToolbarItems.html)
property.

{% aspTab template="chart/user-interaction/zoom/toolbar", sourceFiles="toolbar.razor" %}

{% endaspTab %}

## Enable pan

Using [`EnablePan`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartZoomSettings~EnablePan.html)
property you can able to pan the zoomed chart without help of toolbar items.

{% aspTab template="chart/user-interaction/zoom/pan", sourceFiles="pan.razor" %}

{% endaspTab %}

## Enable Scrollbar

Using [`EnableScrollbar`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartZoomSettings~EnableScrollbar.html) property, you can able to add scrollbar for zoomed chart. Using this scrollbar, you can pan or zoom the chart.

{% aspTab template="chart/user-interaction/zoom/scrollbar", sourceFiles="scrollbar.razor" %}

{% endaspTab %}

![Enable Scrollbar](images/zoom/scrollbar-razor.png)

## Auto interval on zooming

By using [`EnableAutoIntervalOnZooming`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartAxis~EnableAutoIntervalOnZooming.html) property,
the axis interval will get calculated automatically with respect to the zoomed range.

{% aspTab template="chart/user-interaction/zoom/auto-interval", sourceFiles="auto-interval.razor" %}

{% endaspTab %}

## See Also

* [Data label](./data-labels)
* [Legend](./legend)
* [Marker](./data-markers)