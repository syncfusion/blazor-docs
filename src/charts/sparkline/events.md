---
title: "Events in Blazor Sparkline component | Syncfusion"

component: "Sparkline"

description: "Learn here all about events of Syncfusion Sparkline (SfSparkline) component and more."
---

# Events in Blazor Sparkline (SfSparkline)

This section describes the Sparkline component's events that will be triggered when appropriate actions are performed. The events should be provided to the Sparkline through the [`SparklineEvents`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SparklineEvents.html).

## Loaded

Triggers after the Sparkline component has been loaded.

```csharp
@using Syncfusion.Blazor.Charts

<SfSparkline DataSource="new int[]{ 0, 6, 4, 1, 3, 2, 5 }" Type="SparklineType.Line" Height="200px" Width="450px">
    <SparklineEvents OnLoaded="@LoadedHandler"></SparklineEvents>
</SfSparkline>

@code{
    public void LoadedHandler(System.EventArgs args)
    {
        // Here you can customize the code.
    }
}
```

## OnPointRendering

Triggers before the point rendering.

|   Argument name    |   Description                                          |
|--------------------| -------------------------------------------------------|
|   PointIndex            |    Specifies the current point index.           |
|   Fill     |    Specifies the point index color.       |
|   Border               |   Specifies the color and width of point border. |
|   Cancel               |   Specifies the event cancel status. |

```csharp
@using Syncfusion.Blazor.Charts

<SfSparkline DataSource="new int[]{ 6, 4, 1, 3, 2, 5 }" Type="SparklineType.Column" Height="200px" Width="450px">
    <SparklineMarkerSettings Visible="new List<VisibleType>() { VisibleType.All }"></SparklineMarkerSettings>
    <SparklineEvents OnPointRendering="@PointRenderHandler"></SparklineEvents>
</SfSparkline>

@code{
    public void PointRenderHandler(SparklinePointEventArgs args)
    {
        // Here you can customize the code.
    }
}
```

## OnPointRegionMouseClick

Triggers when the mouse click on point region.

|   Argument name    |   Description                                          |
|--------------------| -------------------------------------------------------|
|   PointerIndex     |    Specifies the sparkline point index region.      |
|   Cancel             |   Specifies the event cancel status. |

```csharp
@using Syncfusion.Blazor.Charts

<SfSparkline DataSource="new int[]{ 6, 4, 1, 3, 2, 5 }" Type="SparklineType.Column" Height="200px" Width="450px">
    <SparklineMarkerSettings Visible="new List<VisibleType>() { VisibleType.All }"></SparklineMarkerSettings>
    <SparklineEvents OnPointRegionMouseClick="@PointRegionMouseClickHandler"></SparklineEvents>
</SfSparkline>

@code{
    public void PointRegionMouseClickHandler(PointRegionEventArgs args)
    {
        // Here you can customize the code.
    }
}
```

## OnResizing

Triggers while resize the window.

|   Argument name      |   Description                          |
|----------------------| ---------------------------------------|
|   CurrentSize        |   Specifies the size of sparkline.         |
|   PreviousSize       |   Specifies the size of previous sparkline. |
|   Cancel             |   Specifies the event cancel status. |

```csharp
@using Syncfusion.Blazor.Charts

<SfSparkline DataSource="new int[]{ 0, 6, 4, 1, 3, 2, 5 }" Type="SparklineType.Line" Height="200px" Width="450px">
    <SparklineEvents OnResizing="@ResizeHandler"></SparklineEvents>
</SfSparkline>

@code{
    public void ResizeHandler(SparklineResizeEventArgs args)
    {
        // Here you can customize the code.
    }
}
```

## OnSeriesRendering

Triggers before rendering on each Sparkline series.

|   Argument name      |   Description                                                         |
|----------------------| ----------------------------------------------------------------------|
|   Border             |   Specifies the color and width of series border.                         |
|   Fill               |   Specifies the series fill color.                             |
|   LineWidth          |   Specifies the series line width. |
|   Cancel             |   Specifies the event cancel status. |

```csharp
@using Syncfusion.Blazor.Charts

<SfSparkline DataSource="new int[]{ 0, 6, 4, 1, 3, 2, 5 }" Type="SparklineType.Line" Height="200px" Width="450px">
    <SparklineEvents OnSeriesRendering="@SeriesRenderingHandler"></SparklineEvents>
</SfSparkline>

@code{
    public void SeriesRenderingHandler(SeriesRenderingEventArgs args)
    {
        // Here you can customize the code.
    }
}
```

## OnMarkerRendering

Triggers before rendering the Sparkline marker render.

|   Argument name      |   Description                                                         |
|----------------------| ----------------------------------------------------------------------|
|   Border             |   Specifies the color and width of marker border.                         |
|   Fill               |   Specifies the marker fill color.                             |
|   PointIndex          |   Specifies the marker point index. |
|   X          |   Specifies the x axis of marker. |
|   Y          |   Specifies the x axis of marker. |
|   Size          |   Specifies the size of marker. |
|   Cancel             |   Specifies the event cancel status. |

```csharp
@using Syncfusion.Blazor.Charts

<SfSparkline DataSource="new int[]{ 6, 4, 1, 3, 2, 5 }" Type="SparklineType.Line" Height="200px" Width="450px">
    <SparklineMarkerSettings Visible="new List<VisibleType>() { VisibleType.All }"></SparklineMarkerSettings>
    <SparklineEvents OnMarkerRendering="@MarkerRenderingHandler"></SparklineEvents>
</SfSparkline>

@code{
    public void MarkerRenderingHandler(MarkerRenderingEventArgs args)
    {
        // Here you can customize the code.
    }
}
```

## OnDataLabelRendering

Triggers before rendering the Sparkline data label render.

|   Argument name      |   Description                                                         |
|----------------------| ----------------------------------------------------------------------|
|   Border             |   Specifies the color and width of data label border.                        |
|   Fill               |   Specifies the series fill color of data label.                             |
|   PointIndex          |   Specifies the data label point index. |
|   X          |   Specifies the x axis of data label. |
|   Y          |   Specifies the y axis of data label. |
|   Text          |   Specifies the content of data label. |
|   Color          |   Specifies the content color. |
|   Cancel             |   Specifies the event cancel status. |

```csharp
@using Syncfusion.Blazor.Charts

<SfSparkline DataSource="new int[]{ 6, 4, 1, 3, 2, 5 }" Type="SparklineType.Line" Height="200px" Width="450px">
    <SparklineDataLabelSettings Visible="new List<VisibleType>() { VisibleType.All }"></SparklineDataLabelSettings>
    <SparklineEvents OnDataLabelRendering="@DataLabelRenderingHandler"></SparklineEvents>
    <SparklineAxisSettings MinX="-1" MaxX="7" MaxY="7" MinY="-1"></SparklineAxisSettings>
</SfSparkline>

@code{
    public void DataLabelRenderingHandler(DataLabelRenderingEventArgs args)
    {
        // Here you can customize the code.
    }
}
```
