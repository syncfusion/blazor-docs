---
title: "Customize Button Appearance"
component: "Button"
description: "Button how to section, block button, repeat button, tooltip for Button, customization of button appearance, input and anchor elements."
---

# Customize Button Appearance

You can customize the appearance of the Button by using the Cascading Style Sheets (CSS). Define the CSS according to
your requirement, and assign the class name to the [`cssClass`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.EJ2.RazorComponents~Syncfusion.EJ2.RazorComponents.Buttons.EjsButton~CssClass.html)
property. In the following code snippet the background color, text color, height, width, and sharp corner of the Button
can be customized through the `e-custom` class for all states (hover, focus, and active).

`Index.razor`

```csharp

   <EjsButton ID="custom" Content="CUSTOM" CssClass="e-custom"></EjsButton>

  ```

  `_Host.cshtml`

   ```html

    <style>
        .e-custom {
            border-radius: 0;
            height: 30px;
            width: 80px;
        }

            .e-custom, .e-custom:hover, .e-custom:focus, .e-custom:active {
                background-color: #ff6e40;
                color: #fff;
            }
    </style>

  ```  