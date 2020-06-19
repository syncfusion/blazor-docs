---
title: "Animation Settings"
component: "Context Menu"
description: "This section helps to learn how to change the animation of context menu."
---

# Change animation settings

To change the animation of the Context Menu, [`AnimationSettings`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Navigations.ContextMenuAnimationSettings.html
) property is used.
The supported effects for Context Menu are,

| Effect | Functionality |
| ------------ | ----------------------- |
| None | Specifies the sub menu transform with no animation effect. |
| SlideDown | Specifies the sub menu transform with slide down effect. |
| ZoomIn | Specifies the sub menu transform with zoom in effect. |
| FadeIn | Specifies the sub menu transform with fade in effect. |

The following sample illustrates how to open Context Menu with `FadeIn` effect with the `Duration` of `800ms`.

```csharp
@using Syncfusion.Blazor.Navigations

<div id="target">Right click/Touch hold to open the Context Menu</div>
<SfContextMenu Target="#target" Items="@MenuItems">
    <ContextMenuAnimationSettings Effect = "MenuEffect.FadeIn" Duration = "800"></ContextMenuAnimationSettings>
</SfContextMenu>

@code {
    public List<MenuItem> MenuItems = new List<MenuItem>{
        new MenuItem { Text = "Cut" },
        new MenuItem { Text = "Copy" },
        new MenuItem { Text = "Paste" }
    };
}

<style>
    #target {
        border: 1px dashed;
        height: 250px;
        padding: 10px;
        position: relative;
        text-align: center;
        color: gray;
        line-height: 17;
        font-size: 14px;
    }
</style>

```

Output be like

![Context Menu Sample](./../images/context-menu.png)