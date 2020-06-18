---
title: "Native Event"
component: "DropDownButton"
description: "This section helps to learn how to trigger the native events in ASP.NET Core Razor application"
---

# Overview

You can define the native event using on`<event>` attribute in component. The value of attribute is treated as an event handler. The event specific data will be available in event arguments.

The different event argument types for each event are,

* Focus Events - UIFocusEventArgs
* Mouse Events - UIMouseEventArgs
* Drag Events - UIDragEventArgs
* Keyboard Events - UIKeyboardEventArgs
* Input Events - UIChangeEventArgs/UIEventArgs
* Touch Events – UITouchEventArgs
* Clipboard Events - UIClipboardEventArgs

## List of Native events supported

We have provided the following native event support to the DropDownButton component:

| List of Native events |  |  | |
| --- | --- | --- | --- |
| onclick | onblur | onfocus | onfocusout |
|onmousemove|onmouseover|onmouseout|onmousedown|onmouseup|
|ondblclick|onkeydown|onkeyup|onkeypress|
|ontouchend|onfocusin|onmouseup|ontouchstart|

## How to bind click event to DropDownButton

The ‘onclick’ attribute is used to bind the click event for DropDownButton. Here, we have explained about the sample code snippets of dropdown button.

`Default.razor`

```csharp
@using Syncfusion.EJ2.RazorComponents.Buttons

<EjsDropDownButton Items="@items" Content="Profile" Onclick="@onclick"></EjsDropDownButton>
@code {
    public List<object> items { get; set; } = new List<object>
  {
    new { text = "Dashboard", iconCss = "e-ddb-icons e-dashboard" },
    new { text = "Notifications", iconCss = "e-ddb-icons e-notifications" },
    new { text = "User Settings", iconCss = "e-ddb-icons e-settings" },
    new { text = "Log Out", iconCss = "e-ddb-icons e-logout" }
    };

    private void onclick(UIMouseEventArgs args)
    {
         //onclick Event triggered
    }
}
```
