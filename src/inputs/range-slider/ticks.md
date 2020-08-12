---
title: "Slider Ticks"
component: "Slider"
description: "Slider visually represents the slider values with small and large ticks placed before, after, or both, of the slider bar."
---

# Ticks

The Ticks in Slider supports you to easily identify the current value/values of the Slider. It contains `SmallStep` and `LargeStep`. The value of the major ticks alone will be displayed in the slider. In order to enable/disable the small ticks, use the `ShowSmallTicks` property.

```csharp
@using Syncfusion.Blazor.Inputs

<SfSlider Value="30">
    <SliderTicksData Placement="Placement.After" ShowSmallTicks="true" LargeStep="20" SmallStep="10"></SliderTicksData>
    <SliderTooltipData IsVisible="true" ShowOn="TooltipShowOn.Always" Placement="TooltipPlacement.Before"></SliderTooltipData>
</SfSlider>
```

![Blazor- Slider - Ticks](images/ticks.gif)

## Step

When the Slider is moved, it increases/decreases the value based on the step value. By default, the value is increased/decreased by 1. Use the `Step` property to change the increment step value.

```csharp
@using Syncfusion.Blazor.Inputs

<SfSlider Step="10" Value="30">
    <SliderTooltipData IsVisible="true" ShowOn="TooltipShowOn.Always" Placement="TooltipPlacement.Before"></SliderTooltipData>
</SfSlider>
```

![Blazor- Slider - Step](./images/step.gif)

## Min and Max

Enables the minimum/starting and maximum/ending value of the Slider, by using the `Min` and `Max` property. By default, the minimum value is 1 and maximum value is 100. In the following sample the slider is rendered with the min value as 100 and max value as 1100.

```csharp
@using Syncfusion.Blazor.Inputs

<SfSlider Value="300" Min="100" Max="1100">
    <SliderTicksData Placement="Placement.After" ShowSmallTicks="true" LargeStep="100" SmallStep="50"></SliderTicksData>
    <SliderTooltipData IsVisible="true" ShowOn="TooltipShowOn.Always" Placement="TooltipPlacement.Before"></SliderTooltipData>
</SfSlider>
```

![Blazor- Slider - Min and Max](./images/MinMax.gif)
