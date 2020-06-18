---
title: "Change Size"
component: "Switch"
description: "Switch how to section, customization of Switch bar and handle, change size, name and value in form submit."
---

# Change Size

The different Switch sizes available are default and small. To reduce the size of default Switch to small,
set the [`cssClass`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.EJ2.RazorComponents~Syncfusion.EJ2.RazorComponents.Buttons.EjsSwitch~CssClass.html) property to `e-small`.

`Index.razor`

```csharp

<div ID='container'>
    <table class='size'>
        <tr>
            <td class='lSize'>Checked</td>
            <td>
                <EjsSwitch ID="switch1" CssClass="e-small"></EjsSwitch>
            </td>
        </tr>
        <tr>
            <td class='lSize'>Unchecked</td>
            <td>
                <EjsSwitch ID="switch2"></EjsSwitch>
            </td>
        </tr>
    </table>
</div>

  ```

  `_Host.cshtml`

   ```html

<style>
    .size tr td {
        padding: 10px;
    }

    .size .lSize {
        font-family: "Roboto", "Segoe UI", "GeezaPro", "DejaVu Serif", "sans-serif";
        font-size: 13px;
        cursor: pointer;
        user-select: none;
    }
</style

  ```