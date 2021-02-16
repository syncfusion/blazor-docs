# Overview

The following section explains steps to include native events and pass data to event handler in the DateRangePicker component.

## Bind native events to DateRangePicker

You can access any native event by using on `<event>` attribute with a component. The attribute's value is treated as an event handler.

In the following example, the KeyPressed method is called every time the key is pressed on input.

```csharp
@using Syncfusion.Blazor.Calendars

<SfDateRangePicker TValue="DateTime?" @onkeypress='@KeyPressed'></SfDateRangePicker>

@code {
    public void KeyPressed(){
      Console.WriteLine("Key Pressed!");
  }
}
```

Also, you can rewrite the above example code as follows using Lambda expressions.

```csharp
@using Syncfusion.Blazor.Calendars

<SfDateRangePicker TValue="DateTime?" @onkeypress="@(() => Console.WriteLine("Key Pressed!"))"></SfDateRangePicker>
```

## Pass event data to event handler

Blazor provides set of argument types to map to native events. the list of event types and event arguments are:

* Focus Events - FocusEventArgs
* Mouse Events - MouseEventArgs
* Keyboard Events - KeyboardEventArgs
* Input Events - ChangeEventArgs/EventArgs
* Touch Events – TouchEventArgs
* Pointer Events – PointerEventArgs

In the following example, the KeyPressed method is called every time any key is pressed inside input. But the message will be printed when you press "5" key.

```csharp
@using Syncfusion.Blazor.Calendars

<SfDateRangePicker TValue="DateTime?" @onkeypress='@(e => KeyPressed(e))'></SfDateRangePicker>

@code {
    public void KeyPressed(KeyboardEventArgs args)
    {
        if (args.Key == "5")
        {
            Console.WriteLine("5 was pressed");
        }
    }
}
```

Using Lambda expression also, you can pass the event data to the event handler.

## List of Native events supported

| List of Native events |  |  | |
| --- | --- | --- | --- |
| onclick | onblur | onfocus | onfocusout |
| onmousemove | onmouseover | onmouseout | onmousedown | onmouseup |
| ondblclick | onkeydown | onkeyup | onkeypress |
| ontouchend | onfocusin | onmouseup | ontouchstart |
