---
title: "Slider Formatting"
component: "Slider"
description: "Slider supports formatting to customize slider values like time, currency & km, values, also displayed in ticks & tooltip."
---

# Formatting

The `Format` feature used to customize the units of Slider values to desired format. The formatted values will also be applied to the ARIA attributes of the slider. There are two ways of achieving formatting in slider.

>Use the `Format` API of slider which utilizes our Internationalization to format values.

```csharp
@using Syncfusion.Blazor.Inputs

<SfSlider Value="30">
    <SliderTooltipData IsVisible="true" ShowOn="TooltipShowOn.Always" Format="C2" Placement="TooltipPlacement.Before"></SliderTooltipData>
    <SliderTicksData Placement="Placement.Before" Format="C2" ShowSmallTicks="true" LargeStep="20" SmallStep="10"></SliderTicksData>
</SfSlider>
```

![Blazor - Slider - Format](images/slider-format.gif)

## Using format API

Slider provides different predefined formatting styles like Numeric (N), Percentage (P), Currency (C) and # specifiers. In this below example we have formatted the ticks and tooltip values into percentage.

```csharp
@using Syncfusion.Blazor.Inputs

<SfSlider Min="1" Max="10" Value="3">
    <SliderTicksData Placement="Placement.After" Format="P0" ShowSmallTicks="true" LargeStep="2" SmallStep="1"></SliderTicksData>
    <SliderTooltipData IsVisible="true" ShowOn="TooltipShowOn.Always" Format="P0" Placement="TooltipPlacement.Before"></SliderTooltipData>
</SfSlider>
```

![Blazor - Slider - Format API](images/slider-format-api.gif)
