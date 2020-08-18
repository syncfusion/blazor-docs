---
title: "FirstDayWeek"
component: "Calendar"
description: "Explains how to change the first day of a week in the calendar component."
---

# Change the first day of the week

The Calendar provides an option to change the first day of the week by using the [FirstDayOfWeek](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Calendars.CalendarBase%601~FirstDayOfWeek.html)
property. Generally, the day of the week starts from 0 (Sunday) and ends with 6 (Saturday).

> By default, the first day of the week is culture specific.

The following code shows the Calendar with `Tuesday` as the first day of the week.

```csharp
@using Syncfusion.Blazor.Calendars

<SfCalendar TValue="DateTime?" FirstDayOfWeek=2></SfCalendar>
```

The output will be as follows.

![calendar](../images/first-day-of-week.png)
