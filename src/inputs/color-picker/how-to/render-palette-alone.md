# Render palette alone

To render the `Palette` alone in Color Picker, specify the [`Mode`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Inputs.SfColorPicker~Mode.html) property as `Palette`, and set the [`ModeSwitcher`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Inputs.SfColorPicker~ModeSwitcher.html) property to `false`.

In the following sample, the [`ShowButtons`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Inputs.SfColorPicker~ShowButtons.html) property is set to `false` to hide the control buttons and it renders only the `Palette` area.

```csharp
@using Syncfusion.Blazor.Inputs

<h4>Choose a color</h4>
<SfColorPicker Mode="ColorPickerMode.Palette" ModeSwitcher="false" ShowButtons="false"></SfColorPicker>
```

Output be like
![color-picker](./../images/palette-alone.png)

> To render `Picker` alone, specify the [`Mode`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Inputs.SfColorPicker~Mode.html) property as 'Picker'.