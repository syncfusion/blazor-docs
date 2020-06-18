---
title: "Native Event"
component: "ProgressButton"
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

We have provided the following native event support to the ProgressButton component:

| List of Native events |  |  | |
| --- | --- | --- | --- |
| onclick | onblur | onfocus | onfocusout |
|onmousemove|onmouseover|onmouseout|onmousedown|onmouseup|
|ondblclick|onkeydown|onkeyup|onkeypress|
|ontouchend|onfocusin|onmouseup|ontouchstart|

## How to bind click event to ProgressButton

The ‘onclick’ attribute is used to bind the click event for progress button. Here, we have explained about the sample code snippets of progress button.

`Default.razor`

```csharp
@using Syncfusion.EJ2.RazorComponents.Buttons

<EjsProgressButton Content="Spin Left" IsPrimary="true" Onclick="@onclick" ></EjsProgressButton>

@code {

    private void onclick(UIMouseEventArgs args)
    {
            //onclick Event triggered
    }
}

```
