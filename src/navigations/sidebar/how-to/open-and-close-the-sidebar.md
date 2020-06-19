---
title: "How To"
component: "Sidebar"
description: "Miscellaneous aspects of customizing the sidebar"
---

<!-- markdownlint-disable MD009 -->

# Open and close the Sidebar

Opening and closing the Sidebar can be achieved with built-in public methods.

| Method | Description  |
|------|------|
| `show()`  |  Method to open the Sidebar. |
| `hide()`  |  Method to close the Sidebar. |
| `toggle()`  |  Method to toggle the open/close state of the Sidebar. |

In the following sample, toggle method has been used to show or hide the Sidebar on button click.

```csharp

@using Syncfusion.Blazor.Navigations
@using Syncfusion.Blazor.Buttons

<div id="header" style="height:45px;text-align: center;color:white;background-color:midnightblue;font-size:1.2rem;line-height:45px;">
    Header
</div>

<SfSidebar @ref="sidebarObj" Width="250px">
    <ChildContent>
        <div style="text-align: center;" class="text-content">
            <span>Sidebar</span>
            <span>
                <SfButton @onclick="Close" CssClass="e-btn close-btn">Close Sidebar</SfButton>
            </span>
        </div>
    </ChildContent>
</SfSidebar>

<div class="text-content" style="text-align: center;">
    <div>Main content</div>
    <div>
        <SfButton @onclick="Toggle" IsToggle="true" CssClass="e-btn e-info">Toggle Sidebar</SfButton>
    </div>
</div>

@code{
    SfSidebar sidebarObj;
    public void Close()
    {
        this.sidebarObj.Hide();
    }
    public void Toggle()
    {
        this.sidebarObj.Toggle();
    }
}

<style>
    .e-sidebar {
        background-color: #f8f8f8;
        color: black;
    }

    .text-content {
        font-size: 1.5rem;
        padding: 3rem;
    }

    .main > div {
        padding: 0px !important;
    }
</style>

```

Output be like the below.

![output](./../images/open_close.png)
