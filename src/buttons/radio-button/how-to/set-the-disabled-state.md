---
title: "RadioButton How To sections"
component: "RadioButton"
description: "RadioButton how to section, name and value in form submit, customize RadioButton appearance."
---

# Set the disabled state

RadioButton component can be enabled/disabled by giving [`disabled`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.EJ2.RazorComponents~Syncfusion.EJ2.RazorComponents.Buttons.EjsRadioButton~Disabled.html) property. To disable RadioButton component,
the `disabled` property can be set as `true`.

`Index.razor`

```csharp

<ul>
        <li>
            <EjsRadioButton ID="radio1" Label="Option 1" Name="default" Checked="true"></EjsRadioButton>
        </li>
        <li>
            <EjsRadioButton ID="radio2" Label="Option 2" Name="default" Disabled="true"></EjsRadioButton>
        </li>
        <li>
            <EjsRadioButton ID="radio3" Label="Option 3" Name="default"></EjsRadioButton>
        </li>
    </ul>

  ```

  `_Host.cshtml`

   ```html

<style>
    .e-radio-wrapper {
        margin-top: 18px;
    }

    button {
        margin: 20px 0 0 5px;
    }

    li {
        list-style: none;
    }
</style>

  ```