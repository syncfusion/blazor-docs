---
title: "Right to left"
component: "Menu Bar"
description: "This section helps to learn how to give RTL support to menu bar component."
---

# Right-To-Left

Menu Bar component has RTL support. This can be achieved by setting [`EnableRtl`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Navigations.SfMenu~EnableRtl.html) as `true`.

The following example illustrates how to enable right-to-left support in Menu Bar component.

```csharp
@using Syncfusion.Blazor.Navigations

<SfMenu Items="@MenuItems" EnableRtl="true"></SfMenu>

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

![Menu Sample](./../images/rtl.png)