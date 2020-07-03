# Create Multiple Events in different time slots through CTRL key

In Blazor Scheduler, we can able to select the different time slots(10:00 - 10:30, 8:00 - 8:30) by holding CTRL key and click on cells using `OnCellClick` event. In the following code example, events are created on selected timeslots when clicking the **Add Appointments** button.

```csharp
@using Syncfusion.Blazor
@using Syncfusion.Blazor.Schedule
@using Syncfusion.Blazor.Buttons

<SfButton OnClick="OnButtonClick">Add Appointments</SfButton>
<SfSchedule @ref="ScheduleObj" TValue="AppointmentData" Width="100%" Height="650px" SelectedDate="@(new DateTime(2020, 3, 10))">
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
    <ScheduleEvents TValue="AppointmentData" OnCellClick="OnCellClicked"></ScheduleEvents>
</SfSchedule>

<style>

    .e-schedule .e-month-view .e-work-cells.custom-class,
    .e-schedule .e-vertical-view .e-work-cells.custom-class {
        background: #e0e0e0;
    }
</style>

@code{
    SfSchedule<AppointmentData> ScheduleObj;
    public List<CellClickEventArgs> CellDetails = new List<CellClickEventArgs>();
    public List<DOM> ElementDetails = new List<DOM>();
    public string[] CustomClass = { "custom-class" };
    public async void OnCellClicked(CellClickEventArgs args)
    {
        if (args.Event.CtrlKey == true) //to check whether CTRL key is pressed
        {
            args.Cancel = true;   //to prevent default action
            args.Element.AddClass(CustomClass); // to add the background color for selected cells
            ElementDetails.Add(args.Element);
            CellClickEventArgs cell = await this.ScheduleObj.GetCellDetails(args.Element); //to get the current cell details
            CellDetails.Add(cell);
        }
    }

    public void OnButtonClick()
    {
        for (int i = 0; i < cellDetails.Count; i++)
        {
            Random rnd = new Random();
            int Id = rnd.Next(1000);
            List<AppointmentData> newData = new List<AppointmentData>();
            newData.Add(new AppointmentData
            {
                Id = Id,
                Subject = "Added events",
                StartTime = cellDetails[i].StartTime,
                EndTime = cellDetails[i].EndTime
            });
            this.ScheduleObj.AddEvent(newData);  //to add appointments to the scheduler
            ElementDetails[i].RemoveClass(CustomClass); // to remove the background color for selected cells
        }
        CellDetails.Clear();
    }

    List<AppointmentData> DataSource = new List<AppointmentData>
    {
        new AppointmentData { Id = 1, Subject = "Eclipse", StartTime = new DateTime(2020, 3, 9, 9, 30, 0) , EndTime = new DateTime(2020, 3, 9, 11, 0, 0) },
        new  AppointmentData { Id = 2, Subject = "Crash", StartTime = new DateTime(2020, 3, 11, 11, 30, 0), EndTime = new DateTime(2020, 3, 11, 13, 0, 0)}
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