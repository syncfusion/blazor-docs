---
title: "RadioButton Label and Size"
component: "RadioButton"
description: "RadioButton control supports different sizes and label."
---

# Label and Size

This section explains the different sizes and labels.

## Label

RadioButton caption can be defined by using the [`label`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.EJ2.RazorComponents~Syncfusion.EJ2.RazorComponents.Buttons.EjsRadioButton~Label.html) property.
This reduces the manual addition of label for RadioButton. You can customize the label position before or after the
RadioButton through the [`labelPosition`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.EJ2.RazorComponents~Syncfusion.EJ2.RazorComponents.Buttons.EjsRadioButton~LabelPosition.html) property.

`Index.razor`

```csharp

<ul>
    <li>
        <EjsRadioButton ID="radio1" Label="Left SIDe Label" Name="position" LabelPosition="@Syncfusion.EJ2.RazorComponents.Buttons.RadioLabelPosition.Before"></EjsRadioButton>
    </li>
    <li>
        <EjsRadioButton ID="radio2" Label="Right SIDe Label" Name="position" LabelPosition="@Syncfusion.EJ2.RazorComponents.Buttons.RadioLabelPosition.After"></EjsRadioButton>
    </li>
</ul>

  ```

  `_Host.cshtml`

   ```html

    <style>
    .e-radio-wrapper {
        margin-top: 18px;
    }

    li {
        list-style: none;
    }
   </style>

  ```

## Size

The different RadioButton sizes available are default and small. To reduce the size of the default RadioButton to small,
set the [`cssClass`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.EJ2.RazorComponents~Syncfusion.EJ2.RazorComponents.Buttons.EjsRadioButton~CssClass.html) property to `e-small`.

`Index.razor`

```csharp

<ul>
    <li>
        <EjsRadioButton ID="radio11" Label="Small" Name="size" checked="true" CssClass="e-small"></EjsRadioButton>
    </li>
    <li>
        <EjsRadioButton ID="radio22" Label="Default" Name="size"></EjsRadioButton>
    </li>
</ul>

  ```

  `_Host.cshtml`

   ```html

    <style>
    .e-radio-wrapper {
        margin-top: 18px;
    }

    li {
        list-style: none;
    }
</style>

  ```

## See Also

* [How to customize the RadioButton appearance](./how-to/customize-radiobutton-appearance)