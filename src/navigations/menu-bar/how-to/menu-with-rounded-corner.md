---
title: "Menu Bar with rounded corner"
component: "Menu Bar"
description: "This section helps to learn customise the menu bar with rounded corners."
---

# Menu Bar with rounded corner

The rounded corner can be achieved by using the [`CssClass`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Navigations.SfMenu~CssClass.html) property. Add a custom class to the menu bar component and customize it using the `border-radius` CSS property. For more information, refer to the `styles` specified in the below sample.

```csharp
@using Syncfusion.Blazor.Navigations

<SfMenu Items="@MenuItems" CssClass="e-rounded-menu"></SfMenu>

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

<style>

    /* Styles to achieve rounder corner in menu */
    .e-menu-wrapper.e-rounded-menu:not(.e-menu-popup),
    .e-menu-wrapper.e-rounded-menu .e-menu {
        border-radius: 20px;
    }

    /* Increased the menu component left and right padding for better rounded corner UI */
    .e-menu-wrapper.e-rounded-menu ul.e-menu {
        padding: 0 14px;
    }
</style>

```

Output be like

![Menu Sample](./../images/rounded.png)