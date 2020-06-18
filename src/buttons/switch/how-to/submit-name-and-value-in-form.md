---
title: "Submit name and value in form"
component: "Switch"
description: "Switch how to section, customization of Switch bar and handle, change size, name and value in form submit."
---

# Submit name and value in form

The name attribute of the Switch is used to group Switches. When the Switches are grouped in form, the checked items value attribute will post to the server on form submit. The disabled and unchecked Switch values will not be sent to the server on form submit.

In the following code snippet, USB and Wi-Fi in the checked state, and Bluetooth is in disabled state.
Values that are in checked state only be sent on form submit.

`Index.razor`

```csharp

<div ID='container'>
        <form>
            <table class='size'>
                <tr>
                    <td class='lSize'>USB</td>
                    <td>
                        <EjsSwitch ID="switch1" Checked="true" Value="USB"></EjsSwitch>
                    </td>
                </tr>
                <tr>
                    <td class='lSize'>Wi-Fi</td>
                    <td>
                        <EjsSwitch ID="switch2" Checked="true" Value=">Wi-Fi"></EjsSwitch>
                    </td>
                </tr>
                <tr>
                    <td class='lSize'>Bluetooth</td>
                    <td>
                        <EjsSwitch ID="switch3" Disabled="true" Value="Bluetooth"></EjsSwitch>
                    </td>
                </tr>
                <tr>
                    <td>
                        <EjsButton ID="btnElement" Content="Submit" IsPrimary="true"></EjsButton>
                    </td>
                </tr>
            </table>
        </form>
    </div>

  ```

  `_Host.cshtml`

   ```html

<style>
    button {
        margin: 20px 0 0 5px;
    }

    .size tr td {
        padding: 10px;
    }

    .size .lSize {
        font-family: "Roboto", "Segoe UI", "GeezaPro", "DejaVu Serif", "sans-serif";
        font-size: 13px;
    }

        .size .lSize label {
            user-select: none;
        }
</style>

  ```