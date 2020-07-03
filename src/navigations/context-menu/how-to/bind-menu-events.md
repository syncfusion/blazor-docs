---
title: "Bind Menu Events"
component: "Context Menu"
description: "This section helps to learn how to Bind Menu Events"
---

# Bind Menu Events

To bind the menu event in the context menu [`ItemSelected`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.DropDowns.SfListBox~ItemSelected.html) is used and the event is triggered when the item in the context menu is selected.

```csharp

@using Syncfusion.Blazor.Navigations

<div id="target">Right click/Touch hold to open the ContextMenu </div>
<SfContextMenu Target="#target" Items="@MenuItems">
    <ContextMenuEvents ItemSelected="@select"></ContextMenuEvents>
</SfContextMenu>

@code {
    public MenuItemModel SelectedItem;
    public List<MenuItem> MenuItems = new List <MenuItem>
    {
        new MenuItem{ Text = "Cut" },
        new MenuItem{ Text = "Copy" },
        new MenuItem{ Text = "Paste" }
    };

    private void select(MenuEventArgs args) {
    this.SelectedItem = args.Item; // Triggers when item is selected
}
}

<style>
    #target {
        border: 1px dashed;
        height: 150px;
        padding: 10px;
        position: relative;
        text-align: justify;
        color: gray;
        user-select: none;
    }
</style>

```

Output be like

![Context Menu Sample](./../images/context-menu.png)