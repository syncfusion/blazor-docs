---
title: "Customization"
component: "DateRangePicker"
description: "Explains how to achieve UI level customization in the date range picker component such as day cell format, preset ranges, and more."
---

# Customization

The DateRangePicker is available for UI customization that can be achieved by using the available properties and events in the component.

## First day of week

Start day in a week will differ based on the culture, but you can also customize this based on the application needs.
For this, use the [FirstDayOfWeek](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Calendars.DateRangePickerModel~FirstDayOfWeek.html) property.
By default, first day of a week in en-US is Sunday. In the following example, it is customized to Wednesday with the help of this property.

```csharp
@using Syncfusion.Blazor.Calendars

<SfDateRangePicker Placeholder="Select a range" FirstDayOfWeek=3></SfDateRangePicker>
```

The output will be as follows.

![DateRangePicker](./images/first_day_of_week.png)
