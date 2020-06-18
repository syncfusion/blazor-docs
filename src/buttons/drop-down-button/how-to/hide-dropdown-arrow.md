---
title: "Hide dropdown arrow"
component: "DropDownButton"
description: "DropDownButton how to section, hide drop down arrow, group popup items using list view component, dialog open on popup item click."
---

# Hide dropdown arrow

You can hide the dropdown arrow from the DropDownButton by adding class `e-caret-hide`
to DropDownButton element using [`cssClass`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.EJ2.RazorComponents~Syncfusion.EJ2.RazorComponents.SplitButtons.EjsDropDownButton~CssClass.html)
property.

`Index.razor`

```csharp

<EjsDropDownButton ID="hide-arrow" Items="@items" Content="Message" CssClass="e-caret-hide"></EjsDropDownButton>

@functions {

    List<object> items = new List<object>
     {
            new { text = "Edit" },
            new { text = "Delete" },
            new { text = "Mark as Read" },
             new { text = "Like Message" }  

    };

}
  ```
