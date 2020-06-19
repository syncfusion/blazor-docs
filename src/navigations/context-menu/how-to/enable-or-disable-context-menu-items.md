---
title: "Enable or disable context menu items"
component: "Context Menu"
description: "This section helps to learn how to Enable or disable context menu items"
---

# Enable or disable context menu items

You can enable and disable the menu items using the [`EnableItems`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Navigations.SfContextMenu~EnableItems.html) method in Context Menu. To enable menuItems, set the `Enable` property in argument to `true` and vice-versa.

In the following example, the **Display Settings** in parent items and **Medium icons** in sub menu items are disabled.

```csharp

@using Syncfusion.Blazor.Navigations

<div id="target">Right click/Touch hold to open the ContextMenu </div>
<SfContextMenu Target="#target" Items="@MenuItems" @ref="ContextMenuObj">
    <ContextMenuEvents Created="create" OnOpen="open"></ContextMenuEvents>
</SfContextMenu>

@code {
    SfContextMenu ContextMenuObj;
    public List<MenuItem> MenuItems = new List<MenuItem>
    {
        new MenuItem{ Text="View", Items= new List<MenuItem>{
            new MenuItem { Text="Large Icons"},
            new MenuItem { Text="Medium Icons"},
            new MenuItem { Text="Small Icons"} } },
        new MenuItem{ Text="Sort By" },
        new MenuItem{ Text="Refresh" },
        new MenuItem{ Separator=true },
        new MenuItem{ Text="New" },
        new MenuItem{ Separator=true},
        new MenuItem{ Text="Display Settings"},
        new MenuItem{ Text="Personalize"}
    };
        public string[] SubMenuItem = new string[] { "Medium Icons" };
        public string[] MenuItem = new string[] { "Display Settings" };
        private void open(Syncfusion.Blazor.Navigations.BeforeOpenCloseMenuEventArgs args)
        {
            ContextMenuObj.EnableItems(this.SubMenuItem, false);
        }
        private void create(object obj)
        {
            ContextMenuObj.EnableItems(this.MenuItem, false);
        }
 };

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

![Context Menu Sample](./../images/cm-disable.png)

> To disable sub menu items, use the [`OnOpen`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Navigations.SfContextMenu~OnOpen.html) event.