---
title: "Native Event"
component: "RadioButton"
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

We have provided the following native event support to the RadioButton component:

| List of Native events |  |  | | |
| --- | --- | --- | --- | --- |
| onchange | oninput | onblur | onfocus | onfocusout |
|onfocusin|onclick|onkeydown|onkeyup|Onkeypress |

## How to bind click event to RadioButton

The ‘onclick’ attribute is used to bind the click event for radio button. Here, we have explained about the sample code snippets of radio button.

`Default.razor`

```csharp
@using Syncfusion.EJ2.RazorComponents.Buttons


<div class="row">
    <EjsRadioButton Label="Credit/Debit Card" Name="payment" Value="credit/debit" Onclick="@onclick" ></EjsRadioButton>
</div>
<div class="row">
    <EjsRadioButton Label="Net Banking" Name="payment" Value="netbanking"></EjsRadioButton>
</div>

@code {
    private void onclick(UIMouseEventArgs args){
    //onclick Event triggered
   }
}

```
