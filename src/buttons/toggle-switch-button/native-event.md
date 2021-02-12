---
component: "Toggle Switch Button"
---

# Overview

You can define the native event using on `event` attribute in component. The value of attribute is treated as an event handler. The event specific data will be available in event arguments.

The different event argument types for each event are,

* Focus Events - UIFocusEventArgs
* Mouse Events - UIMouseEventArgs
* Keyboard Events - UIKeyboardEventArgs
* Touch Events – UITouchEventArgs

## List of Native events supported

We have provided the following native event support to the Toggle Switch Button component:

| List of Native events |  |  | | | |
| --- | --- | --- | --- | --- | --- |
|onfocus|onfocusout|onfocusin|onkeydown|onkeyup|Onkeypress|

## How to bind focus event to Toggle Switch Button

The `onfocus` attribute is used to bind the focus event for Toggle Switch Button. Here, we have explained about the sample code snippets of Toggle Switch Button.

```csharp
@using Syncfusion.Blazor.Buttons

<label>onfocus</label>
<SfSwitch @onfocus="onFocus" @bind-Checked="isChecked"></SfSwitch>

@code {
    private bool isChecked = true;
}

@code {

    private void onFocus(Microsoft.AspNetCore.Components.Web.FocusEventArgs args)
    {
       //onfocus Event triggered
    }
}

```