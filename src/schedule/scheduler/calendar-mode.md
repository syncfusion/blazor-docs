---
title: "Calendar Mode in Blazor Scheduler"
component: "Scheduler"
description: "This section explains how to change the default calendar mode on Scheduler to display it either on Gregorian or Islamic mode."
---

# Calendar mode

The Scheduler supports the following two types of calendar mode.

* Gregorian Calendar
* Islamic Calendar

## Gregorian Calendar

The Scheduler by default displays the Gregorian calendar dates which is the most widely used calendar in the world. The Gregorian calendar is a solar calendar which has 12 months with 28 to 31 days each. A year which is divisible by four is said to be a leap year in this calendar mode. A leap year usually has 366 days whereas the regular year has 365 days.

## Islamic Calendar

The Islamic Calendar, also known as the Hijri or Muslim calendar, is a lunar calendar which has 12 months in a year with 354 or 355 days. Each month of this calendar denotes the birth of the new lunar cycle and therefore, each month can have 29 or 30 days depending on the visibility of the moon. Here, the odd-numbered months have 30 days and the even months have 29 days.

The Scheduler has a property `CalendarMode` which is used to switch between the gregorian and islamic calendar modes. By default, it is set to `Gregorian` and to use it with Islamic calendar dates, define the `CalendarMode` of Scheduler to `Islamic`. The following example depicts, how to display the Islamic calendar dates on Scheduler.

It requires the following CLDR data to be loaded using loadCldr function.

* numberingSystems.json
* ca-gregorian.json
* numbers.json
* timeZoneNames.json
* ca-islamic.json

```csharp
@using Syncfusion.Blazor
@using Syncfusion.Blazor.Schedule
@using Microsoft.JSInterop

<SfSchedule TValue="AppointmentData" Height="650px" EnableRtl="true" CalendarMode="CalendarType.Islamic">
</SfSchedule>
@code {
    [Inject]
    IJSRuntime JsRuntime { get; set; }
    protected override void OnAfterRender(bool firstRender)
    {
         this.JsRuntime.Sf().LoadLocaleData("wwwroot/sf-locale/src/ar.json").SetCulture("ar").LoadCldrData(new string[] { "wwwroot/cldr-data/main/ar/ca-gregorian.json", "wwwroot/cldr-data/main/ar/ca-islamic.json", "wwwroot/cldr-data/main/ar/timeZoneNames.json", "wwwroot/cldr-data/main/ar/numberingSystems.json", "wwwroot/cldr-data/main/ar/numbers.json" })
    }
    public class AppointmentData
    {
        public int Id { get; set; }
        public string Subject { get; set; }
        public string Location { get; set; }
        public DateTime StartTime { get; set; }
        public DateTime EndTime { get; set; }
        public string Description { get; set; }
        public bool IsAllDay { get; set; }
        public string RecurrenceRule { get; set; }
        public string RecurrenceException { get; set; }
        public Nullable<int> RecurrenceID { get; set; }
    }
}
```
