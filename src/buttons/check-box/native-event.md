---
title: "Native Event"
component: "CheckBox"
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

We have provided the following native event support to the CheckBox component:

| List of Native events |  |  | | |
| --- | --- | --- | --- | --- |
| onchange | oninput | onblur | onfocusout | onfocusin |
|onfocus|onclick|onkeydown|onkeyup|onkeypress|

## How to bind onchange event to CheckBox

The ‘onchange’ attribute is used to bind the onchange event for checkbox. Here, we have explained about the sample code snippets of checkbox.

`Default.razor`

```csharp
@using Syncfusion.EJ2.RazorComponents.Buttons

<EjsCheckBox Label="onchange" Onchange="@onchange"></EjsCheckBox>

@code {
    private void onchange(UIChangeEventArgs args)
    {
       //onChange Event triggered
    }
}
```
