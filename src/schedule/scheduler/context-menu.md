---
component: "Scheduler"
---

# Context Menu

You can display context menu on work cells and appointments of Scheduler by making use of the `ContextMenu` control manually from the application end. In the following code example, context menu control is being added from sample end and set its target as `Scheduler` and the target element is get by using `GetTargetElement` public method in Blazor.

On Scheduler cells, you can display the menu items such as `New Event`, `New Recurring Event` and `Today` option. For appointments, you can display its related options such as `Edit Event` and `Delete Event`. The default event window can be opened for appointment creation and editing using the `OpenEditor` method of Scheduler.

The deletion of appointments can be done by using the `DeleteEvent` public method. Also, the `SelectedDate` property can be used to navigate between different dates.

> You can also display custom menu options on Scheduler cells and appointments. Context menu will open on tap-hold in responsive mode.

```csharp
@using Syncfusion.Blazor.Schedule
@using Syncfusion.Blazor.Navigations

<SfSchedule TValue="AppointmentData" @ref="ScheduleRef" Height="650px" @bind-SelectedDate="@SelectedDate">
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
</SfSchedule>

<SfContextMenu TValue="MenuItem" @ref="ContextMenuObj" CssClass="schedule-context-menu" Target=".e-schedule">
    <MenuItems>
        <MenuItem Text="New Event" Id="Add" Hidden="@isCell"></MenuItem>
        <MenuItem Text="New Recurring Event" Hidden="@isCell" Id="AddRecurrence"></MenuItem>
        <MenuItem Text="Today" Id="Today" Hidden="@isCell"></MenuItem>
        <MenuItem Text="Edit Event" Id="Save" Hidden="@isEvent"></MenuItem>
        <MenuItem Text="Edit Event" Id="EditRecurrenceEvent" Hidden="@isRecurrence">
            <MenuItems>
                <MenuItem Text="Edit Occurrence" Id="EditOccurrence" Hidden="@isRecurrence"></MenuItem>
                <MenuItem Text="Edit Series" Id="EditSeries" Hidden="@isRecurrence"></MenuItem>
            </MenuItems>
        </MenuItem>
        <MenuItem Text="Delete Event" Id="Delete" Hidden="@isEvent"></MenuItem>
        <MenuItem Text="Delete Event" Id="DeleteRecurrenceEvent" Hidden="@isRecurrence">
            <MenuItems>
                <MenuItem Text="Delete Occurrence" Id="DeleteOccurrence" Hidden="@isRecurrence"></MenuItem>
                <MenuItem Text="Delete Series" Id="DeleteSeries" Hidden="@isRecurrence"></MenuItem>
            </MenuItems>
        </MenuItem>
    </MenuItems>
    <MenuEvents TValue="MenuItem" OnOpen="OnOpen" ItemSelected="OnItemSelected"></MenuEvents>
</SfContextMenu>

@code{
    private DateTime SelectedDate = new DateTime(2020, 1, 8);
    SfSchedule<AppointmentData> ScheduleRef;
    SfContextMenu<MenuItem> ContextMenuObj;
    private bool isCell { get; set; }
    private bool isEvent { get; set; }
    private bool isRecurrence { get; set; }

    public AppointmentData EventData { get; set; }
    public CellClickEventArgs CellData { get; set; }
    public async Task OnOpen(BeforeOpenCloseMenuEventArgs<MenuItem> args)
    {
        if (args.ParentItem == null)
        {
            CellData = await ScheduleRef.GetTargetCell((int)args.Left, (int)args.Top);
            if (CellData == null)
            {
                EventData = await ScheduleRef.GetTargetEvent((int)args.Left, (int)args.Top);
                if (EventData.Id == 0)
                {
                    args.Cancel = true;
                }
                if (EventData.RecurrenceRule != null)
                {
                    isCell = isEvent = true;
                    isRecurrence = false;
                }
                else
                {
                    isCell = isRecurrence = true;
                    isEvent = false;
                }
            }
            else
            {
                isCell = false;
                isEvent = isRecurrence = true;
            }
        }
    }
    public async Task OnItemSelected(MenuEventArgs<MenuItem> args)
    {
        var SelectedMenuItem = args.Item.Id;
        var ActiveCellsData = await ScheduleRef.GetSelectedCells();
        if (ActiveCellsData == null)
        {
            ActiveCellsData = CellData;
        }
        switch (SelectedMenuItem)
        {
            case "Today":
                SelectedDate = DateTime.Now;
                break;

            case "Add":
                await ScheduleRef.OpenEditor(ActiveCellsData, CurrentAction.Add);
                break;

            case "AddRecurrence":
                await ScheduleRef.OpenEditor(ActiveCellsData, CurrentAction.Add, RepeatType.Daily);
                break;

            case "Save":
                await ScheduleRef.OpenEditor(EventData, CurrentAction.Save);
                break;

            case "EditOccurrence":
                await ScheduleRef.OpenEditor(EventData, CurrentAction.EditOccurrence);
                break;

            case "EditSeries":
                List<AppointmentData> Events = await ScheduleRef.GetEvents();
                EventData = (AppointmentData)Events.Where(data => data.Id == EventData.RecurrenceID).FirstOrDefault();
                await ScheduleRef.OpenEditor(EventData, CurrentAction.EditSeries);
                break;

            case "Delete":
                await ScheduleRef.DeleteEvent(EventData);
                break;

            case "DeleteOccurrence":
                await ScheduleRef.DeleteEvent(EventData, CurrentAction.DeleteOccurrence);
                break;

            case "DeleteSeries":
                await ScheduleRef.DeleteEvent(EventData, CurrentAction.DeleteSeries);
                break;
        }
    }
    public List<AppointmentData> DataSource = new List<AppointmentData>
    {
        new AppointmentData { Id = 1, Subject = "Meeting", StartTime = new DateTime(2020, 1, 8, 11, 30, 0) , EndTime = new DateTime(2020, 1, 8, 12, 30, 0) },
        new AppointmentData { Id = 2, Subject = "Conference", StartTime = new DateTime(2020, 1, 10, 11, 30, 0) , EndTime = new DateTime(2020, 1, 10, 12, 30, 0) },
        new AppointmentData { Id = 3, Subject = "Seminar", StartTime = new DateTime(2020, 1, 6, 9, 30, 0) , EndTime = new DateTime(2020, 1, 6, 11, 0, 0),
        RecurrenceRule = "FREQ=DAILY;INTERVAL=1;COUNT=5" }
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
