---
title: "Open and close Context Menu"
component: "Context Menu"
description: "This section helps to learn how to Open and close Context Menu"
---

# Open and close Context Menu

Open and close the Context Menu manually whenever required by using the open and close methods. In the following sample, to open the Context Menu at specified position the [`Open`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Navigations.SfContextMenu-1.html#Syncfusion_Blazor_Navigations_SfContextMenu_1_Open_System_Nullable_System_Double__System_Nullable_System_Double__) method is used with `X` and `Y` coordinates
and to close Context Menu [`Close`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Navigations.SfContextMenu-1.html#Syncfusion_Blazor_Navigations_SfContextMenu_1_Close) method can be used.

```csharp
@using Syncfusion.Blazor.Navigations
@using Syncfusion.Blazor.Buttons

<div id="target">
    <SfContextMenu Target="#target" Items="@MenuItems" @ref="ContextMenuObj"></SfContextMenu>
    <SfButton CssClass="e-btn" OnClick="open">Open ContextMenu</SfButton>
</div>

@code {
    SfContextMenu<MenuItem> ContextMenuObj;
    public List<MenuItem> MenuItems = new List<MenuItem>{
        new MenuItem { Text = "Cut" },
        new MenuItem { Text = "Copy" },
        new MenuItem { Text = "Paste" }
    };
    private void open()
    {
        ContextMenuObj.Open(280, 110);
    }
}

```

Output be like

![Context Menu Sample](./../images/open-close.png)