---
title: "Range Band in Blazor Sparkline component | Syncfusion"

component: "Sparkline"

description: "Learn here all about Range Band of Syncfusion Sparkline (SfSparkline) component and more."
---

# Range Band in Blazor Sparkline (SfSparkline)

Range band represents the quality or makes better readability of a specific range for Sparkline y-axis using [`StartRange`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SparklineRangeBand.html#Syncfusion_Blazor_Charts_SparklineRangeBand_StartRange) and [`EndRange`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SparklineRangeBand.html#Syncfusion_Blazor_Charts_SparklineRangeBand_EndRange) properties in [`SparklineRangeBand`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SparklineRangeBand.html) to specifies in [`SparklineRangeBandSettings`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SparklineRangeBandSettings.html) which hold the collection of [`SparklineRangeBand`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SparklineRangeBand.html).

The following properties are used to customization the range band:

* [`Color`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SparklineRangeBand.html#Syncfusion_Blazor_Charts_SparklineRangeBand_Color) - Specifies the color of range band.
* [`Opacity`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SparklineRangeBand.html#Syncfusion_Blazor_Charts_SparklineRangeBand_Opacity) - Specifies the opacity of [`Color`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SparklineRangeBand.html#Syncfusion_Blazor_Charts_SparklineRangeBand_Color) in range band.

```csharp
@using Syncfusion.Blazor.Charts

<SfSparkline DataSource="new int[]{ 0, 6, 4, 1, 3, 2, 5 }" Height="150px" Width="150px" LineWidth="2" Fill="#0d3c9b">
    <SparklineAxisSettings MinX="-1" MaxX="7" MaxY="7" MinY="-1">
    </SparklineAxisSettings>
    <SparklineRangeBandSettings>
        <SparklineRangeBand StartRange="1" EndRange="2" Color="#bfd4fc" Opacity="0.4">
        </SparklineRangeBand>
        <SparklineRangeBand StartRange="4" EndRange="5" Color="red" Opacity="0.4">
        </SparklineRangeBand>
    </SparklineRangeBandSettings>
</SfSparkline>
```

![Sparkline Charts with multiple range band](./images/rangeband/MultipleRangeBand.png)
