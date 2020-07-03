---
title: "Events available in Blazor Scheduler"
component: "Scheduler"
description: "In this topic, the list of events and their usage with code example for Blazor Scheduler Component has been provided."
---

# Events

In this section, we have provided the list of events of the Scheduler component which will be
triggered for appropriate Scheduler actions.

The events should be provided to the Scheduler using **ScheduleEvents** tag. When using events of Scheduler, **TValue** must be provided in the **ScheduleEvents** tag.

## ActionCompleted

`ActionCompleted` event triggers on successful completion of the Scheduler actions.

The request type that can be checked within the `ActionCompleted` event are as follows.

| RequestType | Description |
|------|-------------|
| `eventCreate` | Triggers on creating new event.|
| `eventChange` | Triggers on updating an event.|
| `eventRemove` | Triggers on deleting an event.|
| `dateNavigate` | Triggers while performing date navigations.|
| `viewNavigate` | Triggers while performing view navigations.|

```csharp
@using Syncfusion.Blazor.Schedule

<p style="color:green; font-size:20px">@ActionCompleted</p>
<SfSchedule TValue="AppointmentData" Width="100%" Height="550px" SelectedDate="@(new DateTime(2020, 3, 10))">
    <ScheduleEvents TValue="AppointmentData" ActionCompleted="OnActionCompleted"></ScheduleEvents>
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
</SfSchedule>

@code{
    string ActionCompleted = "";
    public void OnActionCompleted(ActionEventArgs<AppointmentData> args)
    {
        if (args.RequestType == "eventCreated" || args.RequestType == "eventChanged")   //To check for request type is add event or edit event
        {
            ActionCompleted = "Success";   //ActionCompleted become success while on create and update an event
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

## Created

`Created` event triggers after the Scheduler component is created.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" Width="100%" Height="550px" SelectedDate="@(new DateTime(2020, 3, 10))">
    <ScheduleEvents TValue="AppointmentData" Created="OnCreated"></ScheduleEvents>
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
</SfSchedule>

@code{
    public void OnCreated(object args)
    {
        //Here you can customize your code
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

## DataBinding

`DataBinding` event triggers before the data binds to the Scheduler.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" Width="100%" Height="550px" SelectedDate="@(new DateTime(2020, 3, 10))">
    <ScheduleEvents TValue="AppointmentData" DataBinding="DataBindHandler"></ScheduleEvents>
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
</SfSchedule>

@code{
    public void DataBindHandler(DataBindingEventArgs<AppointmentData> args)
    {
        //Here you can customize your code
        //Triggers before the data binds to the Scheduler, while performing CRUD actions, View and Date navigations
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

## DataBound

`DataBound` event triggers once the event data is bound to the Scheduler.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" @ref="@ScheduleRef" Width="100%" Height="550px" SelectedDate="@(new DateTime(2020, 3, 10))">
    <ScheduleEvents TValue="AppointmentData" DataBound="OnDataBound"></ScheduleEvents>
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
</SfSchedule>

@code{
    SfSchedule<AppointmentData> ScheduleRef;
    public async void OnDataBound(DataBoundEventArgs<AppointmentData> args)
    {
        List<AppointmentData> EventCollection = await ScheduleRef.GetEvents();   //You can get the entire appointment collections in the EventCollection variable
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

## Destroyed

`Destroyed` event triggers when the Scheduler component is destroyed.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" Width="100%" Height="550px" SelectedDate="@(new DateTime(2020, 3, 10))">
    <ScheduleEvents TValue="AppointmentData" Destroyed="OnDestroyed"></ScheduleEvents>
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
</SfSchedule>

@code{
    public void OnDestroyed(object args)
    {
        //Here you can customize your code
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

## Dragged

`Dragged` event triggers when the dragging of appointment is stopped.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" @ref="@ScheduleRef" Width="100%" Height="550px" SelectedDate="@(new DateTime(2020, 3, 10))">
    <ScheduleEvents TValue="AppointmentData" Dragged="OnDragged"></ScheduleEvents>
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
</SfSchedule>

@code{
    SfSchedule<AppointmentData> ScheduleRef;
    public void OnDragged(DragEventArgs<AppointmentData> args)
    {
        ScheduleRef.OpenEditor(args.Data, CurrentAction.Save, true);   //To open the editor window at drag stop
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

## EventRendered

`EventRendered` event triggers before each of the event getting rendered on the Scheduler user interface.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" Width="100%" Height="550px" SelectedDate="@(new DateTime(2020, 3, 10))">
    <ScheduleEvents TValue="AppointmentData" EventRendered="OnEventRendered"></ScheduleEvents>
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
</SfSchedule>
<style>
    .e-schedule .e-vertical-view .e-all-day-appointment-wrapper .e-appointment.custom-class,
    .e-schedule .e-vertical-view .e-day-wrapper .e-appointment.custom-class,
    .e-schedule .e-month-view .e-appointment.custom-class {
        background: yellow;
        color: red;
    }
</style>

@code{
    public string[] CustomClass = { "custom-class" };
    public void OnEventRendered(EventRenderedArgs<AppointmentData> args)
    {
        args.Element.AddClass(CustomClass);   //The custom-class will change the default color of appointment to green color while on event rendered
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

## MoreEventsClicked

`MoreEventsClicked` event triggers when the more events indicator are clicked.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" Width="100%" Height="550px" SelectedDate="@(new DateTime(2020, 3, 10))" CurrentView="View.Month">
    <ScheduleEvents TValue="AppointmentData" MoreEventsClicked="OnMoreEventsClick"></ScheduleEvents>
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
</SfSchedule>

@code{
    public void OnMoreEventsClick(MoreEventsClickArgs args)
    {
        args.Cancel = true;   //To prevent showing the appointments in more indiactor
    }
    List<AppointmentData> DataSource = new List<AppointmentData>
    {
        new AppointmentData { Id = 1, Subject = "Meeting In", StartTime = new DateTime(2020, 3, 10, 9, 30, 0) , EndTime = new DateTime(2020, 3, 10, 12, 0, 0) },
        new AppointmentData { Id = 2, Subject = "Conference", StartTime = new DateTime(2020, 3, 11, 9, 30, 0) , EndTime = new DateTime(2020, 3, 11, 12, 0, 0) },
        new AppointmentData { Id = 3, Subject = "Meeting Out", StartTime = new DateTime(2020, 3, 11, 9, 30, 0) , EndTime = new DateTime(2020, 3, 11, 12, 0, 0) }
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

## Navigating

`Navigating` event triggers before the date or view navigation takes place on Scheduler.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" Width="100%" Height="550px" SelectedDate="@(new DateTime(2020, 3, 10))">
    <ScheduleEvents TValue="AppointmentData" Navigating="OnNavigating"></ScheduleEvents>
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
</SfSchedule>

@code{
    public void OnNavigating(NavigatingEventArgs args)
    {
        args.Cancel = true;   //To prevent date and view navigations
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

## OnActionBegin

`OnActionBegin` event triggers on beginning of every Scheduler action.

The request type that can be checked within the `OnActionBegin` event are as follows.

| RequestType | Description |
|------|-------------|
| `eventCreate` | Triggers on Creating new event.|
| `eventChange` | Triggers on updating an event.|
| `eventRemove` | Triggers on Deleting an event.|
| `dateNavigate` | Triggers while performing date navigations.|
| `viewNavigate` | Triggers while performing view navigations.|

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" Width="100%" Height="550px" SelectedDate="@(new DateTime(2020, 3, 10))">
    <ScheduleEvents TValue="AppointmentData" OnActionBegin="OnActionBegin"></ScheduleEvents>
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
</SfSchedule>

@code{
    public void OnActionBegin(ActionEventArgs<AppointmentData> args)
    {
        if (args.RequestType == "eventRemove")   //To check for request type is event delete
        {
            args.Cancel = true;   //To prevent the appointment deletion
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

## OnActionFailure

`OnActionFailure` event triggers when a Scheduler action gets failed or interrupted.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" Width="100%" Height="550px" SelectedDate="@(new DateTime(2020, 3, 10))">
    <ScheduleEvents TValue="AppointmentData" OnActionFailure="OnActionFailure"></ScheduleEvents>
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
</SfSchedule>

@code{
    public void OnActionFailure(ActionEventArgs<AppointmentData> args)
    {
        //Here you can customize your code
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

## OnCellClick

`OnCellClick` event triggers when the Scheduler cells are single clicked or on single tap on the same cells in mobile devices.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" @ref="@ScheduleRef" Width="100%" Height="550px" SelectedDate="@(new DateTime(2020, 3, 10))">
    <ScheduleEvents TValue="AppointmentData" OnCellClick="OnCellClick"></ScheduleEvents>
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
</SfSchedule>

@code{
    SfSchedule<AppointmentData> ScheduleRef;
    public async void OnCellClick(CellClickEventArgs args)
    {
        var CellData = await ScheduleRef.GetCellDetails(args.Element);   //To get the current cell details
        await ScheduleRef.OpenEditor(CellData, CurrentAction.Add);   //To open editor window on cell click
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

## OnCellDoubleClick

`OnCellDoubleClick` event triggers when the Scheduler cells are double clicked.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" Width="100%" Height="550px" SelectedDate="@(new DateTime(2020, 3, 10))">
    <ScheduleEvents TValue="AppointmentData" OnCellDoubleClick="OnCellDoubleClick"></ScheduleEvents>
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
</SfSchedule>

@code{
    public void OnCellDoubleClick(CellClickEventArgs args)
    {
        args.Cancel = true;   //To prevent the opening of editor window
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

## OnDragStart

`OnDragStart` event triggers when an appointment is started to drag.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" Width="100%" Height="550px" SelectedDate="@(new DateTime(2020, 3, 10))">
    <ScheduleEvents TValue="AppointmentData" OnDragStart="OnDragStart"></ScheduleEvents>
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
</SfSchedule>

@code{
    public void OnDragStart(DragEventArgs<AppointmentData> args)
    {
        args.Scroll.Enable = false;   //To prevent scroll action on dragging
        args.Navigation.Enable = true;   //To allow events to navigate between dates while on dragging
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

## OnEventClick

`OnEventClick` event triggers when the events are single clicked or on single tapping the events on the mobile devices.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" @ref="@ScheduleRef" Width="100%" Height="550px" SelectedDate="@(new DateTime(2020, 3, 10))">
    <ScheduleEvents TValue="AppointmentData" OnEventClick="OnEventClick"></ScheduleEvents>
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
</SfSchedule>

@code{
    SfSchedule<AppointmentData> ScheduleRef;
    public async void OnEventClick(EventClickArgs<AppointmentData> args)
    {
        AppointmentData EventData = await ScheduleRef.GetEventDetails(args.Element);   //In EventData we can get the details of currently clicked Appointments
        await ScheduleRef.OpenEditor(EventData, CurrentAction.Save);   //To open the editor on event click
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

## OnPopupClose

`OnPopupClose` event triggers before any of the Scheduler popups close on the page.

In case, if you need to prevent only specific popups on Scheduler, then you can check the condition based on the popup type. The types of the popup that can be checked within the `OnPopupClose` event are as follows.

| PopupType | Description |
|------|-------------|
| `Editor` | For Detailed editor window.|
| `QuickInfo` | For Quick popup which opens on cell click.|
| `EditEventInfo` |For  Quick popup which opens on event click.|
| `ViewEventInfo` | For Quick popup which opens on responsive mode.|
| `EventContainer` | For more event indicator popup.|
| `RecurrenceAlert` | For edit recurrence event alert popup.|
| `DeleteAlert` | For delete confirmation popup.|
| `ValidationAlert` | For validation alert popup.|
| `RecurrenceValidationAlert` | For recurrence validation alert popup.|

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" Width="100%" Height="550px" SelectedDate="@(new DateTime(2020, 3, 10))">
    <ScheduleEvents TValue="AppointmentData" OnPopupClose="OnPopupClose"></ScheduleEvents>
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
</SfSchedule>

@code{
    public void OnPopupClose(PopupCloseEventArgs<AppointmentData> args)
    {
        if (args.Type == PopupType.Editor || args.Type == PopupType.QuickInfo)
        {
            args.Data.Subject = (args.Data.Subject == "Add title") ? "New event" : args.Data.Subject;   //The default subject is changed from Add Title to New event
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

## OnPopupOpen

`OnPopupOpen` event triggers before any of the Scheduler popups opens on the page.

In case, if you need to prevent only specific popups on Scheduler, then you can check the condition based on the popup type. The types of the popup that can be checked within the `OnPopupOpen` event are as follows.

| PopupType | Description |
|------|-------------|
| `Editor` | For Detailed editor window.|
| `QuickInfo` | For Quick popup which opens on cell click.|
| `EditEventInfo` |For  Quick popup which opens on event click.|
| `ViewEventInfo` | For Quick popup which opens on responsive mode.|
| `EventContainer` | For more event indicator popup.|
| `RecurrenceAlert` | For edit recurrence event alert popup.|
| `DeleteAlert` | For delete confirmation popup.|
| `ValidationAlert` | For validation alert popup.|
| `RecurrenceValidationAlert` | For recurrence validation alert popup.|

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" Width="100%" Height="550px" SelectedDate="@(new DateTime(2020, 3, 10))">
    <ScheduleEvents TValue="AppointmentData" OnPopupOpen="OnPopupOpen"></ScheduleEvents>
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
</SfSchedule>

@code{
    public void OnPopupOpen(PopupOpenEventArgs<AppointmentData> args)
    {
        //In case end time is lesser than the start time popup will be opened for validation alert
        if (args.Type == PopupType.ValidationAlert)   //To check for PopupType is ValidationAlert  
        {
            args.Cancel = true;   //To prevent start and end time validation alert
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

## OnRenderCell

`OnRenderCell` event triggers before each element of the Schedule rendering on the page.

The ElementType that can be checked within the `OnRenderCell` event are as follows.

| ElementType | Description |
|------|-------------|
| `AllDayCells` | Triggers on all day cell rendering.|
| `DateHeader` | Triggers on header cell rendering.|
| `EmptyCells` | Triggers on empty cell rendering on header bar.|
| `MajorSlot` | Triggers on major time slot cell rendering.|
| `MinorSlot` | Triggers on minor time slot cell rendering.|
| `MonthCells` | Triggers on month cell rendering.|
| `MonthDay` | Triggers on header cell in month view rendering.|
| `ResourceGroupCells` | Triggers on rendering of work cells for parent resource.|
| `ResourceHeader` | Triggers on resource header cell rendering.|
| `WorkCells` | Triggers on work cell rendering.|

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" Width="100%" Height="550px" SelectedDate="@(new DateTime(2020, 3, 10))">
    <ScheduleEvents TValue="AppointmentData" OnRenderCell="OnRenderCell"></ScheduleEvents>
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
</SfSchedule>
<style>
    .e-schedule .e-vertical-view .e-work-hours.custom-class {
        background-color: ivory;
    }
</style>

@code{
    public string[] CustomClass = { "custom-class" };
    public void OnRenderCell(RenderCellEventArgs args)
    {
        //workhours is highlighted with ivory color
        if (args.ElementType == ElementType.WorkCells)   //To check for ElementType is WorkCells
        {
            args.Element.AddClass(CustomClass);   //The default work hours color is changed to ivory color
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

## OnResizeStart

`OnResizeStart` event triggers when an appointment is started to resize.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" Width="100%" Height="550px" SelectedDate="@(new DateTime(2020, 3, 10))">
    <ScheduleEvents TValue="AppointmentData" OnResizeStart="OnResizeStart"></ScheduleEvents>
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
</SfSchedule>

@code{
    public void OnResizeStart(ResizeEventArgs<AppointmentData> args)
    {
        args.Scroll.Enable = false;   //To prevent scrolling when resize the event
        args.Interval = 10;   //To change the resizing time imterval from 30 minutes(default) to 10 minutes
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

## Resized

`Resized` event triggers when the resizing of appointment is stopped.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" Width="100%" Height="550px" SelectedDate="@(new DateTime(2020, 3, 10))">
    <ScheduleEvents TValue="AppointmentData" Resized="OnResized"></ScheduleEvents>
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
</SfSchedule>

@code{
    public void OnResized(ResizeEventArgs<AppointmentData> args)
    {
        args.Cancel = true;   //To prevent resize action
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