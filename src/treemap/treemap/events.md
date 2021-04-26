---
title: "Events in Blazor TreeMap component | Syncfusion"

component: "TreeMap"

description: "Learn here all about Events of Syncfusion TreeMap (SfTreeMap) component and more."
---

# Events in Blazor TreeMap (SfTreeMap)

## ItemHighlighted

Triggers, after highlight the TreeMap items.

|   Argument name      |   Description                                 |
|----------------------| ----------------------------------------------|
|   Cancel             |   Specifies the event cancel status.          |

## ItemRendering

Triggers, before rendering the item of the TreeMap.

|   Argument name      |   Description                         |
|----------------------| --------------------------------------|
|   CurrentItem        |   Specifies the current rendering item.   |
|   Text               |   Specifies the text of the current item. |
|   Cancel             |   Specifies the event cancel status.      |

## ItemSelected

Triggers, after select the TreeMap item.

|   Argument name      |   Description                         |
|----------------------| --------------------------------------|
|   Text               |   Specifies the text of the selected item.                |
|   Cancel             |   Specifies the event cancel status.               |

## LegendRendering

Triggers, before rendering the TreeMap legend.

|   Argument name      |   Description                                 |
|----------------------| ----------------------------------------------|
|   Cancel             |   Specifies the event cancel status.          |

## LegendItemRendering

Triggers, before rendering of the each legend item.

|   Argument name      |   Description                                                    |
|----------------------| -----------------------------------------------------------------|
|   Fill               |   Specifies the legend shape color.                               |
|   ImageUrl           |   Specifies the image url.                                        |
|   Shape              |   Specifies the legend shape.                     |
|   ShapeBorder              |   Specifies the legend border color and width.                     |
|   Cancel             |   Specifies the event cancel status        .                      |

## Loaded

Triggers, after the TreeMap component has been loaded.

|   Argument name      |   Description                                                    |
|----------------------| -----------------------------------------------------------------|
|   IsResized               |   Specifies whether the component resize or not.                               |

## Load

Triggers, before rendering the TreeMap. TreeMap will trigger this event first.

## OnPrint

Triggers, before the print operation gets started.

|   Argument name      |   Description                                 |
|----------------------| ----------------------------------------------|
|   Cancel             |   Specifies the event cancel status.              |

## OnClick

Description: Triggers, when click on the treemap.

|   Argument name      |   Description                                 |
|----------------------| ----------------------------------------------|
|   MouseEvent         |   Specifies the pointer mouse event.             |
|   TreeMap            |   Specifies the current treemap instances.        |
|   Name               |   Specifies the name of the event.                 |
|   Cancel             |   Specifies the event cancel status.               |

## OnDoubleClick

Triggers, when double click on the treemap.

|   Argument name      |   Description                         |
|----------------------| --------------------------------------|
|   Cancel             |   Specifies the event cancel status.       |

## DrillCompleted

Triggers, when drill down functionality get completed on the TreeMap item.

|   Argument name      |   Description                         |
|----------------------| --------------------------------------|
|   Cancel             |   Specifies the event cancel status.      |

## OnDrillStart

Triggers, when drill down functionality get starts on the TreeMap item.

|   Argument name  | Description         |
|----------------------| ----------------------------------------------------------|
|   GroupIndex         |   Specifies the index of the TreeMap item.                 |
|   GroupName          |   Specifies the parent name of the TreeMap item. item             |
|   Item               |   Specifies the current drill item.                           |
|   RightClick         |   Return the boolean value whether it is right or not.     |
|   Cancel             |   Specifies the event cancel. status                              |

## OnItemClick

Triggers, when click on the TreeMap item.

|   Argument name      |   Description                                 |
|----------------------| ----------------------------------------------|
|   GroupIndex         |   Specifies the index of the TreeMap item       |
|   GroupName          |   Specifies the parent name of the TreeMap item. |
|   Item               |   Specifies the current item on click.             |
|   Text               |   Specifies the text of the current TreeMap item.         |
|   Cancel             |   Specifies the event cancel status.             |

## OnItemMove

Triggers, when mouse move on the TreeMap item.

|   Argument name      |   Description                         |
|----------------------| --------------------------------------|
|   Cancel             |   Specifies the event cancel status.      |

## OnRightClick

Triggers, when right-click on the TreeMap.

|   Argument name      |   Description                         |
|----------------------| --------------------------------------|
|   Cancel             |   Specifies the event cancel status.      |

## Resizing

Triggers, when resizing the TreeMap component.

|   Argument name      |   Description                          |
|----------------------| ---------------------------------------|
|   CurrentSize        |   Specifies the size of TreeMap.           |
|   PreviousSize       |   Specifies the previous size of TreeMap.  |
|   Cancel             |   Specifies the event cancel status.        |

## TooltipRendering

Triggers, before rendering the TreeMap tooltip.

|   Argument name      |   Description                         |
|----------------------| --------------------------------------|
|   Location           |   Specifies the location of tooltip.     |
|   Text               |   Specifies the text of tooltip.         |
|   TextStyle          |   Specifies the text style of tooltip.   |
|   Data               |   Specifies the TreeMap item data, where tooltip to be render.       |
|   Cancel             |   Specifies the event cancel status.  |