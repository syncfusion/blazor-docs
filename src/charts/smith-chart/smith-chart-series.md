# Series customization

Using following options in `SmithchartSeries`, you can customize each series in Smith Chart as per your requirement.

* `Fill` - Used to customize the fill color for the series.
* `EnableSmartLabels` - Used to place the data labels on the Smith Chart without overlapping with each other.
* `Visibility` - Used to handle the visibility of the series.
* `Opacity` - Used to control the opacity of the series line.
* `Width` - Used to customize the width of the series line.

```csharp
<SfSmithchart>
    <SmithchartSeriesCollection>
        <SmithchartSeries
            Points='FirstTransmissionData'
            Fill="#009933"
            Visibility="visible"
            Opacity="0.75"
            Width="2.5">
            <SmithchartSeriesMarker Visible='true'>
                <SmithchartSeriesMarkerDataLabel Visible='true'></SmithchartSeriesMarkerDataLabel>
            </SmithchartSeriesMarker>
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

![Smith chart with series customization](./images/SmithChartSeries/SeriesCustomization.png)