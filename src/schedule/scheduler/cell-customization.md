---
title: "Customizing Scheduler Cells"
component: "Blazor Scheduler"
description: "This topic demonstrates how to customize the cells of Scheduler using template option, methods and events available in Scheduler."
---

# Cell Customization

The cells of the Scheduler can be easily customized using the cell template.

## Setting cell dimensions in Vertical Views

The height and width of the Scheduler cells can be customized either to increase or reduce its size through the `CssClass` property, which overrides the default CSS applied on cells of vertical views.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" CssClass="schedule-cell-dimension" Height="550px">
</SfSchedule>

<style>
    .schedule-cell-dimension.e-schedule .e-vertical-view .e-date-header-wrap table col,
    .schedule-cell-dimension.e-schedule .e-vertical-view .e-content-wrap table col {
        width: 200px;
    }

    .schedule-cell-dimension.e-schedule .e-vertical-view .e-time-cells-wrap table td,
    .schedule-cell-dimension.e-schedule .e-vertical-view .e-work-cells {
        height: 100px;
    }

    .schedule-cell-dimension.e-schedule .e-month-view .e-work-cells,
    .schedule-cell-dimension.e-schedule .e-month-view .e-date-header-wrap table col {
        width: 200px;
    }

    .schedule-cell-dimension.e-schedule .e-month-view .e-work-cells {
        height: 200px;
    }
</style>
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

## Setting cell dimensions in Timeline Views

The height and width of the Scheduler cells can be customized either to increase or reduce its size through the `CssClass` property, which overrides the default CSS applied on cells of timeline views.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" CssClass="schedule-cell-dimension" Height="550px">
    <ScheduleViews>
        <ScheduleView Option="View.TimelineWeek"></ScheduleView>
        <ScheduleView Option="View.TimelineMonth"></ScheduleView>
    </ScheduleViews>
</SfSchedule>

<style>
    .schedule-cell-dimension.e-schedule .e-timeline-view .e-date-header-wrap table col,
    .schedule-cell-dimension.e-schedule .e-timeline-view .e-content-wrap table col {
        width: 200px;
    }

    .schedule-cell-dimension.e-schedule .e-timeline-month-view .e-date-header-wrap table col,
    .schedule-cell-dimension.e-schedule .e-timeline-month-view .e-content-wrap table col {
        width: 200px;
    }
</style>
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

## Customizing cells using CellTemplate

The `CellTemplate` is used to customize the cell background with specific images or appropriate text on the given date values.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" Width="100%" Height="650px" SelectedDate="@(new DateTime(2020, 1, 15))">
    <ScheduleTemplates>
        <CellTemplate>
            <div class="templatewrap">
                @{
                    @if ((int)(context as TemplateContext).Date.Month == 11 && (int)(context as TemplateContext).Date.Day == 23)
                    {
                        <div class="caption">Thanksgiving day</div>
                    }
                    @if ((int)(context as TemplateContext).Date.Month == 12 && (int)(context as TemplateContext).Date.Day == 9)
                    {
                        <div class="caption">Party time</div>
                    }
                    @if ((int)(context as TemplateContext).Date.Month == 12 && (int)(context as TemplateContext).Date.Day == 13)
                    {
                        <div class="caption">Party time</div>
                    }
                    @if ((int)(context as TemplateContext).Date.Month == 12 && (int)(context as TemplateContext).Date.Day == 22)
                    {
                        <div class="caption">Happy birthday</div>
                    }
                    @if ((int)(context as TemplateContext).Date.Month == 12 && (int)(context as TemplateContext).Date.Day == 24)
                    {
                        <div class="caption">Christmas Eve</div>
                    }
                    @if ((int)(context as TemplateContext).Date.Month == 12 && (int)(context as TemplateContext).Date.Day == 25)
                    {
                        <div class="caption">Christmas day</div>
                    }
                    @if ((int)(context as TemplateContext).Date.Month == 1 && (int)(context as TemplateContext).Date.Day == 1)
                    {
                        <div class="caption">New Year"s Day</div>
                    }
                    @if ((int)(context as TemplateContext).Date.Month == 1 && (int)(context as TemplateContext).Date.Day == 14)
                    {
                        <div class="caption">Get together</div>
                    }
                }
            </div>
        </CellTemplate>
    </ScheduleTemplates>
    <ScheduleViews>
        <ScheduleView Option="View.Month"></ScheduleView>
    </ScheduleViews>
</SfSchedule>
<style>
    .e-schedule .e-month-view .e-work-cells {
        position: relative;
    }
    .e-schedule .templatewrap {
        text-align: center;
        position: absolute;
        width: 100%;
    }
    .e-schedule .caption {
        overflow: hidden;
        text-overflow: ellipsis;
        vertical-align: middle;
    }
</style>

@code {
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