---
title: "Create DropDownButton with rounded corner"
component: "DropDownButton"
description: "DropDownButton how to section, hide drop down arrow, group popup items using list view component, dialog open on popup item click."
---

# Create DropDownButton with rounded corner

DropDownButton with rounded corner can be achieved by adding `border-radius` CSS property to button element.

In the following example, `e-round-corner` class is defined with `5px` `border-radius`
property and added that class to button element using
[`cssClass`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.EJ2.RazorComponents~Syncfusion.EJ2.RazorComponents.SplitButtons.EjsDropDownButton~CssClass.html) property.

`Index.razor`

```csharp

<EjsDropDownButton ID="ddbtn" Items="@items" cssClass="e-round-corner" Content="Clipboard"></EjsDropDownButton>

@functions {

    List<object> items = new List<object>
     {
            new { text = "Edit" },
            new { text = "Copy" },
            new { text = "Paste" }

        };
}
  ```

  `_Host.cshtml`

   ```html

<style>
    .e-round-corner {
        border-radius: 5px;
    }
</style

  ```