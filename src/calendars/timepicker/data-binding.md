---
component: "TimePicker"
---

# Data Binding

This section briefly explains how to bind the value to the TimePicker component in the below different ways.

* One-Way Data Binding
* Two-Way Data Binding
* Dynamic Value Binding

## One-Way Binding

We can bind the value to the TimePicker component directly for `Value` property as mentioned in the following code example. In one-way binding, we need to pass property or variable name along with `@` (For Ex: "@DateValue").

```csharp
@using Syncfusion.Blazor.Calendars

<SfTimePicker TValue="DateTime?" Value="@DateValue"></SfTimePicker>

<button @onclick="@UpdateValue">Update Value</button>

@code {
    public DateTime DateValue { get; set; } = new DateTime(DateTime.Now.Year, DateTime.Now.Month, 28, 12, 30, 00);

    public void UpdateValue()
    {
        DateValue = DateTime.Now;
    }
}
```

## Two-Way Data Binding

Two-way binding can be achieved by using `bind-Value` attribute and its supports string, int, Enum, DateTime, bool types. If component value has been changed, it will affect the all places where we bind the variable for the **bind-value** attribute.

```csharp
@using Syncfusion.Blazor.Calendars

<p>TimePicker value is: @DateValue</p>

<SfTimePicker TValue="DateTime?" @bind-Value="@DateValue"></SfTimePicker>

    @code {
        public DateTime? DateValue { get; set; } = DateTime.Now;
    }
```

## Dynamic Value Binding

We can change the property value dynamically by manually calling the `StateHasChanged()` method inside public event of **Blazor TimePicker component** only. This method notifies the component that its state has changed and queues a re-render.

There is no need to call this method for native events since it’s called after any lifecycle method has been called and can also be invoked manually to trigger a re-render. Please refer the below mentioned code example.

```csharp
@using Syncfusion.Blazor.Calendars

<p>TimePicker value is: @TimeValue</p>

<SfTimePicker TValue="DateTime?" Value="@TimeValue">
    <TimePickerEvents TValue="DateTime?" ValueChange="@onChange"></TimePickerEvents>
</SfTimePicker>

@code {

    public DateTime? TimeValue { get; set; } = DateTime.Now;

    private void onChange(Syncfusion.Blazor.Calendars.ChangeEventArgs<DateTime?> args)
    {
        TimeValue = args.Value;
        StateHasChanged();
    }
}
```
