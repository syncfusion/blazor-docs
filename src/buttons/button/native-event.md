---
title: "Native Event"
component: "Button"
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

We have provided the following native event support to the Button component:

| List of Native events |  |  | |
| --- | --- | --- | --- |
| onclick | onblur | onfocus | onfocusout |
|onmousemove|onmouseover|onmouseout|onmousedown|onmouseup|
|ondblclick|onkeydown|onkeyup|onkeypress|
|ontouchend|onfocusin|onmouseup|ontouchstart|

## How to bind click event to Button

The ‘onclick’ attribute is used to bind the click event for button. Here, we have explained about the sample code snippets of toggle button.

`Default.razor`

```csharp
@using Syncfusion.EJ2.RazorComponents.Buttons

<EjsButton ID="togglebtn" @ref="togglebtn" Onclick="@onToggleClick" CssClass="e-flat" IsToggle="true" IsPrimary="true" Content="@content" IconCss="@iconCss"></EjsButton>

@code {
    EjsButton togglebtn;
    public string content = "Play";
    public string iconCss = "e-btn-sb-icons e-play-icon";
    private void onToggleClick(UIMouseEventArgs args)
    {
        if (togglebtn.Content == "Play")
        {
            this.content = "Pause";
            this.iconCss = "e-btn-sb-icons e-pause-icon";
        }
        else
        {
            this.content = "Play";
            this.iconCss = "e-btn-sb-icons e-play-icon";
        }
        togglebtn.Content = this.content;
        togglebtn.IconCss = this.iconCss;
        togglebtn.DataBind();
    }
}
```
