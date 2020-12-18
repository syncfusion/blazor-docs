---
title: "Getting Started"
component: "Menu Bar"
description: "This section helps to learn how to Change SubMenu Position."
---

# Change SubMenu Position

The submenu position can be changed by using the [`OnOpen`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Navigations.MenuEvents~OnOpen.html) event. Assign the `Top` and `Left` position where you want to open the submenu.

In the below sample, the sub menu opens above the parent menu item

```csharp

@using Syncfusion.Blazor.Navigations

<SfMenu ID="element" Items="@MenuItems">
    <MenuEvents OnOpen="Open"></MenuEvents>
</SfMenu>

@code {
    public List<MenuItem> MenuItems = new List<MenuItem>{
        new MenuItem{ Text = "File", Items = new List<MenuItem>{
            new MenuItem{ Text= "Open" },
            new MenuItem{ Text= "Save" },
            new MenuItem{ Text= "Exit" }}
    },
        new MenuItem{ Text = "Edit", Items = new List<MenuItem>{
            new MenuItem{ Text= "Cut" },
            new MenuItem{ Text= "Copy" },
            new MenuItem{ Text= "Paste" }}
    },
        new MenuItem{ Text = "View", Items = new List<MenuItem>{
            new MenuItem{ Text = "Toolbars" },
            new MenuItem{ Text = "Zoom" },
            new MenuItem{ Text = "Full Screen" }}
    },
        new MenuItem{ Text = "Tools", Items = new List<MenuItem>{
            new MenuItem{ Text= "Spelling & Grammar" },
            new MenuItem{ Text= "Customize" },
            new MenuItem{ Text= "Options" }}
    },
        new MenuItem{ Text = "Go" },
        new MenuItem{ Text = "Help" }
    };

    public void Open(BeforeOpenCloseMenuEventArgs args)
    {
        if (args.ParentItem.Text == "File")
        {
            args.Left = 390;
            args.Top = 40;
        }
        if (args.ParentItem.Text == "Edit")
        {
            args.Left = 455;
            args.Top = 40;
        }
        if (args.ParentItem.Text == "View")
        {
            args.Left = 520;
            args.Top = 40;
        }
        if (args.ParentItem.Text == "Tools")
        {
            args.Left = 585;
            args.Top = 40;
        }
    }
}

<style>
    #element {
        margin: 25% 5px 20px 30%;
    }
</style>

```

Output be like

![Menu Sample](./../images/menu-position.png)