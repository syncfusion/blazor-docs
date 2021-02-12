---
component: "Context Menu"
---

# Multilevel nesting

The Multiple level nesting supports in Context Menu. It can be achieved by mapping the [`Items`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Navigations.SfMenu~Items.html)
property inside the parent [`MenuItem`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Navigations.ContextMenuItem.html). In the below sample, three level nesting of Context Menu is provided.

```csharp
@using Syncfusion.Blazor.Navigations

<div id="target">Right click/Touch hold to open the Context Menu </div>
<SfContextMenu Target="#target" Items="@MenuItems"></SfContextMenu>

@code {
public List<MenuItem> MenuItems = new List<MenuItem>
{
    new MenuItem { Text = "Show All Bookmarks" },
    new MenuItem { Text = "Bookmarks Toolbar", Items = new List<MenuItem>{
    new MenuItem { Text = "Most Visited", Items = new List<MenuItem>{
    new MenuItem { Text = "Google"},
    new MenuItem { Text = "Gmail"} }
    } } },
    new MenuItem { Text = "Recently Added" }
    };
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

![Context Menu Sample](./images/cm-multilevel.png)