---
title: "Customization in Blazor Progress Bar component | Syncfusion"

component: "Progress Bar"

description: "Learn here all about Customization of Syncfusion Progress Bar (SfProgressBar) component and more."
---

# Customization in Blazor Progress Bar (SfProgressBar)

## Segments

Divide a Progress Bar into multiple segments by setting the [`SegmentCount`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.SfProgressBar.html#Syncfusion_Blazor_ProgressBar_SfProgressBar_SegmentCount) property to visualize the progress for multiple sequential tasks and [`EnableProgressSegments`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.SfProgressBar.html#Syncfusion_Blazor_ProgressBar_SfProgressBar_EnableProgressSegments) property divide the progress  into multiple segments without the track.

[`SegmentColor`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.SfProgressBar.html#Syncfusion_Blazor_ProgressBar_SfProgressBar_SegmentColor) property represents the color of the each segment.

```csharp
@using Syncfusion.Blazor.ProgressBar

<SfProgressBar Type="ProgressType.Circular" Value="100" Height="180" SegmentCount="8" SegmentColor='new string[] { "#00bdaf", "#2f7ecc", "#e9648e", "#fbb78a" }' Minimum="0" Maximum="100" TrackColor="#696969">
</SfProgressBar>

<SfProgressBar Type="ProgressType.Circular" EnableProgressSegments="true" Value="100" Height="180" SegmentColor='new string[] { "#00bdaf", "#2f7ecc", "#e9648e", "#fbb78a" }' SegmentCount="8" Minimum="0" Maximum="100" TrackColor="#696969">
</SfProgressBar>
```

![Progress Bar with segments](images/segment.png)

## Thickness

Customize the thickness of the track using [`TrackThickness`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.SfProgressBar.html#Syncfusion_Blazor_ProgressBar_SfProgressBar_TrackThickness) property and the progress using [`ProgressThickness`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.SfProgressBar.html#Syncfusion_Blazor_ProgressBar_SfProgressBar_ProgressThickness) property to render the Progress Bar with different appearances.

 ```csharp
 @using Syncfusion.Blazor.ProgressBar

<SfProgressBar Type="ProgressType.Linear" Value="100" Height="60" Width="90%" TrackThickness="24" ProgressThickness="24" ShowProgressValue="true" Minimum="0" Maximum="100">
</SfProgressBar>
```

![Progress Bar with thickness](images/thickness.png)

## Radius

The  radius of the Progress Bar can be customized using [`Radius`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.SfProgressBar.html#Syncfusion_Blazor_ProgressBar_SfProgressBar_Radius) property and the progress edges can be customized by [`CornerRadius`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.SfProgressBar.html#Syncfusion_Blazor_ProgressBar_SfProgressBar_CornerRadius) property.

```csharp
@using Syncfusion.Blazor.ProgressBar

<SfProgressBar Type="ProgressType.Circular" Value="60" Height="160px" Width="160px" EnableRtl="false" TrackColor="#FFD939" Radius="100%" InnerRadius="190%" ProgressColor="white" TrackThickness="80" ProgressThickness="10" CornerRadius="CornerType.Round" Minimum="0" Maximum="100">
</SfProgressBar>
```

![Progress Bar with radius](images/radius.png)

## InnerRadius

The inner radius of the Progress Bar can be customized using [`InnerRadius`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.SfProgressBar.html#Syncfusion_Blazor_ProgressBar_SfProgressBar_InnerRadius) property.

```csharp
@using Syncfusion.Blazor.ProgressBar

<SfProgressBar Type="ProgressType.Circular" Value="60" Height="160px" Width="160px" EnableRtl="false"
                TrackColor="#FFD939" Radius="100%" InnerRadius="190%" ProgressColor="white" TrackThickness="80" ProgressThickness="10" CornerRadius="CornerType.Round" Minimum="0" Maximum="100">
</SfProgressBar>
```

![Progress Bar with inner radius](images/innerRadius.png)

## Progress Color and Track Color

Customize the color of progress and track by using  [`ProgressColor`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.SfProgressBar.html#Syncfusion_Blazor_ProgressBar_SfProgressBar_ProgressColor) and [`TrackColor`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.SfProgressBar.html#Syncfusion_Blazor_ProgressBar_SfProgressBar_TrackColor) properties.

```csharp
@using Syncfusion.Blazor.ProgressBar

<SfProgressBar Type="ProgressType.Linear" Value="50" Height="60" Width="90%" TrackColor="#F8C7D8"
        ShowProgressValue="true" InnerRadius="190%" ProgressColor="#E3165B" TrackThickness="24" CornerRadius="CornerType.Round"
        ProgressThickness="24" Minimum="0" Maximum="100">
</SfProgressBar>
```

![Progress Bar with color](images/trackThickness.png)

## Range Colors

Enhance the readability of progress by visualising the multiple ranges with different colors, that are mapped to each range. Colors can be mapped to the specific ranges using the [`ProgressBarRangeColors`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.ProgressBarRangeColors.html), which holds a collection of [`ProgressBarRangeColor`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.ProgressBarRangeColor.html).

The [`Color`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.ProgressBarRangeColor.html#Syncfusion_Blazor_ProgressBar_ProgressBarRangeColor_Color) property represents the color to the specified range, [`Start`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.ProgressBarRangeColor.html#Syncfusion_Blazor_ProgressBar_ProgressBarRangeColor_Start) and [`End`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.ProgressBarRangeColor.html#Syncfusion_Blazor_ProgressBar_ProgressBarRangeColor_End) property represents start and end range of the color and  the [`IsGradient`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.SfProgressBar.html#Syncfusion_Blazor_ProgressBar_SfProgressBar_IsGradient) property represents whether the gradient effect is applied to the color.

```csharp
@using Syncfusion.Blazor.ProgressBar

<SfProgressBar Value="100" IsGradient="true">
    <ProgressBarRangeColors>
        <ProgressBarRangeColor Start="0" End="25" Color="#00bdaf"></ProgressBarRangeColor>
        <ProgressBarRangeColor Start="25" End="50" Color="#2f7ecc"></ProgressBarRangeColor>
        <ProgressBarRangeColor Start="50" End="75" Color="#e9648e"></ProgressBarRangeColor>
        <ProgressBarRangeColor Start="75" End="100" Color="#fbb78a"></ProgressBarRangeColor>
    </ProgressBarRangeColors>
</SfProgressBar>
```

![Progress Bar with range colors](images/range-colors.png)

## RTL

Progress Bar support, right to left rendering direction and it can be enabled by setting the [`EnableRtl`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.SfProgressBar.html#Syncfusion_Blazor_ProgressBar_SfProgressBar_EnableRtl) property to **true**.

```csharp
@using Syncfusion.Blazor.ProgressBar

<SfProgressBar EnableRtl="true" Value="50" Type="ProgressType.Linear">
</SfProgressBar>

<SfProgressBar EnableRtl="true" Value="80" Type="ProgressType.Circular">
</SfProgressBar>
```

![Progress Bar with RTL](images/rtl.png)
