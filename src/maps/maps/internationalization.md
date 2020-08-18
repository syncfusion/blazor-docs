# Internationalization

Maps provides support for internationalization for the below elements.

* Datalabel
* Tooltip

## Globalization

Globalization is the process of designing and developing an component that works in different
cultures/locales. Internationalization library is used to globalize number, date, time values in
Maps component using `LoadCldrData` method.

## Numeric Format

In the below example tooltip is globalized to Deutsch culture.

```csharp
<SfMaps>
    <MapsLayers>
        <MapsLayer ShapeData='MapShapeData'
            DataSource='CountryData' Format="c"
            ShapePropertyPath="name"
            ShapeDataPath="Country">
            <MapsShapeSettings Fill="#E5E5E5" colorValuePath="Membership">
                <MapsColorMappings>
                    <MapsColorMapping Value="Permanent" Color="#D84444"/>
                    <MapsColorMapping Value="Non-Permanent" Color="#316DB5"/>
                </MapsColorMappings>
            </MapsShapeSettings>
            <LayerTooltipSettings Visible="true" ValuePath="Population"></LayerTooltipSettings>
        </MapsLayer>
    </MapsLayers>
    <MapsLegendSettings Visible="true"></MapsLegendSettings>
</SfMaps>

@code {
    public class MapDataSettings
    {
        public Boolean async{ get; set; }
        public String dataOptions { get; set; }
        public String type { get; set; }
    };
    private MapDataSettings MapShapeData = new MapDataSettings{
        async= true,
        dataOptions= "scripts/map-data/world-map.json",
        type= "GET"
    };
    public class MapDataSource {
        public string Country;
        public string Membership;
    };
    public List<MapDataSource> CountryData = new List<MapDataSource>{
         new MapDataSource {  Country= "China", Membership= "Permanent", Population="20"},
         new MapDataSource { Country= "France",Membership= "Permanent", Population="30" },
         new MapDataSource { Country= "Russia",Membership= "Permanent", Population="40"},
         new MapDataSource { Country= "Kazakhstan",Membership= "Non-Permanent", Population="50"},
         new MapDataSource { Country= "Poland",Membership= "Non-Permanent", Population="60"},
         new MapDataSource { Country= "Sweden",Membership= "Non-Permanent", Population="70"}
    };
     [Inject]
    protected IJSRuntime JsRuntime { get; set; }
    protected override void OnAfterRender()
    {
        this.JsRuntime.Sf().LoadCldrData(new string[]{"ca-gregorian.json",
        "currencies.json","numbers.json","timeZoneNames.json"}).SetCulture("de");
    }
}
```

![Maps Sample](./images/Internationalization/Internationalization.png)