---
title: "Appearance in Blazor Sparkline component | Syncfusion"

component: "Sparkline"

description: "Learn here all about Appearance of Syncfusion Sparkline (SfSparkline) component and more."
---

# Appearance in Blazor Sparkline (SfSparkline)

The Sparkline rendering direction, padding, border and background appearance can be customized.

## RTL

Sparkline support, right to left rendering direction and it can be enabled by setting the [`EnableRtl`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SfSparkline-1.html#Syncfusion_Blazor_Charts_SfSparkline_1_EnableRtl) property to **true**.

```csharp
@using Syncfusion.Blazor.Charts

<SfSparkline DataSource="new double[]{ 300.00, 600.00, 400.21, 100.20, 300.70, 200.04, 500.00 }" Height="200px" Width="350px" Format="c2" EnableRtl="true">
    <SparklineDataLabelSettings Visible="new List<VisibleType> { VisibleType.All }" EdgeLabelMode="EdgeLabelMode.Shift"></SparklineDataLabelSettings>
    <SparklinePadding Top="25"></SparklinePadding>
</SfSparkline>
```

![Sparkline with RTL](/images/Appearance/Rtl.png)

## Border

The border can be enabled by specifying in [`Color`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.BorderSettings.html#Syncfusion_Blazor_Charts_BorderSettings_Color)
 and [`Width`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.BorderSettings.html#Syncfusion_Blazor_Charts_BorderSettings_Width) properties of [`SparklineContainerAreaBorder`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.SparklineContainerAreaBorder.html).

The following code example shows the Sparkline Charts with overall border.

```csharp
@using Syncfusion.Blazor.Charts

<SfSparkline DataSource="new int[]{ 3, 6, 4, 1, 3, 2, 5 }" Type="SparklineType.Area" Height="200px" Width="350px" Fill="#b2cfff" LineWidth="1">
    <SparklineContainerArea>
        <SparklineContainerAreaBorder Color="#033e96" Width="1"></SparklineContainerAreaBorder>
    </SparklineContainerArea>
</SfSparkline>
```

![Sparkline with border](/images/Appearance/border.png)

## Padding

Sparkline supports the padding between container and bottom, left, right, top padding of the Sparkline to be customized by setting in [`SparklinePadding`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SparklinePadding.html).

The following code example shows the Sparkline Charts with overall padding is set to 20.

```csharp
@using Syncfusion.Blazor.Charts

<SfSparkline DataSource="new int[]{ 3, 6, 4, 1, 3, 2, 5 }" Type="SparklineType.Area" Height="200px" Width="350px" Fill="#b2cfff" LineWidth="1">
    <SparklineContainerArea>
        <SparklineContainerAreaBorder Color="#033e96" Width="2"></SparklineContainerAreaBorder>
    </SparklineContainerArea>
    <SparklineBorder Color="#033e96" Width="1"></SparklineBorder>
    <SparklinePadding Left="20" Right="20" Bottom="20" Top="20"></SparklinePadding>
</SfSparkline>
```

![Sparkline with padding](/images/Appearance/Padding.png)

## Sparkline area customization

The background color of the Sparkline area can be customized using the [`Background`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SparklineContainerArea.html#Syncfusion_Blazor_Charts_SparklineContainerArea_Background) property in [`SparklineContainerArea`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SparklineContainerArea.html). By default, the Sparkline background color is **Transparent**.

```csharp
@using Syncfusion.Blazor.Charts

<SfSparkline DataSource="new int[]{ 3, 6, 4, 1, 3, 2, 5 }" Type="SparklineType.Area" Height="200px" Width="350px" Fill="#b2cfff" LineWidth="1">
    <SparklineContainerArea Background="#eff1f4">
        <SparklineContainerAreaBorder Color="#033e96" Width="2">
        </SparklineContainerAreaBorder>
    </SparklineContainerArea>
    <SparklineBorder Color="#033e96" Width="1"></SparklineBorder>
    <SparklinePadding Left="20" Right="20" Bottom="20" Top="20"></SparklinePadding>
</SfSparkline>
```

![Sparkline with background](/images/Appearance/ContainerBackground.png)
