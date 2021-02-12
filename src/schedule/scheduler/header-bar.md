---
component: "Blazor Scheduler"
---

# Header customization

The header part of Scheduler can be customized easily with the built-in options available.

## Show or Hide header bar

By default, the header bar holds the date and view navigation options, through which the user can switch between the dates and various views. This header bar can be hidden from the UI by setting `false` to the `ShowHeaderBar` property. It's default value is `true`.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" ShowHeaderBar="false" Height="550px" @bind-SelectedDate="@CurrentDate">
</SfSchedule>

@code{
    DateTime CurrentDate = new DateTime(2020, 1, 31);
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

## Date header customization

The Scheduler UI that displays the date text on all views are considered as the date header cells. You can customize the date header cells of Scheduler using `DateHeaderTemplate`. The `DateHeaderTemplate` option is used to customize the date header cells of day, week and work-week views.

```csharp
@using Syncfusion.Blazor.Schedule
@using System.Globalization

<SfSchedule TValue="AppointmentData" Width="100%" CssClass="schedule-date-header-template" Height="650px" @bind-SelectedDate="@CurrentDate">
    <ScheduleTemplates>
        <DateHeaderTemplate>
            <div class="date-text">@(getDateHeaderText((context as TemplateContext).Date))</div>
            @{
                @switch ((int)(context as TemplateContext).Date.DayOfWeek)
                {
                    case 0:
                        <div class="weather-text">25&deg;C</div>
                        break;
                    case 1:
                        <div class="weather-text">18&deg;C</div>
                        break;
                    case 2:
                        <div class="weather-text">10&deg;C</div>
                        break;
                    case 3:
                        <div class="weather-text">16&deg;C</div>
                        break;
                    case 4:
                        <div class="weather-text">8&deg;C</div>
                        break;
                    case 5:
                        <div class="weather-text">27&deg;C</div>
                        break;
                    case 6:
                        <div class="weather-text">17&deg;C</div>
                        break;
                }
            }
        </DateHeaderTemplate>
    </ScheduleTemplates>
    <ScheduleViews>
        <ScheduleView Option="View.Day"></ScheduleView>
        <ScheduleView Option="View.Week"></ScheduleView>
        <ScheduleView Option="View.WorkWeek"></ScheduleView>
    </ScheduleViews>
</SfSchedule>

@code {
    DateTime CurrentDate = new DateTime(2020, 1, 10);
    public static string getDateHeaderText(DateTime date)
    {
        return date.ToString("dd ddd", CultureInfo.InvariantCulture);
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
<style>
    .schedule-date-header-template.e-schedule .e-vertical-view .e-header-cells {
        padding: 0;
        text-align: center !important;
    }

    .schedule-date-header-template.e-schedule .date-text {
        font-size: 14px;
    }

    .schedule-date-header-template.e-schedule.e-device .date-text {
        font-size: 12px;
    }

    .schedule-date-header-template.e-schedule .weather-image {
        width: 20px;
        height: 20px;
        background-position: center center;
        background-repeat: no-repeat;
        background-size: cover;
    }

    .schedule-date-header-template.e-schedule .weather-text {
        font-size: 11px;
    }
</style>
```

### Customization using OnRenderCell event

We can also customize the date header by using `OnRenderCell` event. In the `OnRenderCell`, the argument `RenderCellEventArgs` returns the `ElementType` as `DateHeader` when the date header is rendering. In the following example, we customized the date header's background color.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" Width="100%" Height="550px" @bind-SelectedDate="@CurrentDate">
    <ScheduleEvents TValue="AppointmentData" OnRenderCell="OnRenderCell"></ScheduleEvents>
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
</SfSchedule>
<style>
    .e-schedule .e-vertical-view .e-date-header-wrap table tbody td.e-header-cells {
        background-color: ivory;
    }
</style>

@code{
    private DateTime CurrentDate = new DateTime(2020, 3, 10);
    public string[] CustomClass = { "custom-class" };
    public void OnRenderCell(RenderCellEventArgs args)
    {
        //Here you can customize with your code
        if (args.ElementType == ElementType.DateHeader)
        {
            args.CssClasses = new List<string>(CustomClass);
        }
    }
    List<AppointmentData> DataSource = new List<AppointmentData>
    {
        new AppointmentData { Id = 1, Subject = "Meeting", StartTime = new DateTime(2020, 3, 10, 9, 30, 0) , EndTime = new DateTime(2020, 3, 10, 12, 0, 0) }
    };
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