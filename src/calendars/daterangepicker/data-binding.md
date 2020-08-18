---
title: "Data-Binding"
component: "DateRangePicker"
description: "This section helps to learn how to bind the value in ASP.NET Core Blazor application"
---

# Data Binding

This section briefly explains how to bind the value to the DateRangePicker component in the below different ways.

* One-Way Data Binding
* Two-Way Data Binding
* Dynamic Value Binding

## One-Way Binding

We can bind the value to the DateRangePicker component directly for `StartDate` and `EndDate` property as mentioned in the following code example. In one-way binding, we need to pass property or variable name along with `@` (For Ex: "@StartValue").

```csharp
@using Syncfusion.Blazor.Calendars

<SfDateRangePicker StartDate="@StartValue" EndDate="@EndValue"></SfDateRangePicker>

<button @onclick="@UpdateValue">Update Value</button>

@code {

    public DateTime StartValue { get; set; } = new DateTime(DateTime.Now.Year, DateTime.Now.Month, 28);

    public DateTime EndValue { get; set; } = new DateTime(DateTime.Now.Year, DateTime.Now.Month + 1, 28);

    public void UpdateValue()
    {
        StartValue = new DateTime(DateTime.Now.Year + 1, DateTime.Now.Month, 28);
        EndValue = new DateTime(DateTime.Now.Year + 1, DateTime.Now.Month + 1, 28);
    }
}
```

## Two-Way Data Binding

Two-way binding can be achieved by using `bind-StartDate` and `bind-EndDate` attribute and its supports string, int, Enum, DateTime, bool types. If component value has been changed, it will affect the all places where we bind the variable for the **bind-StartDate** and **bind-EndDate**attribute.

```csharp
@using Syncfusion.Blazor.Calendars

<p>DateRangePickers StarteDate and EndDate is: <strong>@StartValue</strong> and <strong>@EndValue</strong></p>

<SfDateRangePicker @bind-StartDate="@StartValue" EndDate="@EndValue" ></SfDateRangePicker>

@code {

public DateTime? StartValue { get; set; } = DateTime.Now;

public DateTime? EndValue { get; set; } = DateTime.Now;
}
```

## Dynamic Value Binding

We can change the property value dynamically by manually calling the `StateHasChanged()` method inside public event of **Blazor DateRangePicker component** only. This method notifies the component that its state has changed and queues a re-render.

There is no need to call this method for native events since it’s called after any lifecycle method has been called and can also be invoked manually to trigger a re-render. Please refer the below mentioned code example.

```csharp
@using Syncfusion.Blazor.Calendars

<p>DateRangePicker StarteDate and EndDate is: <strong> @StartValue </strong> and <strong> @EndValue </strong></p>

<SfDateRangePicker StartDate="@StartValue" EndDate="@EndValue">
<DateRangePickerEvents ValueChange="@onChange"></DateRangePickerEvents>
</SfDateRangePicker>

@code {

public DateTime StartValue { get; set; } = DateTime.Now;

public DateTime EndValue { get; set; } = DateTime.Now;

private void onChange(RangeEventArgs args)
{
    StartValue = args.StartDate;
    EndValue = args.EndDate;
    StateHasChanged();
}
}
```
