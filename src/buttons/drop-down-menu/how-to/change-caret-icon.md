---
title: "Change caret icon"
component: "Dropdown Menu"
description: "Dropdown Menu how to section, hide drop down arrow, group popup items using list view component, dialog open on popup item click."
---

# Change caret icon

Dropdown arrow can be customized on popup open and close. It can be handled in
[`OnOpen`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.SplitButtons.SfDropDownButton~OnOpen.html) and
[`OnClose`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.SplitButtons.SfDropDownButton~OnClose.html) event.

In the following example, the up arrow is updated on popup close and down arrow is updated on popup open using `OnOpen` and `OnClose` event by adding and removing `e-caret-up` class.

```csharp
@using Syncfusion.Blazor.SplitButtons

<SfDropDownButton CssClass="@IconCss" Content="Clipboard">
    <DropDownButtonEvents OnOpen="beforeOpen" OnClose="beforeClose"></DropDownButtonEvents>
    <DropDownButtonItems>
        <DropDownButtonItem Text="Edit"></DropDownButtonItem>
        <DropDownButtonItem Text="Copy"></DropDownButtonItem>
        <DropDownButtonItem Text="Paste"></DropDownButtonItem>
    </DropDownButtonItems>
</SfDropDownButton>

@code {
    public string IconCss = "";
    private void beforeOpen(BeforeOpenCloseMenuEventArgs args)
    {
        this.IconCss = "e-caret-up";
        this.StateHasChanged();
    }
    private void beforeClose(BeforeOpenCloseMenuEventArgs args)
    {
        this.IconCss = "";
        this.StateHasChanged();
    }
}

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

Output be like

![Change caret icon](./../images/ddb-caret.png)