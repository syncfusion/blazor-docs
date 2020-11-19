# Range Band

This section explains how to customize the Sparkline Charts with multiple range bands.

## Range band customization

The range band feature is used to highlight a particular range along with the y-axis using the [`StartRange`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.SparklineRangeBand~StartRange.html) and [`EndRange`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.SparklineRangeBand~EndRange.html) properties. You can also customize the [`Color`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.SparklineRangeBand~Color.html) and [`Opacity`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.SparklineRangeBand~Opacity.html) of the range band.

```csharp
@using Syncfusion.Blazor.Charts

<SfSparkline DataSource="new int[]{ 0, 6, 4, 1, 3, 2, 5 }"
              Height="150px"
              Width="150px"
              LineWidth="2"
              Fill="#0d3c9b">
    <SparklineAxisSettings MinX="-1" MaxX="7" MaxY="7" MinY="-1">
    </SparklineAxisSettings>
    <SparklineRangeBandSettings>
        <SparklineRangeBand StartRange="1" EndRange="3" Color="#bfd4fc" Opacity="0.4">
        </SparklineRangeBand>
    </SparklineRangeBandSettings>
</SfSparkline>
```

![Sparkline Charts with range band](./images/rangeband/RangeBand.png)

## Multiple range band customization

You can define multiple range bands to a Sparkline Chart as demonstrated in the following code sample.

```csharp
@using Syncfusion.Blazor.Charts

<SfSparkline DataSource="new int[]{ 0, 6, 4, 1, 3, 2, 5 }"
              Height="150px"
              Width="150px"
              LineWidth="2"
              Fill="#0d3c9b">
    <SparklineAxisSettings MinX="-1" MaxX="7" MaxY="7" MinY="-1"></SparklineAxisSettings>
    <SparklineRangeBandSettings>
        <SparklineRangeBand StartRange="1" EndRange="2" Color="#bfd4fc" Opacity="0.4">
        </SparklineRangeBand>
        <SparklineRangeBand StartRange="4" EndRange="5" Color="red" Opacity="0.4">
        </SparklineRangeBand>
    </SparklineRangeBandSettings>
</SfSparkline>
```

![Sparkline Charts with multiple range band](./images/rangeband/MultipleRangeBand.png)
