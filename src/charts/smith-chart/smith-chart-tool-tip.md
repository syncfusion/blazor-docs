# Tooltip

Smith Chart will display details about the points through tooltip, when the mouse is moved over the point. By default, tooltip is disabled. To enable the tooltip, set the property `Visible` as true, in `SmithchartSeriesTooltip`. You can customize the tooltip's visibility and appearance differently each series in the Smith Chart.

```csharp
<SfSmithchart>
    <SmithchartSeriesCollection>
        <SmithchartSeries Name="First transmission" Points='FirstTransmissionData'>
            <SmithchartSeriesMarker Visible='true'></SmithchartSeriesMarker>
            <SmithchartSeriesTooltip Visible='true'></SmithchartSeriesTooltip>
        </SmithchartSeries>
    </SmithchartSeriesCollection>
</SfSmithchart>

@code {
    public class SmithDataSource
    {
        public double? resistance;
        public double? reactance;
    };
    private List<SmithDataSource> FirstTransmissionData = new List<SmithDataSource> {
        new SmithDataSource { resistance= 10, reactance= 25 },
        new SmithDataSource { resistance= 6, reactance= 4.5 },
        new SmithDataSource { resistance= 3.5, reactance= 1.6 },
        new SmithDataSource { resistance= 2, reactance= 1.2 },
        new SmithDataSource { resistance= 1, reactance= 0.8 },
        new SmithDataSource { resistance= 0, reactance= 0.2 }
    };
}
```

![Smith chart with tooltip](./images/Tooltip/Tooltip.png)
