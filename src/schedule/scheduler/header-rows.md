---
title: "Timeline header rows in Blazor Scheduler"
component: "Scheduler"
description: "This section explains how to display the additional header rows on timeline view of Scheduler."
---

# Timeline header rows

The Timeline views can have additional header rows other than its default date and time header rows. It is possible to show individual header rows for displaying year, month and week separately using the `ScheduleHeaderRow` which is applicable only on the timeline views. The possible rows which can be added using `ScheduleHeaderRow` are as follows.

* `Year`
* `Month`
* `Week`
* `Date`
* `Hour`

> The `Hour` row is not applicable for Timeline month view.

The following example shows the Scheduler displaying all the available header rows on timeline views.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" Height="650px">
    <ScheduleHeaderRows>
        <ScheduleHeaderRow Option="HeaderRowType.Year"></ScheduleHeaderRow>
        <ScheduleHeaderRow Option="HeaderRowType.Month"></ScheduleHeaderRow>
        <ScheduleHeaderRow Option="HeaderRowType.Week"></ScheduleHeaderRow>
        <ScheduleHeaderRow Option="HeaderRowType.Date"></ScheduleHeaderRow>
        <ScheduleHeaderRow Option="HeaderRowType.Hour"></ScheduleHeaderRow>
    </ScheduleHeaderRows>
    <ScheduleViews>
        <ScheduleView Option="View.TimelineWeek"></ScheduleView>
    </ScheduleViews>
</SfSchedule>

@code{
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

## Display year and month rows in timeline views

To display the timeline Scheduler simply with year and month names alone, define the option `Year` and `Month` within the `ScheduleHeaderRow` property.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" Height="650px">
    <ScheduleHeaderRows>
        <ScheduleHeaderRow Option="HeaderRowType.Year"></ScheduleHeaderRow>
        <ScheduleHeaderRow Option="HeaderRowType.Month"></ScheduleHeaderRow>
    </ScheduleHeaderRows>
    <ScheduleViews>
        <ScheduleView Option="View.TimelineMonth" Interval="24"></ScheduleView>
    </ScheduleViews>
</SfSchedule>

@code{
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

## Display week numbers in timeline views

The week number can be displayed in a separate header row of the timeline Scheduler by setting `Week` option within `ScheduleHeaderRow` property.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" Height="650px">
    <ScheduleHeaderRows>
        <ScheduleHeaderRow Option="HeaderRowType.Week"></ScheduleHeaderRow>
        <ScheduleHeaderRow Option="HeaderRowType.Date"></ScheduleHeaderRow>
        <ScheduleHeaderRow Option="HeaderRowType.Hour"></ScheduleHeaderRow>
    </ScheduleHeaderRows>
    <ScheduleViews>
        <ScheduleView Option="View.TimelineWeek"></ScheduleView>
        <ScheduleView Option="View.TimelineMonth"></ScheduleView>
    </ScheduleViews>
</SfSchedule>

@code{
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

## Timeline view displaying dates of a complete year

It is possible to display a complete year in a timeline view by setting `Interval` value as 12 and defining **TimelineMonth** view option within the `ScheduleView` tag helper.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" Height="650px">
    <ScheduleHeaderRows>
        <ScheduleHeaderRow Option="HeaderRowType.Month"></ScheduleHeaderRow>
        <ScheduleHeaderRow Option="HeaderRowType.Date"></ScheduleHeaderRow>
    </ScheduleHeaderRows>
    <ScheduleViews>
        <ScheduleView Option="View.TimelineMonth" Interval="12"></ScheduleView>
    </ScheduleViews>
</SfSchedule>

@code{
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
