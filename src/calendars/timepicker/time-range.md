---
title: "Time Range"
component: "TimePicker"
description: "Explains how to specify min and max time options in the time picker component to restrict the users from selecting a value out of given min/max time range."
---

# Time Range

TimePicker provides an option to select a time value within a specified range by using the
[Min](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Calendars.SfTimePicker~Min.html)
and
[Max](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Calendars.SfTimePicker~Max.html)
properties. The Min value should always be
lesser than the Max value.

The `Value` property depends on the Min/Max with respect to [StrictMode](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Calendars.SfTimePicker~StrictMode.html) property.
The following code allows you to select a time value within a range of `9:00 AM` to `11:30 AM`. For more information about StrictMode, refer to the [Strict Mode](./strict-mode) section from the documentation.

```csharp
@using Syncfusion.Blazor.Calendars

<SfTimePicker TValue="DateTime?" Value='@TimeValue' Min='@MinVal' Max='@MaxVal'></SfTimePicker>

@code{
    public DateTime MinVal { get; set; } = new DateTime(DateTime.Now.Year, DateTime.Now.Month, 15, 09, 00, 00);
    public DateTime MaxVal { get; set; } = new DateTime(DateTime.Now.Year, DateTime.Now.Month, 15, 11, 30, 00);
    public DateTime? TimeValue { get; set; } = new DateTime(DateTime.Now.Year, DateTime.Now.Month, 15, 11, 00, 00);
}

```

The output will be as follows.

![timepicker](./images/time_range.png)

When the `Min` and `Max` properties are configured and the selected time value is out-of-range or
invalid, then the model value will be set to `out of range` time value or `null` respectively
with highlighted `error` class to indicates the time is out of range or invalid.

```csharp
@using Syncfusion.Blazor.Calendars

<SfTimePicker TValue="DateTime?" Value='@TimeValue' Min='@MinVal' Max='@MaxVal'></SfTimePicker>

@code{
    public DateTime MinVal { get; set; } = new DateTime(DateTime.Now.Year, DateTime.Now.Month, 15, 09, 00, 00);
    public DateTime MaxVal { get; set; } = new DateTime(DateTime.Now.Year, DateTime.Now.Month, 15, 11, 30, 00);
    public DateTime? TimeValue { get; set; } = new DateTime(DateTime.Now.Year, DateTime.Now.Month, 15, 11, 40, 00);
}
```

The output will be as follows.

![timepicker](./images/time_range_02.png)

> If the value of `Min` or `Max` property is changed through code behind, you have to
update the `Value` property to set within the range.
