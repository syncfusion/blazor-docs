# Types and Icons

This section explains the different types and icons of Progress Button.

## Types

The types of Blazor Progress Button are as follows:

* Outline Progress Button
* Round Progress Button
* Primary Progress Button

### Outline Progress Button

An outline Progress Button has a border with transparent background. To create an outline Progress Button,
set the [`CssClass`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.SplitButtons.SfProgressButton.html#Syncfusion_Blazor_SplitButtons_SfProgressButton_CssClass) property to `e-outline`.

```csharp
@using Syncfusion.Blazor.SplitButtons

<SfProgressButton Content="Outline" EnableProgress="true" CssClass="e-outline e-success">
    <ProgressButtonSpinSettings Position="SpinPosition.Center"></ProgressButtonSpinSettings>
</SfProgressButton>
```

### Round Progress Button

A round Progress Button is shaped like a circle. Usually, it contains an icon representing its action. To create a round Progress Button,
set the [`CssClass`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.SplitButtons.SfProgressButton.html#Syncfusion_Blazor_SplitButtons_SfProgressButton_CssClass) property to `e-round`.

```csharp
@using Syncfusion.Blazor.SplitButtons

<SfProgressButton CssClass="e-round e-small e-success" IconCss="e-icons e-play-icon">
<ProgressButtonSpinSettings Position="SpinPosition.Center"></ProgressButtonSpinSettings>
</SfProgressButton>

<style>
    .e-play-icon::before {
        content: '\e324';
    }
</style>
```

### Primary Progress Button

The primary progress button is styled with background color and it is used to represent a primary action. To create a Primary Progress Button,
set the [`IsPrimary`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.SplitButtons.SfProgressButton.html#Syncfusion_Blazor_SplitButtons_SfProgressButton_IsPrimary) property to `true`.

```csharp
@using Syncfusion.Blazor.SplitButtons

<SfProgressButton Content="Primary" IsPrimary="true"></SfProgressButton>
```

Output be like

![Button Sample](./images/progress-button-types.png)

## Icons

### Progress Button with font icons

The Progress Button can have an icon to provide the visual representation of the action. To place the icon on a Progress Button, set the [`IconCss`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.SplitButtons.SfProgressButton.html#Syncfusion_Blazor_SplitButtons_SfProgressButton_IconCss)
property to `e-icons` with the required icon CSS. By default, the icon is positioned to the left side of the Progress Button.
You can customize the icon's position by using the [`IconPosition`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.SplitButtons.SfProgressButton.html#Syncfusion_Blazor_SplitButtons_SfProgressButton_IconPosition) property.

```csharp
@using Syncfusion.Blazor.SplitButtons
@using Syncfusion.Blazor.Buttons

<SfProgressButton IconCss="e-icons e-play-icon" IconPosition="IconPosition.Left">PLAY
</SfProgressButton>

<style>
    .e-play-icon::before {
        content: '\e324';
    }
</style>

```

Output be like

![Button Sample](./images/progress-button-icons.png)
