---
title: "All-day scroller"
component: "Scheduler"
description: "This section explains how to enable scroller for all-day row in the scheduler"
---

# Enable scroll option on all-day section

When you have larger number of appointments in all-day row, it is difficult to view all the appointments properly. In that case you can enable scroller option for all-day row by setting true to `EnableAllDayScroll` whereas its default value is false. When setting this property to true, individual scroller for all-day row is enabled when it reaches its maximum height on expanding.

> Note: This property is not applicable for Scheduler with height `auto`.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" Height="550px" EnableAllDayScroll="true" @bind-SelectedDate="@CurrentDate">
    <ScheduleEventSettings DataSource="@generateObject()"></ScheduleEventSettings>
    <ScheduleViews>
        <ScheduleView Option="View.Day"></ScheduleView>
        <ScheduleView Option="View.Week"></ScheduleView>
        <ScheduleView Option="View.WorkWeek"></ScheduleView>
        <ScheduleView Option="View.Month"></ScheduleView>
        <ScheduleView Option="View.Agenda"></ScheduleView>
    </ScheduleViews>
</SfSchedule>
@code{
    SfSchedule<ScheduleData.RoomData> ScheduleObj;
    private View CurrentView = View.Week;
    public DateTime CurrentDate = new DateTime(2021, 6, 29);
    public List<AppointmentData> generateObject()
    {
        List<AppointmentData> appData = new List<AppointmentData>(25);
        for (int a = 0; a <= 25; a++)
        {
            appData.Add(new AppointmentData
            {
                Id = a + 1,
                Subject = "Testing",
                StartTime = new DateTime(2021, 6, 29, 0, 0, 0),
                EndTime = new DateTime(2021, 6, 30, 0, 0, 0),
                IsAllDay = true
            });
        }
        return appData;
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

The Scheduler with enable all-day scroll will be rendered as shown in the following image.

![Scroller in all-day row](../images/all-day-scroll.png)