---
title: "CheckBox Label and Size"
component: "CheckBox"
description: "CheckBox control supports different sizes and label."
---

# Label and Size

This section explains the different sizes and labels.

## Label

The CheckBox caption can be defined by using the [`label`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.EJ2.RazorComponents~Syncfusion.EJ2.RazorComponents.Buttons.EjsCheckBox~Label.html) property.
This reduces the manual addition of label for CheckBox. You can customize the label position before or after the CheckBox
through the [`labelPosition`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.EJ2.RazorComponents~Syncfusion.EJ2.RazorComponents.Buttons.EjsCheckBox~LabelPosition.html) property.

`Index.razor`

```csharp

<ul>
    <li>
        <EjsCheckBox ID="cbox1" Label="Left SIDe Label" LabelPosition="@Syncfusion.EJ2.RazorComponents.Buttons.LabelPosition.Before"></EjsCheckBox>
    </li>
    <li>
        <EjsCheckBox ID="cbox2" Label="Right SIDe Label" LabelPosition="@Syncfusion.EJ2.RazorComponents.Buttons.LabelPosition.After" Checked="true"></EjsCheckBox>
    </li>
</ul>

  ```

  `_Host.cshtml`

   ```html

     <style >
        .e-checkbox-wrapper {
            margin-top: 18px;
        }

        li {
            list-style: none;
        }
    </style>

  ```  

## Size

The different CheckBox sizes available are default and small. To reduce the size of default CheckBox to small,
set the [`cssClass`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.EJ2.RazorComponents~Syncfusion.EJ2.RazorComponents.Buttons.EjsCheckBox~CssClass.html) property to `e-small`.

`Index.razor`

```csharp

<ul>
    <li>
        <EjsCheckBox ID="cbox3" Label="Small" CssClass="e-small"></EjsCheckBox>
    </li>
    <li>
        <EjsCheckBox ID="cbox4" Label="Default"></EjsCheckBox>
    </li>
</ul>

  ```

  `_Host.cshtml`

   ```html

     <style >
        .e-checkbox-wrapper {
            margin-top: 18px;
        }

        li {
            list-style: none;
        }
    </style>

  ```  

## See Also

* [CheckBox customization](./how-to/customized-checkbox)