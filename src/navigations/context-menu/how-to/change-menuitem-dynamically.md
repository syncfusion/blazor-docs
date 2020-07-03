---
title: "Change Menu Item Dynamically"
component: "Context Menu"
description: "This section helps to learn how to Change Menu Item Dynamically"
---

# Change Menu Item Dynamically

The items visible in the Context Menu can be changed dynamically based on the target. To achieve this behavior, initialize Context Menu with all items using [`Items`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Navigations.SfContextMenu~Items.html) property and then you can Hide/Show items using [`HideItems`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Navigations.SfContextMenu~HideItems.html)/[`ShowItems`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Navigations.SfContextMenu~ShowItems.html) method in [`OnOpen`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Navigations.ContextMenuEvents~OnOpen.html) event.

```csharp

@using Syncfusion.Blazor.Navigations

<div id="target">Right click/Touch hold to open the ContextMenu </div>
<SfContextMenu Target="#target" Items="MenuItems" @ref="ContextMenuObj">
    <ContextMenuEvents OnOpen="Open"></ContextMenuEvents>
</SfContextMenu>

@code {
    SfContextMenu ContextMenuObj;
    public List<MenuItem> MenuItems = new List<MenuItem>
    {
        new MenuItem{ Text = "Cut" },
        new MenuItem{ Text = "Copy" },
        new MenuItem{ Text = "Paste" },
        new MenuItem{ Text = "Add" },
        new MenuItem{ Text = "Edit" },
        new MenuItem{ Text = "Delete" }
    };

    public void Open(BeforeOpenCloseMenuEventArgs args)
    {
        this.MenuObj.HideItems(new string[] { "Cut", "Copy", "Paste" });
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

![Context Menu Sample](./../images/cm-dynamic.png)