---
title: "Radio Button Label and Size"
component: "Radio Button"
description: "Radio Button control supports different sizes and label."
---

# Label and Size

This section explains the different sizes and labels.

## Label

Radio Button caption can be defined by using the [`Label`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Buttons.SfRadioButton~Label.html) property.
This reduces the manual addition of label for Radio Button. You can customize the label position before or after the
Radio Button through the [`LabelPosition`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Buttons.SfRadioButton~LabelPosition.html) property.

```csharp
@using Syncfusion.Blazor.Buttons

<SfRadioButton Label="Left Side Label" Name="position" LabelPosition="RadioLabelPosition.Before"></SfRadioButton><br />
<SfRadioButton Label="Right Side Label" Checked="true" Name="position" LabelPosition="RadioLabelPosition.After"></SfRadioButton>

```

Output be like

![Radio Button Sample](./images/rb-label.png)

## Size

The different Radio Button sizes available are default and small. To reduce the size of the default Radio Button to small,
set the [`CssClass`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Buttons.SfRadioButton~CssClass.html) property to `e-small`.

```csharp
@using Syncfusion.Blazor.Buttons

<SfRadioButton Label="Small" Name="size" checked="true" CssClass="e-small"></SfRadioButton><br />
<SfRadioButton Label="Default" Name="size"></SfRadioButton>

```

Output be like

![Radio Button Sample](./images/rb-size.png)

## See Also

* [How to customize the Radio Button appearance](./how-to/customize-radiobutton-appearance)