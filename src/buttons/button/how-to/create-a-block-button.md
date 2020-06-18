---
title: "Create a Block Button"
component: "Button"
description: "Button how to section, block button, repeat button, tooltip for Button, customization of button appearance, input and anchor elements."
---

# Create a Block Button

You can customize a Button into a Block Button that will span the entire width of its parent element. To create a Block
Button, set the [`cssClass`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.EJ2.RazorComponents~Syncfusion.EJ2.RazorComponents.Buttons.EjsButton~CssClass.html)
property to `e-block`.

`Index.razor`

```csharp

   <EjsButton ID="blockbtn" Content="BLOCKBUTTON" CssClass="e-block"></EjsButton>
   <EjsButton ID="primarybtn" Content="BLOCKBUTTON" CssClass="e-block" IsPrimary="true"></EjsButton>
   <EjsButton ID="successbtn" Content="BLOCKBUTTON" CssClass="e-block e-success"></EjsButton>

}
  ```