# Appearance

The appearance of the Sparkline Charts can be customized using margin, container area border, and container area background.

## Sparkline border

The [`SparklineContainerAreaBorder`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.SparklineContainerAreaBorder.html) of the Sparkline Charts is used to render border to cover the Sparkline Charts area.

The following code example shows the Sparkline Charts with overall border.

```csharp
@using Syncfusion.Blazor.Charts

<SfSparkline DataSource="new int[]{ 3, 6, 4, 1, 3, 2, 5 }"
              Type="SparklineType.Area"
              Height="200px"
              Width="350px"
              Fill="#b2cfff"
              Linewidth="1">
    <SparklineContainerArea>
        <SparklineContainerAreaBorder Color="#033e96" Width="1" ></SparklineContainerAreaBorder>
    </SparklineContainerArea>
</SfSparkline>
```

![Sparkline Charts with border](./images/Appearance/border.png)

## Sparkline padding

Padding is used to specify padding value between container and Sparkline Charts. By default, padding value of the Sparkline Charts is 5. The [`Padding`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.SparklinePadding.html) values of Sparkline Charts are specified by the left, right, top, and bottom.

The following code example shows the Sparkline Charts with overall padding is set to 20.

```csharp
@using Syncfusion.Blazor.Charts

<SfSparkline DataSource="new int[]{ 3, 6, 4, 1, 3, 2, 5 }"
              Type="SparklineType.Area"
              Height="200px"
              Width="350px"
              Fill="#b2cfff"
              Linewidth="1">
    <SparklineContainerArea>
        <SparklineContainerAreaBorder Color="#033e96" Width="2"></SparklineContainerAreaBorder>
    </SparklineContainerArea>
    <SparklineBorder Color="#033e96" Width="1px"></SparklineBorder>
    <SparklinePadding Left="20" Right="20" Bottom="20" Top="20"></SparklinePadding>
</SfSparkline>
```

![Sparkline Charts border with Color](./images/Appearance/Padding.png)

## Sparkline area customization

The background color of the Sparkline Charts area can be customized using the [`SparklineContainerArea Background`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.SparklineContainerArea~Background.html) color. By default, the Sparkline Charts background color is `Transparent`.

```csharp
@using Syncfusion.Blazor.Charts

<SfSparkline DataSource="new int[]{ 3, 6, 4, 1, 3, 2, 5 }"
              Type="SparklineType.Area"
              Height="200px"
              Width="350px"
              Fill="#b2cfff"
              Linewidth="1">
    <SparklineContainerArea Background="#eff1f4">
        <SparklineContainerAreaBorder Color="#033e96" Width="2">
        </SparklineContainerAreaBorder>
    </SparklineContainerArea>
    <SparklineBorder Color="#033e96" Width="1px"></SparklineBorder>
    <SparklinePadding Left="20" Right="20" Bottom="20" Top="20"></SparklinePadding>
</SfSparkline>
```

![Sparkline Charts border width customization](./images/Appearance/ContainerBackground.png)
