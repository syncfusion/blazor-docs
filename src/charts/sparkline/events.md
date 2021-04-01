# Events

## Loaded

Description: Triggers, after the sparkline component has been loaded.

## OnPointRegionMouseClick

Description: Triggers, when the mouse click on the point region of the sparkline.

|   Argument name    |   Description                                          |
|--------------------| -------------------------------------------------------|
|   Event            |    Specifies the current sparkline mouse event           |
|   PointerIndex     |    Specifies the sparkline point index region       |
|   Name               |   Specifies the name of the event |
|   Cancel             |   Specifies the event cancel status |

## OnPointRegionMouseMove

Description: Triggers, when the mouse move on the point region of the sparkline.

|   Argument name    |   Description                                          |
|--------------------| -------------------------------------------------------|
|   Event            |    Specifies the current sparkline mouse event           |
|   PointerIndex     |    Specifies the sparkline point index region       |
|   Name               |   Specifies the name of the event |
|   Cancel             |   Specifies the event cancel status |

## OnLoad

Description: Triggers, before rendering the sparkline. Sparkline will trigger this event first.

## OnSparklineMouseClick

Description: Triggers, when mouse click on the container of the sparkline.

|   Argument name    |   Description                                          |
|--------------------| -------------------------------------------------------|
|   Event            |    Specifies the current sparkline mouse event           |
|   Name               |   Specifies the name of the event |
|   Cancel             |   Specifies the event cancel status |

## OnSparklineMouseMove

Description: Triggers, when the mouse move on the container of the sparkline.

|   Argument name    |   Description                                          |
|--------------------| -------------------------------------------------------|
|   Event            |    Specifies the current sparkline mouse event           |
|   Name               |   Specifies the name of the event |
|   Cancel             |   Specifies the event cancel status |

## Resizing

Description: Triggers, when you resize the maps.

|   Argument name      |   Description                          |
|----------------------| ---------------------------------------|
|   CurrentSize        |   Specifies the size of sparkline         |
|   PreviousSize       |   Specifies the size of previous sparkline|
|   Name               |   Specifies the name of the event |
|   Cancel             |   Specifies the event cancel status |

## SeriesRendering

Description: Triggers, before rendering on each sparkline series. You can customize sparkline series using these arguments.

|   Argument name      |   Description                                                         |
|----------------------| ----------------------------------------------------------------------|
|   Border             |   Specifies the current sparkline series border                         |
|   Fill               |   Specifies the sparkline series fill color                             |
|   LineWidth          |   Specifies the sparkline series line width for applicable line and area|
|   Name               |   Specifies the name of the event |
|   Cancel             |   Specifies the event cancel status |