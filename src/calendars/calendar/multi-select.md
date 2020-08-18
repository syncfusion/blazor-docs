---
title: "Multi Selection"
component: Calendar
description: "Explains how to achieve the multiple date selection in the calendar component to select single or multiple date values (sequence or random date selection)."
---

# Multi Selection

A calendar provides an option to select **single** or **multiple dates** by using the [IsMultiSelection](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Calendars.SfCalendar%601~Values.html) properties. By default, the IsMultiSelection property will be in disabled state.

The following code demonstrates the functionality of IsMultiSelection and Values properties in the Calendar component.

```csharp
@using Syncfusion.Blazor.Calendars

<SfCalendar TValue="DateTime?" IsMultiSelection=true Values="@MultipleValues"></SfCalendar>

@code {
public DateTime[] MultipleValues { get; set; } = new DateTime[] { new DateTime(DateTime.Now.Year, DateTime.Now.Month, 10),
        new DateTime(DateTime.Now.Year, DateTime.Now.Month, 15),
        new DateTime(DateTime.Now.Year, DateTime.Now.Month, 25) };
}
```

The output will be as follows.

![calendar](./images/multi-selection.png)
