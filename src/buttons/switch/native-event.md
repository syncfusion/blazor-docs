---
title: "Native Event"
component: "Switch"
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

We have provided the following native event support to the Switch component:

| List of Native events |  |  | | | |
| --- | --- | --- | --- | --- | --- |
|onfocus|onfocusout|onfocusin|onkeydown|onkeyup|Onkeypress|

## How to bind focus event to Switch

The ‘onfocus’ attribute is used to bind the focus event for Switch. Here, we have explained about the sample code snippets.

`Default.razor`

```csharp
@using Syncfusion.EJ2.RazorComponents.Buttons

<label>onfocus</label><EjsSwitch Onfocus="@onfocus"></EjsSwitch>

@code {

    private void onfocus(UIFocusEventArgs args)
    {
       //onfocus Event triggered
    }
}

```
