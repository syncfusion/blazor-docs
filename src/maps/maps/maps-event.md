# Events

## Using events in the Maps component

In the following code example, the `OnClick` event binds to the Maps component, so the event handler `GetGEOLocation` will be called when you click the maps and display the currently clicked geo location.

```csharp
@using Syncfusion.Blazor.Maps

<h3>Currently clicked position</h3>
<p>
    Latitude : <b>@Latitude</b><br />
    Longitude : <b>@Longitude</b>
</p>
<SfMaps>
    <MapsEvents OnClick="@GetGEOLocation"></MapsEvents>
    <MapsLayers>
        <MapsLayer ShapeData='new {dataOptions= "https://cdn.syncfusion.com/maps/map-data/world-map.json"}'>
        </MapsLayer>
    </MapsLayers>
</SfMaps>

@code {
    public double Latitude { get; set; }
    public double Longitude { get; set; }
    void GetGEOLocation(IMouseEventArgs args)
    {
        Latitude = args.Latitude;
        Longitude = args.Longitude;
    }
}
```

![Event binding in maps](./images/Events/onclick.png)

## Available events

### AnimationCompleted

Occurs after animation has is completed.

|   Argument name      |   Description                            |
|----------------------| -----------------------------------------|
|   Element            |   Animation element  |
|     Cancel           |    Defines the event cancel status   |
|     Name             |    Name of the event     |

### AnnotationRendering

Occurs before rendering each annotation. You can customize annotations using the following arguments.

|   Argument name      |   Description                        |
|----------------------| -------------------------------------|
|   Content            |   Specifies the annotation content   |
|     Cancel           |    Defines the event cancel status   |
|     Name             |    Name of the event     |
|   Annotation         |   Specifies the annotation instance  |

### BubbleRendering

Occurs before rendering each bubble. Using the following arguments, you can customize bubbles.

|   Argument name      |   Description                       |
|----------------------| ------------------------------------|
|      Border          |   Bubble's border      |
|      Cancel          |   Cancels rendering the bubble   |
|      Cx              |   Center x of current bubble           |
|      Cy              |   Center y of current bubble           |
|      Data            |   Current bubble data               |
|      Fill            |   Fills color for bubble      |
|      Radius          |   Current bubble radius             |
|      Name            |   Name of the event     |

### DataLabelRendering

Occurs before rendering each data label. Using the following arguments, you can customize the labels.

|   Argument name      |   Description                                     |
|----------------------| --------------------------------------------------|
|     Border           |    Configures the label border                    |
|     Cancel           |    Defines the event cancel status   |
|     Name             |    Name of the event     |
|     Datalabel        |    Label instance                |
|     Fill             |    Specifies label fill color |
|     Template         |    Specifies the template of data label, and you can customize it   |
|     Text             |    Specifies the data label text, and you can customize it |

### LayerRendering

Occurs before rendering each layer. Using the following arguments, you can customize the layers.

|   Argument name      |   Description                                     |
|----------------------| --------------------------------------------------|
|     Index            |    Specifies the current layer index   |
|     Cancel           |    Cancels the rendering of the current layer by setting it to true   |
|     Name             |    Name of the event                  |

### Loaded

Occurs after the maps component has been loaded.

### MarkerRendering

Occurs before rendering each marker. Using the following arguments, you can customize the marker.

|   Argument name      |   Description                                       |
|----------------------| ----------------------------------------------------|
|     Cancel           |    Cancels the rendering of the current marker by setting it to true |
|     Fill             |    Specifies the color of the legend    |
|     Height           |    Specifies the height of legend  |
|     Width            |    Specifies the width of legend |
|     Name             |    Defines the name of the event                    |
|     Shape            |    Defines the shape of legend            |
|     ImageUrl         |    Defines the image for legend                |
|     Data             |    Defines the data of legend                 |
|     Border           |    Defines border for legend                 |

### OnBubbleClick

Occurs after clicking the maps bubble element.

|   Argument name      |   Description                                       |
|----------------------| ----------------------------------------------------|
|     Data             |    Bubble's current data|
|     Cancel           |    Defines the event cancel status   |
|     Name             |    Name of the event     |
|     Target           |    Specifies current mouse event target id            |
|     X                |    Specifies current mouse x location                 |
|     Y                |    Specifies current mouse y location                 |

### OnBubbleMouseMove

Occurs when moving the cursor on the bubble element of the maps.

|   Argument name      |   Description                                       |
|----------------------| ----------------------------------------------------|
|     Data             |    Bubble current data event argument               |
|     Cancel           |    Defines the event cancel status   |
|     Name             |    Name of the event     |
|     Target           |    Specifies current mouse event target id            |
|     X                |    Specifies current mouse x location                 |
|     Y                |    Specifies current mouse y location                 |

### OnClick

Occurs after clicking the maps.

|   Argument name      |   Description                                       |
|----------------------| ----------------------------------------------------|
|     Latitude         |    Specifies current latitude value of maps location  |
|     Name             |    Defines the name of the Event                    |
|     Longitude        |    Specifies current longitude value of maps location |
|     Target           |    Specifies current mouse event target id            |
|     X                |    Specifies current mouse x location                 |
|     Y                |    Specifies current mouse y location                 |

### OnMarkerClick

Occurs by clicking an element of the maps marker.

|   Argument name      |   Description                                       |
|----------------------| ----------------------------------------------------|
|     Latitude         |    Defines current latitude value of maps location  |
|     Longitude        |    Defines current longitude value of maps location |
|     Name             |    Defines the name of the Event  |
|     Data             |    Defines the data for the marker |
|     Target           |    Defines current mouse event target id            |
|     X                |    Defines current mouse x location                 |
|     Y                |    Defines current mouse y location                 |

### OnMarkerClusterClick

Occurs by clicking an element of the maps marker-cluster.

|   Argument name      |   Description                                       |
|----------------------| ----------------------------------------------------|
|     Latitude         |    Defines current latitude value of maps location  |
|     Longitude        |    Defines current longitude value of maps location |
|     Name             |    Defines the name of the Event                    |
|     Data             |    Defines the data for the markerCluster           |
|     Target           |    Defines current mouse event target id            |
|     X                |    Defines current mouse x location                 |
|     Y                |    Defines current mouse y location                 |

### OnMarkerClusterMouseMove

Occurs on cursor moving on the maps cluster element.

|   Argument name      |   Description                                       |
|----------------------| ----------------------------------------------------|
|     Data             |    Bubble current data event argument               |
|     Name             |    Defines the name of the Event                    |
|     Latitude         |    Defines current latitude value of maps location  |
|     Longitude        |    Defines current longitude value of maps location |
|     Target           |    Defines current mouse event target id            |
|     X                |    Defines current mouse x location                 |
|     Y                |    Defines current mouse y location                 |

### OnItemHighlight

Occurs when cursor move over the shapes. You can customize the highlight option as it triggers before the item is highlighted.

|   Argument name      |   Description                                     |
|----------------------| --------------------------------------------------|
|     Border           |    Configures selection border                |
|     Data             |    Data from the datasource                       |
|     Cancel           |    Defines the event cancel status   |
|     Name             |    Name of the event     |
|     Fill             |    Configures the shape fill color                 |
|     Opacity          |    Defines the color opacity                       |
|     Target           |    Defines current mouse event target id          |

### OnItemSelection

Occurs when selecting a shape. As it triggers before the selection changes are applied, you can customize the selection option.

|   Argument name      |   Description                                     |
|----------------------| --------------------------------------------------|
|     Border           |    Configures selection border                |
|     Data             |    Data from the datasource                       |
|     Cancel           |    Defines the event cancel status   |
|     Name             |    Name of the event     |
|     Fill             |    Configures the shape fill color                 |
|     Opacity          |    Defines the color opacity                       |
|     Target           |    Defines current mouse event target id          |

### OnMarkerMouseMove

Occurs when the cursor moves over the marker element of the maps.

|   Argument name      |   Description                                       |
|----------------------| ----------------------------------------------------|
|     Data             |    Bubble current data event argument               |
|     Name             |    Defines the name of the Event                    |
|     Latitude         |    Defines current latitude value of maps location  |
|     Longitude        |    Defines current longitude value of maps location |
|     Target           |    Defines current mouse event target id            |
|     X                |    Defines current mouse x location                 |
|     Y                |    Defines current mouse y location                 |

### OnLoad

Occurs before rendering the maps. Maps will trigger this event at first.

### OnPan

Occurs when you pan the maps.

|   Argument name       |   Description                                     |
|-----------------------| --------------------------------------------------|
|     Scale             |    Geometry layer scale                           |
|     Cancel           |    Defines the event cancel status   |
|     Name             |    Name of the event     |
|     TileTranslatePoint|    Tile translate point                           |
|     TileZoomLevel     |    Defines the Zoom level                          |
|     TranslatePoint    |    Geometry translate point                       |

### OnPrint

Occurs before the print operation is started.

### Resizing

Occurs when you resize the maps.

|   Argument name      |   Description                                     |
|----------------------| --------------------------------------------------|
|     CurrentSize      |    Defines the current size of the maps           |
|     PreviousSize     |    Defines the previous size of the maps          |
|     Cancel           |    Defines the event cancel status                |
|     Name             |    Name of the event                              |

### OnZoom

Occurs before zooming in or zooming out the maps.

|   Argument name       |   Description                                     |
|-----------------------| --------------------------------------------------|
|     Scale             |    Geometry layer scale.                          |
|     Cancel           |    Defines the event cancel status   |
|     Name             |    Name of the event     |
|     TileTranslatePoint|    Tile translate point.                           |
|     TileZoomLevel     |    Defines the Zoom level                           |
|     TranslatePoint    |    Geometry translate point.                       |
|     Type              |    Type of zoom interaction                        |

### ShapeHighlighted

Occurs before applying highlight option to shapes.

### ShapeRendering

Occurs before rendering a shape of the maps.

|   Argument name      |   Description                                          |
|----------------------| -------------------------------------------------------|
|     Border           |    Configures the shape border                         |
|     Cancel           |    Defines the event cancel status                     |
|     Data             |    Data from the datasource                            |
|     Fill             |    Configures the shape fill color                      |
|     Name             |    Defines the name of the event                       |
|     Index            |    Defines the shape index                              |

### ShapeSelected

Occurs when selecting a shape.

|   Argument name      |   Description                                          |
|----------------------| -------------------------------------------------------|
|     Border           |    Configures the shape border                         |
|     Cancel           |    Defines the event cancel status                     |
|     Data             |    Data from the datasource                            |
|     Fill             |    Configures the shape fill color                      |
|     Opacity          |    Defines the opacity of color                         |
|     Name             |    Defines the name of the event                      |
|     ShapeData        |    ShapeData event argument                           |
|     Target           |    Defines current mouse event target id               |