---
title: "Checkbox Label and Size"
component: "Checkbox"
description: "Checkbox control supports different sizes and label."
---

# Label and Size

This section explains the different sizes and labels.

## Label

The Checkbox caption can be defined by using the [`Label`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Buttons.SfCheckBox~Label.html) property.
This reduces the manual addition of label for Checkbox. You can customize the label position before or after the Checkbox through the [`LabelPosition`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Buttons.SfCheckBox~LabelPosition.html) property.

```csharp
@using Syncfusion.Blazor.Buttons

<SfCheckBox Label="Left Side Label" LabelPosition="LabelPosition.Before" @bind-Checked="isLeftChecked"></SfCheckBox><br />
<SfCheckBox Label="Right Side Label" LabelPosition="LabelPosition.After" @bind-Checked="isRightChecked"></SfCheckBox>

@code {
    private bool isLeftChecked = true;
    private bool isRightChecked = true;
}

```

Output be like

![Button Sample](./images/cb-label.png)

## Size

The different Checkbox sizes available are default and small. To reduce the size of default Checkbox to small, set the [`CssClass`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Buttons.SfCheckBox~CssClass.html) property to `e-small`.

```csharp
@using Syncfusion.Blazor.Buttons

<SfCheckBox @bind-Checked="isSmallChecked" Label="Small" CssClass="e-small"></SfCheckBox><br />
<SfCheckBox @bind-Checked="isDefaultChecked" Label="Default"></SfCheckBox>

@code {
    private bool isSmallChecked = true;
     private bool isDefaultChecked = true;
}

<style>
    .e-checkbox-wrapper {
        margin-top: 18px;
    }
</style>

```

Output be like

![Button Sample](./images/cb-size.png)

## See Also

* [Checkbox customization](./how-to/customized-checkbox)