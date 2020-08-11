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
    <ContextMenuEvents TValue="ContextMenuItem" Created="create" OnOpen="open"></ContextMenuEvents>
</SfContextMenu>

@code {
    SfContextMenu<ContextMenuItem> ContextMenuObj;
    public List<ContextMenuItem> MenuItems = new List<ContextMenuItem>
    {
        new ContextMenuItem{ Text="View", Items= new List<ContextMenuItem>{
            new ContextMenuItem { Text="Large Icons"},
            new ContextMenuItem { Text="Medium Icons"},
            new ContextMenuItem { Text="Small Icons"} } },
        new ContextMenuItem{ Text="Sort By" },
        new ContextMenuItem{ Text="Refresh" },
        new ContextMenuItem{ Separator=true },
        new ContextMenuItem{ Text="New" },
        new ContextMenuItem{ Separator=true},
        new ContextMenuItem{ Text="Display Settings"},
        new ContextMenuItem{ Text="Personalize"}
    };
        public List<string> SubMenuItem = new List<string> { "Medium Icons" };
        public List<string> MenuItem = new List<string> { "Display Settings" };
        private void open(Syncfusion.Blazor.Navigations.BeforeOpenCloseMenuEventArgs<ContextMenuItem> args)
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