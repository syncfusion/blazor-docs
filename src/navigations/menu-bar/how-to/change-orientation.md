---
title: "Change orientation"
component: "Menu Bar"
description: "This section helps to learn how to Change orientation."
---

# Change orientation

Orientation in menu items can be changed horizontally or vertically using the [`Orientation`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Navigations.SfMenu~Orientation.html) property. By default, it is horizontally aligned.

```csharp
@using Syncfusion.Blazor.Navigations

<SfMenu Items="@MenuItems" Orientation="Orientation.Vertical"></SfMenu>

@code {
    public List<MenuItem> MenuItems = new List<MenuItem>{
        new MenuItem { Text = "File", Items = new List<MenuItem>{
            new MenuItem{ Text = "Open" },
            new MenuItem{ Text = "Save" },
            new MenuItem{ Text = "Exit" } } },
        new MenuItem { Text = "Edit", Items = new List<MenuItem>{
            new MenuItem{ Text = "Cut" },
            new MenuItem{ Text = "Copy" },
            new MenuItem{ Text = "Paste" } } },
        new MenuItem { Text = "View", Items = new List<MenuItem>{
            new MenuItem{ Text = "Toolbar" },
            new MenuItem{ Text = "Sidebar" },
            new MenuItem{ Text = "Fullscreen" } } },
        new MenuItem { Text = "Tools", Items = new List<MenuItem>{
            new MenuItem{ Text = "Spelling & Grammer" },
            new MenuItem{ Text = "Customize" },
            new MenuItem{ Text = "Options" } } },
    };
}

```

Output be like

![Menu Sample](./../images/orientation.png)