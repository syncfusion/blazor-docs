# Events

## AnimationCompleted

Description: Triggers, after animation is completed.

## AxisLabelRendering

Description: Triggers, before rendering on each axis label. You can customize the labels using
these arguments.

|   Argument name      |   Description                               |
|----------------------| --------------------------------------------|
|   Text               |   Specifies the current axis label text       |
|   X                  |   Specifies the current axis label x location |
|   Y                  |   Specifies the current axis label y location |
|   Name               |   Specifies the name of the event |
|   Cancel             |   Specifies the event cancel status |

## LegendRendering

Description: Triggers, before rendering on each legend. You can customize the legends using these arguments.

|   Argument name      |   Description                                                    |
|----------------------| -----------------------------------------------------------------|
|   Fill               |   Specifies the legend shape color                               |
|   Shape              |   Customize the shape of the legends                         |
|   Text               |   Specifies the current legend text |
|   Name               |   Specifies the name of the event |
|   Cancel             |   Specifies the event cancel status |

## OnLoad

Description: Triggers, before rendering the Smith Chart. Smith Chart will trigger this event first.

## Loaded

Description: Triggers, after the Smith Chart component has been loaded.

## OnPrint

Description: Triggers, before the prints gets started.

## SeriesRendering

Description: Triggers, before rendering on each series. You can customize the series using
these arguments.

|   Argument name      |   Description                                         |
|----------------------| ------------------------------------------------------|
|   Fill               |   Specifies the legend shape color                    |
|   Text               |   Specifies the current series text               |
|   Name               |   Specifies the name of the event |
|   Cancel             |   Specifies the event cancel status |

## SubtitleRendering

Description: Triggers, before the sub-title is rendered. You can customize the subtitle text using
these arguments.

|   Argument name      |   Description                               |
|----------------------| --------------------------------------------|
|   Text               |   Specifies the current subtitle text         |
|   X                  |   Specifies the current subtitle x location   |
|   Y                  |   Specifies the current subtitle y location   |
|   Name               |   Specifies the name of the event |
|   Cancel             |   Specifies the event cancel status |

## TextRendering

Description: Triggers, before the datalabel text is rendered. You can customize the datalabel using
these arguments.

|   Argument name      |   Description                               |
|----------------------| --------------------------------------------|
|   PointerIndex       |   Specifies the current pointIndex of the labels  |
|   SeriesIndex        |   Specifies the current seriesIndex of the labels |
|   Text               |   Specifies the current text of the labels       |
|   X                  |   Specifies the current datalabel x location  |
|   Y                  |   Specifies the current datalabel y location  |
|   Name               |   Specifies the name of the event |
|   Cancel             |   Specifies the event cancel status |

## TitleRendering

Description: Triggers before the title is rendered. You can customize the title using
these arguments.

|   Argument name      |   Description                            |
|----------------------| -----------------------------------------|
|   Text               |   Specifies the current title text         |
|   X                  |   Specifies the current title x location   |
|   Y                  |   Specifies the current title y location   |
|   Name               |   Specifies the name of the event |
|   Cancel             |   Specifies the event cancel status |