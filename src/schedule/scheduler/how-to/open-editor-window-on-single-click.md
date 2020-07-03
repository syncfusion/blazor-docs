# Open Editor Window on Single Click

By default, the editor window will open on double clicking the cell or appointment. In the following code example, we have opened the editor window on single click using `OpenEditor` public method within `OnCellClick` and `OnEventClick` Scheduler events.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule @ref="ScheduleObj" TValue="AppointmentData" ShowQuickInfo="false" Height="550px" SelectedDate="@(new DateTime(2020, 3, 11))">
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
    <ScheduleEvents TValue="AppointmentData" OnCellClick="OnCellClick" OnEventClick="OnEventClick"></ScheduleEvents>
</SfSchedule>

@code{
    SfSchedule<AppointmentData> ScheduleObj;
    public async void OnCellClick(CellClickEventArgs args)
    {
        var cellData = await ScheduleObj.GetCellDetails(args.Element); //to get the current cell details
        await ScheduleObj.OpenEditor(cellData, CurrentAction.Add); //to open the editor on cell click
    }
    public async void OnEventClick(EventClickArgs<AppointmentData> args)
    {
        var eventData = await ScheduleObj.GetEventDetails(args.Element); //to get the current appointment details
        await ScheduleObj.OpenEditor(eventData, CurrentAction.Save); //to open the editor on event click
    }
    List<AppointmentData> DataSource = new List<AppointmentData>
    {
        new AppointmentData{ Id = 1, Subject = "Meeting", StartTime = new DateTime(2020, 3, 11, 9, 30, 0) , EndTime = new DateTime(2020, 3, 11, 11, 0, 0)}
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