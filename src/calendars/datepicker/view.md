---
title: "Date Views"
component: "DatePicker"
description: "Explains how to specify start and depth view options in the date picker component to restrict the calendar view navigation (month picker or year picker)."
---

# Start and Depth View

The DatePicker has the following predefined views
that provides a flexible way to navigate back and forth to select the date:

| **View** | **Description** |
| --- | --- |
| Month (default) | Displays the days in a month. |
| Year | Displays the months in a year. |
| Decade | Displays the years in a decade. |

## Start view

You can use the [Start](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Calendars.CalendarBase%601~Start.html) property to define the initial rendering view.

The following example demonstrates how to create a DatePicker with `Decade` as initial rendering view.

```csharp
@using Syncfusion.Blazor.Calendars

<SfDatePicker TValue="DateTime?" Value='@DateValue' Placeholder='Select a date' Start='CalendarView.Decade'></SfDatePicker>

@code {
    public DateTime? DateValue {get;set;} = DateTime.Now;
}
```

The output will be as follows.

![datepicker](./images/view.png)

## Depth view

Define the [Depth](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Calendars.CalendarBase%601~Depth.html) property to control the view navigation.

> Always the Depth view has to be smaller than the Start view, otherwise the view restriction
will be not restricted.

The following example demonstrates how to create a DatePicker that allows users to select a month.

```csharp
@using Syncfusion.Blazor.Calendars

<SfDatePicker TValue="DateTime?" Value='@DateValue' Placeholder='choose a date' Start='CalendarView.Decade' Depth='CalendarView.Year'></SfDatePicker>

@code {
    public DateTime? DateValue { get; set; } = DateTime.Now;
}
```

> To learn more about Calendar views, refer to the Calendar's
[Calendar Views](../calendar/calendar-views/)
section.
