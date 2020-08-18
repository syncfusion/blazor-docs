# Layers

The Maps component is maintained through [`layers`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Maps.MapsLayer_members.html), and it can accommodate one or more layers.

## Sublayer

Sublayer in the maps component allows to load multiple shape files in a single map view. For example, add a sublayer over a main shape layer to view geographic features such as rivers, valleys, and cities in a map of a country.

In this example, the United States map shape is used as shape data by utilizing the `USA.json` file, and the `texas.json` and `california.json` files are used as sub layers in the United States map.

```csharp
@using Syncfusion.Blazor.Maps

<SfMaps>
    <MapsLayers>
        <MapsLayer ShapeData='new {dataOptions ="https://cdn.syncfusion.com/maps/map-data/usa.json"}'>
            <MapsShapeSettings Fill="#E5E5E5">
                <MapsShapeBorder Color="black" Width="0.1"></MapsShapeBorder>
            </MapsShapeSettings>
        </MapsLayer>
        <MapsLayer ShapeData='new {dataOptions = "https://cdn.syncfusion.com/maps/map-data/texas.json"}' Type="Syncfusion.Blazor.Maps.Type.SubLayer">
            <MapsShapeSettings Fill="rgba(141, 206, 255, 0.6)">
                <MapsShapeBorder Color="#1a9cff" Width="0.25"></MapsShapeBorder>
            </MapsShapeSettings>
        </MapsLayer>
        <MapsLayer ShapeData='new {dataOptions= "https://cdn.syncfusion.com/maps/map-data/california.json"}' Type="Syncfusion.Blazor.Maps.Type.SubLayer">
            <MapsShapeSettings Fill="rgba(141, 206, 255, 0.6)">
                <MapsShapeBorder Color="#1a9cff" Width="0.25"></MapsShapeBorder>
            </MapsShapeSettings>
        </MapsLayer>
    </MapsLayers>
</SfMaps>
```

![Maps with sublayer](./images/Layers/layers.png)

> Sublayer is a type of shape file layer. You can add all the elements such as markers, bubbles, color mapping, and legends to sublayer.

## Displaying layer in the view

In Maps, you can load multiple shape files. Using the [`BaseLayerIndex`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Base~LoadCldrData.html) property, you can select a layer to display on user interface.

In this example, we have loaded two layers with the World map and the United States map shape data and selected a layer using the `BaseLayerIndex` property to show that layer on the web page.

```csharp
@using Syncfusion.Blazor.Maps

@*  To switch the layer, set `BaseLayerIndex`  *@
<SfMaps BaseLayerIndex="1">
    <MapsLayers>
        <MapsLayer ShapeData='new { dataOptions = "https://cdn.syncfusion.com/maps/map-data/world-map.json" }'>
        </MapsLayer>
        <MapsLayer ShapeData='new { dataOptions = "https://cdn.syncfusion.com/maps/map-data/usa.json" }'>
        </MapsLayer>
    </MapsLayers>
</SfMaps>
```

![Maps with multiple layer](./images/Layers/multi-layer.png)

If you set the [`BaseLayerIndex`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Base~LoadCldrData.html) value to 0, the world map will be loaded.

This concept is used in the Maps drill-down feature, so the corresponding shape will be loaded when clicking a shape of the maps.

> Note: The Maps component will render even [`ShapeData`](https://help.syncfusion.com/cr/blazor/Syncfusion.EJ2.Blazor~Syncfusion.EJ2.Blazor.Maps.MapsLayer~ShapeData.html) only is set in [`MapsLayer`](https://help.syncfusion.com/cr/blazor/Syncfusion.EJ2.Blazor~Syncfusion.EJ2.Blazor.Maps.MapsLayer_members.html). The [`LayerType`](https://help.syncfusion.com/cr/blazor/Syncfusion.EJ2.Blazor~Syncfusion.EJ2.Blazor.Maps.MapsLayer~LayerType.html) will be set Geometry by default. If we set `LayerType` other than Geometry type and `ShapeData` in the `MapsLayer`, the Maps will be rendered based on the provided `LayerType`. It will not consider the `ShapeData` as the `LayerType` is not Geometry type.

Consider we want to view Bing map. If we set `ShapeData` and [`BingMapType`](https://help.syncfusion.com/cr/blazor/Syncfusion.EJ2.Blazor~Syncfusion.EJ2.Blazor.Maps.MapsLayer~BingMapType.html) in the MapsLayer but missed to set LayerType, the Maps component will consider the `LayerType` as Geometry and render the map based on the provided ShapeType.

## See also

* [Display geometry shapes in Bing maps](how-to/display-geometry-shapes-in-bing-maps)
