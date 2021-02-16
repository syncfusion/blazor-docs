<!-- markdownlint-disable MD009 -->

# Responsive Sidebar

Sidebar often behaves differently on a mobile versus a desktop display. It has an effective feature that offers to set it in opened or closed state corresponding to the specified resolution. This is achieved through `MediaQuery` property that allows you to set the Sidebar in an expanded state or collapsed state only in user-defined resolution.

In the following sample, mediaQuery has been used for specific resolution to close and open sidebar.

```csharp

@using Syncfusion.Blazor.Navigations

<div id="header" style="height:45px;color:white;background-color:midnightblue;font-size:1.2rem;line-height:45px;">
    <span style="position:absolute; left:10px; font-size:25px;">&#9776;</span>
    <span style="margin-left:45%;">Header</span>
</div>

<SfSidebar Width="250px" MediaQuery="(min-width: 600px)">
    <ChildContent>
        <div style="text-align: center;" class="text-content"> Sidebar </div>
    </ChildContent>
</SfSidebar>

<div class="text-content" style="text-align: center;">Main content</div>

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

![output](./images/auto-close.gif)
