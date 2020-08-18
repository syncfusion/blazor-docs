# Events

## ItemHighlighted

Description: Triggers, before applying highlight option to the items.

|   Argument name      |   Description                                 |
|----------------------| ----------------------------------------------|
|   Elements           |   Specifies the current element of highlight   |
|   Item               |   Specifies the current item highlight           |
|   Name               |   Specifies the name of the event                |
|   Cancel             |   Specifies the event cancel status              |

## ItemRendering

Description: Triggers, before rendering the item of the treemap.

|   Argument name      |   Description                         |
|----------------------| --------------------------------------|
|   CurrentItem        |   Specifies the current rendering item   |
|   Options            |   Specifies the rendering items options  |
|   Name               |   Specifies the name of the event        |
|   Cancel             |   Specifies the event cancel status      |
|   Text               |   Specifies the text of the current item |

## ItemSelected

Description: Triggers, when selecting the item.

|   Argument name      |   Description                         |
|----------------------| --------------------------------------|
|   Item               |   Specifies the current item highlight   |
|   Elements           |   Specifies the current element of selected       |
|   Name               |   Specifies the name of the event                 |
|   Cancel             |   Specifies the event cancel status               |

## LegendItemRendering

Description: Triggers, before rendering of the each legend item. You can customize legend item using
these arguments.

|   Argument name      |   Description                                                    |
|----------------------| -----------------------------------------------------------------|
|   Fill               |   Specifies the legend shape color                               |
|   Name               |   Specifies the name of the event                                |
|   Cancel             |   Specifies the event cancel status                              |
|   ImageUrl           |   Customize the image url                                        |
|   Shape              |   Customize the legend shape of the treemap                      |

## Loaded

Description: Triggers, after the treemap component has been loaded.

## OnLoad

Description: Triggers, before rendering the treemap. Treemap will trigger this event first.

## OnPrint

Description: Triggers, before the print operation gets started.

|   Argument name      |   Description                                 |
|----------------------| ----------------------------------------------|
|   HtmlContent        |   Specifies the Element              |
|   Name               |   Specifies the name of the event                 |
|   Cancel             |   Specifies the event cancel status               |

## OnClick

Description: Triggers, when you click on the treemap.

|   Argument name      |   Description                                 |
|----------------------| ----------------------------------------------|
|   MouseEvent         |   Specifies the pointer mouse event              |
|   TreeMap            |   Specifies the current treemap instances        |
|   Name               |   Specifies the name of the event                 |
|   Cancel             |   Specifies the event cancel status               |

## OnDoubleClick

Description: Triggers, when you double click on the treemap.

|   Argument name      |   Description                         |
|----------------------| --------------------------------------|
|   MouseEvent         |   Specifies the mouse event              |
|   Name               |   Specifies the name of the event         |
|   Cancel             |   Specifies the event cancel status       |

## DrillCompleted

Description: Triggers, when you finished click on the item.

|   Argument name      |   Description                         |
|----------------------| --------------------------------------|
|   RenderItems        |   Specifies the rendering all items      |
|   Name               |   Specifies the name of the event        |
|   Cancel             |   Specifies the event cancel status      |

## OnDrillStart

Description: Triggers, when you start to click on the item.

|   Argument name      |   Description                                             |
|----------------------| ----------------------------------------------------------|
|   ChildItems         |   Return the child values to process the onDemand support |
|   GroupIndex         |   Specifies the level of the treemap item                   |
|   GroupName          |   Specifies the parent name of the treemap item             |
|   Item               |   Specifies the current item click                           |
|   Element            |   Specifies the current element of drill down                |
|   RightClick         |   Return the boolean value whether it is right or not     |
|   Name               |   Specifies the name of the event                                |
|   Cancel             |   Specifies the event cancel status                              |

## OnItemClick

Description: Triggers, when you click on the item.

|   Argument name      |   Description                                 |
|----------------------| ----------------------------------------------|
|   GroupIndex         |   Specifies the level of the treemap item       |
|   GroupName          |   Specifies the parent name of the treemap item |
|   Item               |   Specifies the current item click               |
|   MouseEvent         |   Specifies the pointer mouse event              |
|   Name               |   Specifies the name of the event                |
|   Cancel             |   Specifies the event cancel status              |
|   Text               |   Specifies the text of the current item         |

## OnItemMove

Description: Triggers the item move.

|   Argument name      |   Description                         |
|----------------------| --------------------------------------|
|   Item               |   Specifies the current item highlight   |
|   MouseEvent         |   Specifies the mouse event              |
|   Name               |   Specifies the name of the event        |
|   Cancel             |   Specifies the event cancel status      |

## OnMouseMove

Description: Triggers on cursor moving on the treemap.

|   Argument name      |   Description                         |
|----------------------| --------------------------------------|
|   MouseEvent         |   Specifies the mouse event              |
|   Name               |   Specifies the name of the event        |
|   Cancel             |   Specifies the event cancel status      |

## OnRightClick

Description: Triggers when you right-click on the maps.

|   Argument name      |   Description                         |
|----------------------| --------------------------------------|
|   MouseEvent         |   Specifies the mouse event              |
|   Name               |   Specifies the name of the event        |
|   Cancel             |   Specifies the event cancel status      |

## Resizing

Description: Triggers when you resize the maps

|   Argument name      |   Description                          |
|----------------------| ---------------------------------------|
|   CurrentSize        |   Specifies the size of treemap           |
|   PreviousSize       |   Specifies the size of previous treemap  |
|   Name               |   Specifies the name of the event          |
|   Cancel             |   Specifies the event cancel status        |

## TooltipRendering

Description: Triggers, before rendering the treemap tooltip.

|   Argument name      |   Description                         |
|----------------------| --------------------------------------|
|   Location           |   Specifies the location of tooltip     |
|   Text               |   Specifies the text of tooltip         |
|   TextStyle          |   Specifies the text style of tooltip   |
|   Data               |   Specifies the data of the tooltip       |
|   Template           |   Specifies the template of tooltip  |
|   Name               |   Specifies the name of the event    |
|   Cancel             |   Specifies the event cancel status  |