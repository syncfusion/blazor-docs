---
title: "Scrollable Menu Bar"
component: "Menu Bar"
description: "This section helps to learn how to Scrollable Menu Bar."
---

# Use Case Scenario

## Scrollable Menu Bar

The Menu Bar component supports horizontal and vertical scrolling to render large Menu Bars and sub menus in an adaptive way. This can be achieved by enabling the [`EnableScrolling`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Navigations.SfMenu~EnableScrolling.html) property and by restricting the corresponding Menu Bar/Sub Menu Bar size.

```csharp

@using Syncfusion.Blazor.Navigations

<SfMenu Items="MenuItems" EnableScrolling="true" CssClass="e-scrollable-menu">
</SfMenu>

@code{
    public List<MenuItem> MenuItems = new List<MenuItem>{
        new MenuItem{ Text = "File", Items = new List<MenuItem>{
            new MenuItem{ Text= "Open" },
            new MenuItem{ Text= "Save" },
            new MenuItem{ Text= "Save As" },
            new MenuItem{ Text= "Print" },
            new MenuItem{ Text= "Share" },
            new MenuItem{ Text= "Info" },
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
        new MenuItem{ Text = "Insert", Items = new List<MenuItem>{
        new MenuItem{ Text="Comment"},
        new MenuItem{ Text="Links"},
        new MenuItem{ Text="Table"} }
    },
        new MenuItem{ Text = "Design" },
        new MenuItem{ Text = "Go" },
        new MenuItem{ Text = "Layout" },
        new MenuItem{ Text = "Help" }
    };
}

<style>
    .e-scrollable-menu:not(.e-menu-popup) {
       width: 400px;
    }
</style>

```

Output be like

![Menu Sample](./images/menu-scrollable.png)

## Hamburger Menu

The following example demonstrates the use case of [`HamburgerMenu`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Navigations.SfMenu~HamburgerMode.html) mode.

```csharp

@using Syncfusion.Blazor.Navigations;

<SfMenu Items="@menuItems" HamburgerMode="true" ShowItemOnClick="true"></SfMenu>

@code {
    private List<MenuItem> menuItems = new List<MenuItem>
    {
        new MenuItem{ Text = "File", IconCss = "em-icons e-file", Items = new List<MenuItem>
        {
            new MenuItem { Text= "Open", IconCss= "em-icons e-open" },
            new MenuItem { Text= "Save", IconCss= "em-icons e-save" },
            new MenuItem { Separator= true },
            new MenuItem { Text= "Exit" }
        }
    },
         new MenuItem { Text = "Edit", IconCss = "em-icons e-edit", Items = new List<MenuItem>
         {
            new MenuItem { Text= "Cut", IconCss= "em-icons e-cut" },
            new MenuItem { Text= "Copy", IconCss= "em-icons e-copy" },
            new MenuItem { Text= "Paste", IconCss= "em-icons e-paste" }
         }
    },
         new MenuItem { Text = "View", Items = new List<MenuItem> {
            new MenuItem { Text = "Toolbars", Items = new List<MenuItem>{
                new MenuItem { Text= "Menu Bar" },
                new MenuItem { Text= "Bookmarks Toolbar" },
                new MenuItem { Text= "Customize" }
         }
    },
         new MenuItem { Text = "Zoom", Items = new List<MenuItem>
         {
            new MenuItem { Text= "Zoom In" },
            new MenuItem { Text= "Zoom Out" },
            new MenuItem { Text= "Reset" },
         }
    },
         new MenuItem { Text = "Full Screen" } }
    },
         new MenuItem { Text = "Tools", Items = new List<MenuItem> {
            new MenuItem { Text= "Spelling & Grammar" },
            new MenuItem { Text= "Customize" },
            new MenuItem { Separator= true },
            new MenuItem { Text= "Options" }
         }
    },
          new MenuItem { Text = "Help" }
    };
}

<style>

    .e-menu-header {
        width: 100%;
        background-color: #7b8cfb;
    }

</style>

```

Output be like

![Menu Sample](./images/menu-hamburger.png)

## Mobile View

The following example demonstrates the use case of Menu Bar in Mobile mode with hamburger.

```csharp

@using Syncfusion.Blazor.Navigations;

<div class="menu-control">
    <div id='layoutcontainer' class="deviceLayout">
        <div class="speaker">
            <div class="camera"></div>
        </div>
        <div class="layout">
            <div id="container">
                <SfMenu Items="@menuItems" HamburgerMode="true" ShowItemOnClick="true"></SfMenu>
            </div>
        </div>
        <div class="outerButton"> </div>
    </div>
</div>

@code {
    private List<MenuItem> menuItems = new List<MenuItem>
    {
        new MenuItem{ Text = "File", IconCss = "em-icons e-file", Items = new List<MenuItem>
        {
            new MenuItem { Text= "Open", IconCss= "em-icons e-open" },
            new MenuItem { Text= "Save", IconCss= "em-icons e-save" },
            new MenuItem { Separator= true },
            new MenuItem { Text= "Exit" }
        }
    },
         new MenuItem { Text = "Edit", IconCss = "em-icons e-edit", Items = new List<MenuItem>
         {
            new MenuItem { Text= "Cut", IconCss= "em-icons e-cut" },
            new MenuItem { Text= "Copy", IconCss= "em-icons e-copy" },
            new MenuItem { Text= "Paste", IconCss= "em-icons e-paste" }
         }
    },
         new MenuItem { Text = "View", Items = new List<MenuItem> {
            new MenuItem { Text = "Toolbars", Items = new List<MenuItem>{
                new MenuItem { Text= "Menu Bar" },
                new MenuItem { Text= "Bookmarks Toolbar" },
                new MenuItem { Text= "Customize" }
         }
    },
         new MenuItem { Text = "Zoom", Items = new List<MenuItem>
         {
            new MenuItem { Text= "Zoom In" },
            new MenuItem { Text= "Zoom Out" },
            new MenuItem { Text= "Reset" },
         }
    },
         new MenuItem { Text = "Full Screen" } }
    },
         new MenuItem { Text = "Tools", Items = new List<MenuItem> {
            new MenuItem { Text= "Spelling & Grammar" },
            new MenuItem { Text= "Customize" },
            new MenuItem { Separator= true },
            new MenuItem { Text= "Options" }
         }
    },
          new MenuItem { Text = "Help" }
    };
}

<style>
    .deviceLayout #menu {
        -ms-overflow-style: none;
        scrollbar-width: none;
        height: 363px;
    }

    .deviceLayout #menu::-webkit-scrollbar {
         width: 0;
    }

    .menu-control {
        text-align: center;
    }

    #layoutcontainer:not(.deviceLayout) {
        margin-top: 45px;
    }

    .deviceLayout {
        line-height: initial;
        border: 1px solid black;
        width: 285px;
        height: 505px;
        margin: auto;
        margin-bottom: 15px;
        border-radius: 28px;
        position: relative;
        background-image: linear-gradient(to top, #ffffff, #f5f5f5);
    }

    .deviceLayout .speaker {
        border: 1px solid black;
        border-radius: 5px;
        width: 20%;
        height: 5px;
        margin: 15px auto 0px auto;
        position: relative;
    }

    .deviceLayout .outerButton {
        width: 30px;
        height: 30px;
        border: 1px solid black;
        border-radius: 50%;
        position: absolute;
        bottom: calc(0% + 10px);
        left: calc(50% - 15px);
    }

    .deviceLayout .camera {
        position: absolute;
        left: calc(-15% - 10px);
        top: -100%;
        width: 10px;
        height: 10px;
        border-radius: 50%;
        border: 1px solid black;
    }

    .deviceLayout .layout {
        border: 1px solid black;
        margin: 20px 13px 0px 13px;
    }

    .layout #container {
        height: 405px;
        background-color: white;
        overflow: hidden;
    }

</style>

```

Output be like

![Menu Sample](./images/menu-mobile-view.png)
