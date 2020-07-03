---
title: "Change caret icon"
component: "DropDownButton"
description: "DropDownButton how to section, hide drop down arrow, group popup items using list view component, dialog open on popup item click."
---

# Change caret icon

Dropdown arrow can be customized on popup open and close. It can be handled in
[`beforeOpen`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.EJ2.RazorComponents~Syncfusion.EJ2.RazorComponents.SplitButtons.EjsDropDownButton~BeforeOpen.html) and
[`beforeClose`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.EJ2.RazorComponents~Syncfusion.EJ2.RazorComponents.SplitButtons.EjsDropDownButton~BeforeClose.html) event.

In the following example, the up arrow is updated on popup close and down arrow is updated
on popup open using `beforeOpen` and `beforeClose` event by adding and removing
`e-caret-up` class.

`Index.razor`

```csharp

<EjsDropDownButton ID="ddbtn" ref="ddbtn" Items="@items" Content="Clipboard" BeforeOpen="@beforeOpen" BeforeClose="@beforeClose"></EjsDropDownButton>

@functions {

    List<object> items = new List<object>
     {
            new { text = "Edit" },
            new { text = "Copy" },
            new { text = "Paste" }

        };
    EjsDropDownButton ddbtn;
    public string iconCss = "e-caret-up";
    private void beforeOpen(BeforeOpenCloseMenuEventArgs args)
    {
        ddbtn.CssClass = this.iconCss;
        ddbtn.DataBind();
    }

      private void beforeClose(BeforeOpenCloseMenuEventArgs args)
    {
         ddbtn.CssClass = "";
         ddbtn.DataBind();
    }

}
  ```

  `_Host.cshtml`

   ```html

<style>
    .e-caret {
        transform: rotate(0deg);
        transition: transform 200ms ease-in-out;
    }

    .e-caret-up .e-caret {
        transform: rotate(180deg);
    }
</style>

  ```