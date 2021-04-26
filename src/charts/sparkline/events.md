---
title: "Events in Blazor Sparkline component | Syncfusion"

component: "Sparkline"

description: "Learn here all about Events of Syncfusion Sparkline (SfSparkline) component and more."
---

# Events in Blazor Sparkline (SfSparkline)

## Loaded

Triggers, after the Sparkline component has been loaded.

## OnPointRendering

Triggers, before the point rendering.

|   Argument name    |   Description                                          |
|--------------------| -------------------------------------------------------|
|   PointIndex            |    Specifies the current point index.           |
|   Fill     |    Specifies the point index color.       |
|   Border               |   Specifies the color and width of point border. |
|   Cancel               |   Specifies the event cancel status. |

## OnPointRegionMouseClick

Triggers, when the mouse click on point region.

|   Argument name    |   Description                                          |
|--------------------| -------------------------------------------------------|
|   PointerIndex     |    Specifies the sparkline point index region.      |
|   Cancel             |   Specifies the event cancel status. |

## OnResizing

Triggers, while resize the window.

|   Argument name      |   Description                          |
|----------------------| ---------------------------------------|
|   CurrentSize        |   Specifies the size of sparkline.         |
|   PreviousSize       |   Specifies the size of previous sparkline. |
|   Cancel             |   Specifies the event cancel status. |

## OnSeriesRendering

Triggers, before rendering on each Sparkline series.

|   Argument name      |   Description                                                         |
|----------------------| ----------------------------------------------------------------------|
|   Border             |   Specifies the color and width of series border.                         |
|   Fill               |   Specifies the series fill color.                             |
|   LineWidth          |   Specifies the series line width. |
|   Cancel             |   Specifies the event cancel status. |

## OnMarkerRendering

Triggers, before rendering the Sparkline marker render.

|   Argument name      |   Description                                                         |
|----------------------| ----------------------------------------------------------------------|
|   Border             |   Specifies the color and width of marker border.                         |
|   Fill               |   Specifies the marker fill color.                             |
|   PointIndex          |   Specifies the marker point index. |
|   X          |   Specifies the x axis of marker. |
|   Y          |   Specifies the x axis of marker. |
|   Size          |   Specifies the size of marker. |
|   Cancel             |   Specifies the event cancel status. |

## OnDataLabelRendering

Triggers, before rendering the Sparkline data label render.

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
