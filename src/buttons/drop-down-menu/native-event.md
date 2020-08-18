---
title: "Native Event"
component: "Dropdown Menu"
description: "This section helps to learn how to trigger the native events in ASP.NET Core Razor application"
---

# Overview

You can define the native event using on `event` attribute in component. The value of attribute is treated as an event handler. The event specific data will be available in event arguments.

The different event argument types for each event are,

* Focus Events - UIFocusEventArgs
* Mouse Events - UIMouseEventArgs
* Keyboard Events - UIKeyboardEventArgs
* Touch Events – UITouchEventArgs

## List of Native events supported

We have provided the following native event support to the DropDownButton component:

| List of Native events |  |  | |
| --- | --- | --- | --- |
| onclick | onblur | onfocus | onfocusout |
|onmousemove|onmouseover|onmouseout|onmousedown|onmouseup|
|ondblclick|onkeydown|onkeyup|onkeypress|
|ontouchend|onfocusin|onmouseup|ontouchstart|

## How to bind click event to Dropdown Menu

The `onclick` attribute is used to bind the click event for Dropdown Menu. Here, we have explained about the sample code snippets of Dropdown Menu.

```csharp
@using Syncfusion.Blazor.SplitButtons

<SfDropDownButton @onclick="onClick" Content="Profile">
    <DropDownMenuItems>
        <DropDownMenuItem Text="Dashboard"></DropDownMenuItem>
        <DropDownMenuItem Text="Notifications"></DropDownMenuItem>
        <DropDownMenuItem Text="User Settings"></DropDownMenuItem>
        <DropDownMenuItem Text="Log Out"></DropDownMenuItem>
     </DropDownMenuItems>
</SfDropDownButton>

@code {
  private void onClick(Microsoft.AspNetCore.Components.Web.MouseEventArgs args)
  {
         //onclick Event triggered
  }
}

```
