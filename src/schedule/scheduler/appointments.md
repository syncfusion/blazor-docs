---
title: "Handling Appointments of Blazor Scheduler"
component: "Scheduler"
description: "This section explains about the types of Scheduler events, recurring events, customization options available in it, and also drag and resize options."
---

# Appointments

Appointments can be anything that are scheduled for a specific time period. It can be created on varied time range and each appointments are categorized based on this range. The Scheduler events can be categorized as,

* Normal events
* Spanned events
* All-day events
* Recurring events

## Normal events

Represents an appointment that is created for any specific time interval within a day.

### Creating a normal event

The following example depicts how to define a normal event on the Scheduler, with event data being loaded from simple list of array objects.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" Height="550px" SelectedDate="@(new DateTime(2020, 1, 31))">
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
</SfSchedule>

@code{
    List<AppointmentData> DataSource = new List<AppointmentData>
    {
        new AppointmentData { Id = 1, Subject = "Meeting", StartTime = new DateTime(2020, 1, 31, 9, 30, 0) , EndTime = new DateTime(2020, 1, 31, 11, 0, 0) }
    };
    public class AppointmentData
    {
        public int Id { get; set; }
        public string Subject { get; set; }
        public DateTime StartTime { get; set; }
        public DateTime EndTime { get; set; }
    }
}
```

## Spanned events

Represents an appointment that is created for more than 24 hours, and usually displayed on the all-day row. Also, represents another type of appointment that is created for more than one day but less than 24 hours, and usually displayed appropriately on both the days.

> For example, in week view if an appointment is created for two days say from November 25, 2020 – 11.00 PM to November 26, 2020 - 2.00 AM but less than 24 hours time interval, then the appointment split into two partitions and will be displayed on both the days.

## All-day events

Represents an appointment that is created for an entire day such as holiday events. It is usually displayed separately in an all-day row, a separate row for all-day appointments below the date header section. In Timeline views, the all-day appointments displays in the working space area, and no separate all-day row is present in that view.

> To change normal appointment into all-day event, set `IsAllDay` field to true.

### Hide all-day row events

You can make use of the CSS customization to prevent the display of all-day row appointments on the Scheduler UI.

```css
    .e-schedule .e-date-header-wrap .e-schedule-table thead {
        display: none;
    }
```

## Recurring events

Represents an appointment that is created for a certain time interval and occurring repeatedly on a daily, weekly, monthly or yearly basis at the same time interval based on the provided recurrence rule. Usually, the recurring events are indicated by a repeat marker added at the bottom-right position.

### Creating a recurring event

The following example depicts how to create a recurring event on Scheduler with the specific recurrence rule. In the following example, an event is made to repeat on daily mode and ends after 5 occurrences.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" Height="550px" SelectedDate="@(new DateTime(2020, 1, 9))">
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
</SfSchedule>

@code{
    List<AppointmentData> DataSource = new List<AppointmentData>
    {
        new AppointmentData { Id = 1, Subject = "Meeting", StartTime = new DateTime(2020, 1, 6, 9, 30, 0) , EndTime = new DateTime(2020, 1, 6, 11, 0, 0),
        RecurrenceRule = "FREQ=DAILY;INTERVAL=1;COUNT=5" }
    };
    public class AppointmentData
    {
        public int Id { get; set; }
        public string Subject { get; set; }
        public DateTime StartTime { get; set; }
        public DateTime EndTime { get; set; }
        public string RecurrenceRule { get; set; }
        public Nullable<int> RecurrenceID { get; set; }
        public string RecurrenceException { get; set; }
    }
}
```

### Adding exceptions

A few instance of the recurrence series can be excluded on specific dates, by adding those exceptional dates to the `RecurrenceException` field. These date values should be given in the ISO date time format with no hyphens(-) separating the date elements.

For example, 22nd February 2020 can be represented as 20200222. Also, the time part being represented in UTC format needs to add "Z" after the time portion with no space. "07:30:00 UTC" is therefore represented as "073000Z".

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" Height="550px" SelectedDate="@(new DateTime(2020, 1, 6))">
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
</SfSchedule>

@code{
    List<AppointmentData> DataSource = new List<AppointmentData>
    {
        new AppointmentData { Id = 1, Subject = "Meeting", StartTime = new DateTime(2020, 1, 6, 9, 30, 0) , EndTime = new DateTime(2020, 1, 6, 11, 0, 0),
        RecurrenceRule = "FREQ=DAILY;INTERVAL=1;COUNT=5", RecurrenceException = "20200107T043000Z,20200109T043000Z" }
    };
    public class AppointmentData
    {
        public int Id { get; set; }
        public string Subject { get; set; }
        public DateTime StartTime { get; set; }
        public DateTime EndTime { get; set; }
        public string RecurrenceRule { get; set; }
        public string RecurrenceException { get; set; }
        public Nullable<int> RecurrenceID { get; set; }
    }
}
```

### Editing an occurrence from a series

To dynamically edit a particular occurrence from an event series and display it on the initial load of Scheduler, the edited occurrence needs to be added as a new event to the dataSource collection, with an additional `RecurrenceID` field defined to it. The `RecurrenceID` field of edited occurrence usually maps the ID value of the parent event.

In this example, a recurring instance that displays on the date 30th Jan 2020 is edited with different timings. Therefore, this particular date is excluded from the parent recurring event that repeats from 28th January 2020 to 4th February 2020. This can be done by adding the `RecurrenceException` field with the excluded date value on the parent event. Also, the edited occurrence event which is created as a new event should carry the `RecurrenceID` field pointing to the parent event's `Id` value.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" Height="550px" SelectedDate="@(new DateTime(2020, 1, 31))">
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
</SfSchedule>

@code{
    List<AppointmentData> DataSource = new List<AppointmentData>
    {
        new AppointmentData { Id = 1, Subject = "Scrum Meeting", StartTime = new DateTime(2020, 1, 28, 9, 30, 0) , EndTime = new DateTime(2020, 1, 28, 11, 0, 0),
        RecurrenceRule = "FREQ=DAILY;INTERVAL=1;COUNT=5", RecurrenceException = "20200130T043000Z" },
        new AppointmentData { Id = 2, Subject = "Scrum Meeting Rescheduled", StartTime = new DateTime(2020, 1, 30, 10, 30, 0) , EndTime = new DateTime(2020, 1, 30, 12, 0, 0), RecurrenceID = 1 }
    };
    public class AppointmentData
    {
        public int Id { get; set; }
        public string Subject { get; set; }
        public DateTime StartTime { get; set; }
        public DateTime EndTime { get; set; }
        public string RecurrenceRule { get; set; }
        public string RecurrenceException { get; set; }
        public Nullable<int> RecurrenceID { get; set; }
    }
}
```

### Edit/Delete following recurrence events

The Scheduler allows the user to edit the following recurrence events by setting true value to `EditFollowingEvents` within the `ScheduleEventSettings` tag. Once we have edited/ deleted the recurrence events as following events, then the following recurrence events will be considered as separate series, the changes will not reflect to parent series. In the following code example, if we edit or delete any of the recurrence event with following events option, then the edit or delete action is applied to further recurrence events.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" Width="100%" Height="550px" SelectedDate="@(new DateTime(2020, 3, 10))">
    <ScheduleEventSettings DataSource="@DataSource" EditFollowingEvents="true"></ScheduleEventSettings>
</SfSchedule>

@code{
    List<AppointmentData> DataSource = new List<AppointmentData>
    {
        new AppointmentData { Id = 1, Subject = "Meeting", StartTime = new DateTime(2020, 3, 9, 9, 30, 0) , EndTime = new DateTime(2020, 3, 9, 11, 0, 0), RecurrenceRule = "FREQ=DAILY;INTERVAL=1;COUNT=5" }
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

The following image depicts the edited recurrence following events.

![Edit Following Events](images/edit-following-events.png)

### Recurrence options and rules

Events can be repeated on a daily, weekly, monthly or yearly basis based on the recurrence rule which accepts the string value. The following details should be assigned to the `RecurrenceRule` property to generate the recurring instances.

* Repeat type - daily/weekly/monthly/yearly.
* How many times it needs to be repeated?
* The interval duration.
* The time period to render the appointment, etc.

There are four repeat types available namely,

* **Daily** - Creates the recurring instances on daily basis.
* **Weekly** - Creates the recurring instances on weekly basis for the selected days.
* **Monthly** - Creates the recurring instances on monthly basis for the selected months and other provided recurrence criteria.
* **Yearly** - Creates the recurring instances on yearly basis.

### Recurrence properties

 The properties based on which the recurrence appointments are created with its respective time period are depicted in the following table. Also, the valid rule string can be referred from [`iCalendar`](https://tools.ietf.org/html/rfc5545#section-3.3.10) specifications.

 > Refer [`iCalendar`](https://tools.ietf.org/html/rfc5545#section-3.3.10) specifications for valid recurrence rule string.

| Property | Purpose | Example |
|-------|---------| --------- |
| FREQ | Maintains the repeat type (Daily, Weekly, Monthly, Yearly) value of the appointment. | FREQ=DAILY;INTERVAL=1|
| INTERVAL | Maintains the interval value of the appointments. When you create the daily appointment at an interval of 2, the appointments are rendered on the days Monday, Wednesday and Friday (Creates an appointment on all days by leaving the interval of one day gap). | FREQ=DAILY;INTERVAL=2|
| COUNT | It holds the appointment’s count value. When the COUNT value is 10, then 10 instances of appointments are created in the recurrence series. | FREQ=DAILY;INTERVAL=1;COUNT=10|
| UNTIL | This property holds the end date value (in ISO format) denoting when the recurrence actually ends. | FREQ=DAILY;INTERVAL=1;UNTIL=20200530T041343Z;|
| BYDAY | It holds the day value(s), representing on which the appointments actually renders. Create the weekly appointment, and select the day(s) from the day options (Monday/Tuesday/Wednesday/Thursday/Friday/Saturday/Sunday). When Monday is selected, the first two letters of the selected day "MO" is saved in the BYDAY property. When multiple days are selected, the values are separated by commas. | FREQ=WEEKLY;INTERVAL=1;BYDAY=MO,WE;COUNT=10|
| BYMONTHDAY | This property is used to store the date value of the Month, while creating the Month recurrence appointment. When you create a Monthly recurrence appointment for every 3rd day of the month, then BYMONTHDAY holds the value 3 and creates the appointment on 3rd day of every month. | FREQ=MONTHLY;BYMONTHDAY=3;INTERVAL=1;COUNT=10|
| BYMONTH | This property is used to store the index value of the selected Month while creating the yearly appointments. When you create the yearly appointment on June month, the index value of June month 6 will get stored in the BYMONTH field. The appointment is created on every 6th month of a year. | FREQ=YEARLY;BYMONTHDAY=16;BYMONTH=6;INTERVAL=1;COUNT=10|
| BYSETPOS | This property is used to store the index value of the week. When you create the monthly appointment in second week of a month, the index value of the second week (2) is stored in BYSETPOS. | FREQ=MONTHLY;BYDAY=MO;BYSETPOS=2;COUNT=10|

> The default recurrence related validation has been included for recurrence appointments similar to the one available in Outlook. The validation usually occurs during the recurrence appointment creation, editing, drag and drop or resizing of the recurrence appointments and also if any single occurrence changes.

### Daily Frequency

| Description | Example |
|-------------|---------|
| Daily recurring event that never ends | FREQ=DAILY; INTERVAL=1 |
| Daily recurring event that ends after 5 occurrences | FREQ=DAILY; INTERVAL=1; COUNT=5 |
| Daily recurring event that ends exactly on 12/12/2020 | FREQ=DAILY; INTERVAL=1; UNTIL=20201212T041343Z |
| Daily event that recurs on alternative days and repeats for 10 occurrences | FREQ=DAILY; INTERVAL=2; COUNT=10 |

### Weekly Frequency

| Description | Example |
|-------------|---------|
| Weekly recurring event that repeats on every Monday, Wednesday and Friday and never ends | FREQ=WEEKLY; INTERVAL=1; BYDAY=MO,WE,FR |
| Repeats every week Thursday and ends after 10 occurrences | FREQ=WEEKLY; INTERVAL=1; BYDAY=TH; COUNT=10 |
| Repeats every week Monday and ends on 12/12/2020 | FREQ=WEEKLY; INTERVAL=1; BYDAY=MO; UNTIL=20201212T041343Z |
| Repeats on Monday, Wednesday and Friday of alternative weeks and ends after 10 occurrences | FREQ=WEEKLY; INTERVAL=2; BYDAY=MO, WE, FR; COUNT=10 |

### Monthly Frequency

| Description | Example |
|-------------|---------|
| Monthly recurring event that repeats on every 15th day of a month and never ends | FREQ=MONTHLY; BYMONTHDAY=15; INTERVAL=1 |
| Monthly recurring event that repeats on every 16th day of a month and ends after 10 occurrences | FREQ=MONTHLY; BYMONTHDAY=16; INTERVAL=1; COUNT=10 |
| Repeats every 17th day of a month and ends on 12/12/2020 | FREQ=MONTHLY; BYMONTHDAY=17; INTERVAL=1; UNTIL=20201212T041343Z |
| Repeats every 2nd Friday of a month and never ends | FREQ=MONTHLY; BYDAY=FR; BYSETPOS=2; INTERVAL=1 |
| Repeats every 4th Wednesday of a month and ends after 10 occurrences | FREQ=MONTHLY; BYDAY=WE; BYSETPOS=4; INTERVAL=1; COUNT=10 |
| Repeats every 4th Friday of a month and ends on 12/12/2020 | FREQ=MONTHLY; BYDAY=FR; BYSETPOS=4; INTERVAL=1; UNTIL=20201212T041343Z; |

### Yearly Frequency

| Description | Example |
|-------------|---------|
| Yearly event that repeats on every 15th day of December month and never ends | FREQ=YEARLY; BYMONTHDAY=15; BYMONTH=12; INTERVAL=1 |
| Event that repeats on every 10th day of December month and ends after 10 occurrences | FREQ=YEARLY; BYMONTHDAY=10; BYMONTH=12; INTERVAL=1; COUNT=10 |
| Repeats on every 12th day of December month and ends on 12/12/2025 | FREQ=YEARLY; BYMONTHDAY=12; BYMONTH=12; INTERVAL=1; UNTIL=20251212T041343Z |
| Repeats on every 3rd Friday of December month and never ends | FREQ=YEARLY; BYDAY=FR; BYMONTH=12; BYSETPOS=3; INTERVAL=1 |
| Repeats on every 3rd Tuesday of December month and ends after 10 occurrences | FREQ=YEARLY; BYDAY=TU; BYMONTH=12; BYSETPOS=3; INTERVAL=1; COUNT=10 |
| Repeats on every 4th Wednesday of December month and ends on 12/12/2028 | FREQ=YEARLY; BYDAY=WE; BYMONTH=12; BYSETPOS=4; INTERVAL=1; UNTIL=20281212T041343Z |

### Recurrence Validation

The built-in validation support has been added by default for recurring appointments during its creation, edit, drag and drop or resize action. The following are the possible validation alerts that displays on Scheduler while creating or editing the recurring events.

| Validation messages | Description |
|-------|---------|
| The recurrence pattern is not valid. | This alert will raise, when the selected recurrence rule value is not a valid one. For example, when you try to select the end date value (using `Until` option) for a recurring event, which occurs before the start date, an alert will popup out saying that the chosen pattern is invalid. |
| The changes made to specific instances of this series will be cancelled and those events will match the series again. | This alert will raise, when you try to edit the whole series, whose occurrence might have been already edited. For example, If there are five occurrences and one of the occurrence is already edited. Now, when you try to edit the entire series, you will get this validation alert. |
| The duration of the event must be shorter than how frequently it occurs. Shorten the duration, or change the recurrence pattern in the recurrence event editor. | This validation will occur, if the event duration is longer than the selected frequency. For example, if you create a recurring appointment with two days duration in `Daily` frequency with no intervals set to it, you may get this alert. |
| Some months have fewer than the selected date. For these months, the occurrence will fall on the last date of the month. | When you try to create a recurring appointment on 31st of every month, where few months won’t have 31 days and in this scenario, you will get this alert. |
| Two occurrences of the same event cannot occur on the same day. | This validation will occur, when you try to edit or move any single occurrence to some other date, where another occurrence of the same event is already present. |

## Event fields

The Scheduler dataSource usually holds the event instances, where each of the instance includes a collection of appropriate [fields](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Schedule.FieldModel_properties.html). It is mandatory to map these fields with the equivalent fields of database, when remote data is bound to it. When the local JSON data is bound, then the field names defined within the instances needs to be mapped with the scheduler event fields correctly.

> To create an event on Scheduler, it is enough to define the `StartTime` and `EndTime` fields. In case, if remote data is bound to Scheduler, then `Id` field becomes mandatory to process the CRUD actions on appropriate events.

### Built-in fields

The built-in fields available on Scheduler event object are as follows.

| Field name | Description |
|-------|---------|
| Id | The `Id` field needs to be defined as mandatory, and usually assigns a unique ID value to each of the events.|
| Subject | The `Subject` field is optional, and usually assigns the summary text to each of the events.|
| StartTime | The `StartTime` field defines the start time of an event and it is mandatory to provide it for any of the valid event objects.|
| EndTime | The `EndTime` field defines the end time of an event and it is mandatory to provide the end time for any of the valid event objects.|
| StartTimezone | It maps the `StartTimezone` field from the dataSource and usually accepts the valid IANA timezone names. It is assumed that the value provided for this field is taken into consideration while processing the `StartTime` field. When this field is not mapped with any timezone names, then the events will be processed based on the timezone assigned to the Scheduler.|
| EndTimezone | It maps the `EndTimezone` field from the dataSource and usually accepts the valid IANA timezone names. It is assumed that the value provided for this field is taken into consideration while processing the `EndTime` field. When this field is not mapped with any timezone names, then the events will be processed based on the timezone assigned to the Scheduler.|
| Location | It maps the `Location` field from the dataSource and the location text value will be displayed over the events.|
| Description | It maps the `Description` field from the dataSource and denotes the event description which is optional.|
| IsAllDay | The `IsAllDay` field is mapped from the dataSource and is used to denote whether an event is created for an entire day or for specific time alone. Usually, an event with `IsAllDay` field set to true will be considered as an all-day event. |
| RecurrenceID | It maps the `RecurrenceID` field from dataSource and usually holds the ID value of the parent recurrence event. This field is applicable only for the edited occurrence events.|
| RecurrenceRule | It maps the `RecurrenceRule` field from dataSource and holds the recurrence rule value in a string format. Also, it uniquely identifies whether the event belongs to a recurring type or normal ones. |
| RecurrenceException | It maps the `RecurrenceException` field from dataSource and is used to hold the collection of exception dates, on which the recurring occurrences needs to be excluded. |
| IsReadonly | It maps the `IsReadonly` field from dataSource. It is mainly used to make specific appointments as readonly when set to `true`. |
| IsBlock | It maps the `IsBlock` field from dataSource. It is used to block the particular time ranges in the Scheduler and prevents the event creation on those time slots. |

### Binding different field names

When the fields of event instances has the default mapping name, it is not mandatory to map them manually. If a Scheduler's dataSource holds the events collection with different field names, then it is necessary to map them with its equivalent field name within the `EventSettings` property.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" Height="550px" SelectedDate="@(new DateTime(2020, 1, 10))">
    <ScheduleEventSettings DataSource="@DataSource">
        <ScheduleField Id="TravelId">
            <FieldSubject Name="TravelSummary"></FieldSubject>
            <FieldLocation Name="Source"></FieldLocation>
            <FieldDescription Name="Comments"></FieldDescription>
            <FieldIsAllDay Name="FullDay"></FieldIsAllDay>
            <FieldStartTime Name="DepartureTime"></FieldStartTime>
            <FieldEndTime Name="ArrivalTime"></FieldEndTime>
            <FieldStartTimezone Name="Origin"></FieldStartTimezone>
            <FieldEndTimezone Name="Destination"></FieldEndTimezone>
        </ScheduleField>
    </ScheduleEventSettings>
</SfSchedule>

@code{
    List<AppointmentData> DataSource = new List<AppointmentData>
    {
        new AppointmentData { TravelId = 1, TravelSummary = "Paris", DepartureTime = new DateTime(2020, 1, 10, 10, 0, 0) , ArrivalTime = new DateTime(2020, 1, 10, 12, 30, 0),
        Source = "London", Comments = "Summer vacation planned for outstation.", Origin= "Asia/Yekaterinburg", Destination= "Asia/Yekaterinburg" }
    };
    public class AppointmentData
    {
        public int TravelId { get; set; }
        public string TravelSummary { get; set; }
        public DateTime DepartureTime { get; set; }
        public DateTime ArrivalTime { get; set; }
        public bool FullDay { get; set; }
        public string Source { get; set; }
        public string Comments { get; set; }
        public string Origin { get; set; }
        public string Destination { get; set; }
    }
}
```

> The mapper field `Id` is of string type and has no additional validation options, whereas all other fields are of `Object` type and has additional options.

### Event field settings

Each field of the Scheduler events are provided with additional settings such as options to set default value, to map with appropriate data source fields, to validate every event fields and to provide label values for those fields in the event window.

| Options | Description |
| ------- | ----------- |
| Default | Accepts the default value to the applicable fields (Subject, Location and Description), when no values are provided to them from dataSource. |
| Name | Accepts the field name to be mapped from the dataSource fields. |
| Title | Accepts the label values to be displayed for the fields of event editor. |
| Validation | Defines the validation rules to be applied on the event fields within the event editor. |

In following example, the Subject field in event editor will display its appropriate label as **Summary**. When no subject value is provided while saving an event, then the appointment will be saved with the default subject value as **Add Summary**.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" Height="550px" SelectedDate="@(new DateTime(2020, 1, 31))">
    <ScheduleEventSettings DataSource="@DataSource">
        <ScheduleField Id="Id">
            <FieldSubject Name="Subject" Title="Summary" Default="Add Summary"></FieldSubject>
            <FieldLocation Name="Location"></FieldLocation>
            <FieldDescription Name="Description"></FieldDescription>
            <FieldStartTime Name="StartTime"></FieldStartTime>
            <FieldEndTime Name="EndTime"></FieldEndTime>
        </ScheduleField>
    </ScheduleEventSettings>
</SfSchedule>

@code{
    List<AppointmentData> DataSource = new List<AppointmentData>
    {
        new AppointmentData { Id = 1, Subject = "Meeting", StartTime = new DateTime(2020, 1, 31, 9, 30, 0) , EndTime = new DateTime(2020, 1, 31, 11, 0, 0) }
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

## Adding Custom fields

Apart from the default Scheduler fields, the user can include 'n' number of custom fields for appointments. The following code example shows how to include two custom fields namely **Status** and **Priority** within event collection. It is not necessary to bind the custom fields within the `EventSettings`. However, those additional fields can be accessed easily, for internal processing as well as from application end.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" Height="550px" SelectedDate="@(new DateTime(2020, 1, 31))">
    <ScheduleEventSettings DataSource="@DataSource">
    </ScheduleEventSettings>
</SfSchedule>

@code{
    List<AppointmentData> DataSource = new List<AppointmentData>
    {
        new AppointmentData { Id = 1, Subject = "Meeting", StartTime = new DateTime(2020, 1, 31, 9, 30, 0) , EndTime = new DateTime(2020, 1, 31, 11, 0, 0),
        Status = "Completed", Priority = "High"}
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
        public string Status { get; set; }
        public string Priority { get; set; }
    }
}
```

## Drag and drop appointments

Appointments can be rescheduled to any time by dragging and dropping them onto the desired location. To work with drag and drop functionality make sure that `AllowDragAndDrop` is set to **true** on Scheduler. In mobile mode, you can drag and drop the events by tap holding an event and dropping them on to the desired location.

> By default, drag and drop action is applicable on all Scheduler views, except Agenda and Month-Agenda view.

### Disable the drag action

By default, you can drag and drop the events within any of the applicable scheduler views, and to disable it, set **false** to the `AllowDragAndDrop` property.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" Height="550px" AllowDragAndDrop="false" SelectedDate="@(new DateTime(2020, 1, 31))">
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
</SfSchedule>

@code{
    List<AppointmentData> DataSource = new List<AppointmentData>
    {
        new AppointmentData{ Id = 1, Subject = "Meeting", StartTime = new DateTime(2020, 1, 31, 9, 30, 0) , EndTime = new DateTime(2020, 1, 31, 11, 0, 0)}
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

### Preventing drag and drop on specific targets

It is possible to prevent the drag action on particular target, by passing the target to be excluded in the `ExcludeSelectors` option within `OnDragStart` event. In this example, we have prevented the drag action on all-day row.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" Height="550px" SelectedDate="@(new DateTime(2020, 1, 31))">
    <ScheduleEvents TValue="AppointmentData" OnDragStart="OnAppointmentDrag"></ScheduleEvents>
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
</SfSchedule>

@code{
    public void OnAppointmentDrag(DragEventArgs<AppointmentData> args)
    {
        args.ExcludeSelectors = "e-header-cells,e-all-day-cells";
    }
    List<AppointmentData> DataSource = new List<AppointmentData>
    {
        new AppointmentData{ Id = 1, Subject = "Meeting", StartTime = new DateTime(2020, 1, 31, 9, 30, 0) , EndTime = new DateTime(2020, 1, 31, 11, 0, 0)}
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

### Disable scrolling on drag action

By default, while dragging an appointment to the edges, either top/bottom in the vertical Scheduler or left/right in the timeline Scheduler, scrolling action takes place automatically. To prevent this scrolling, set `false` to the `Scroll` value within the `OnDragStart` event arguments.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" Height="550px" SelectedDate="@(new DateTime(2020, 1, 31))">
    <ScheduleEvents TValue="AppointmentData" OnDragStart="OnAppointmentDrag"></ScheduleEvents>
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
</SfSchedule>

@code{
    public void OnAppointmentDrag(DragEventArgs<AppointmentData> args)
    {
        args.Scroll.Enable = false;
    }
    List<AppointmentData> DataSource = new List<AppointmentData>
    {
        new AppointmentData{ Id = 1, Subject = "Meeting", StartTime = new DateTime(2020, 1, 31, 9, 30, 0) , EndTime = new DateTime(2020, 1, 31, 11, 0, 0)}
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

### Controlling scroll speed while dragging an event

The speed of the scrolling action while dragging an appointment to the Scheduler edges, can be controlled within the `OnDragStart` event by setting the desired value to the `ScrollBy` and `TimeDelay` option whereas its default value is 30 minutes and 100ms.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" Height="550px" SelectedDate="@(new DateTime(2020, 1, 31))">
    <ScheduleEvents TValue="AppointmentData" OnDragStart="OnAppointmentDrag"></ScheduleEvents>
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
</SfSchedule>

@code{
    public void OnAppointmentDrag(DragEventArgs<AppointmentData> args)
    {
        args.Scroll.ScrollBy = 5;
        args.Scroll.TimeDelay = 200;
    }
    List<AppointmentData> DataSource = new List<AppointmentData>
    {
        new AppointmentData{ Id = 1, Subject = "Meeting", StartTime = new DateTime(2020, 1, 31, 9, 30, 0) , EndTime = new DateTime(2020, 1, 31, 11, 0, 0)}
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

### Auto navigation of date ranges on dragging an event

When an event is dragged either to the left or right extreme edges of the Scheduler and kept hold for few seconds without dropping, the auto navigation of date ranges will be enabled allowing the Scheduler to navigate from current date range to back and forth respectively. This action is set to `false` by default and to enable it, you need to set `Navigation` to true within the `OnDragStart` event.

By default, the navigation delay is set to 2000ms. The navigation delay decides how long the user needs to drag and hold the appointments at the extremities. You can also set your own delay value for letting the users to navigate based on it, using the `TimeDelay` within the `OnDragStart` event.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" Height="550px" SelectedDate="@(new DateTime(2020, 1, 31))">
    <ScheduleEvents TValue="AppointmentData" OnDragStart="OnAppointmentDrag"></ScheduleEvents>
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
</SfSchedule>

@code{
    public void OnAppointmentDrag(DragEventArgs<AppointmentData> args)
    {
        args.Navigation.Enable = true;
        args.Navigation.TimeDelay = 4000;
    }
    List<AppointmentData> DataSource = new List<AppointmentData>
    {
        new AppointmentData{ Id = 1, Subject = "Meeting", StartTime = new DateTime(2020, 1, 31, 9, 30, 0) , EndTime = new DateTime(2020, 1, 31, 11, 0, 0)}
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

### Setting drag time interval

By default, while dragging an appointment, it moves at an interval of 30 minutes. To change the dragging time interval, pass the appropriate values to the `Interval` option within the `OnDragStart` event.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" Height="550px" SelectedDate="@(new DateTime(2020, 1, 31))">
    <ScheduleEvents TValue="AppointmentData" OnDragStart="OnAppointmentDrag"></ScheduleEvents>
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
</SfSchedule>

@code{
    public void OnAppointmentDrag(DragEventArgs<AppointmentData> args)
    {
        args.Interval = 10;
    }
    List<AppointmentData> DataSource = new List<AppointmentData>
    {
        new AppointmentData{ Id = 1, Subject = "Meeting", StartTime = new DateTime(2020, 1, 31, 9, 30, 0) , EndTime = new DateTime(2020, 1, 31, 11, 0, 0)}
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

### Drag and drop items from external source

It is possible to drag and drop the unplanned items from any of the external source into the scheduler, by manually saving those dropped item as a new appointment data through `AddEvent` method of Scheduler.

In this example, we have used the tree view control as an external source and the child nodes from the tree view component are dragged and dropped onto the Scheduler. Therefore, it is necessary to make use of the `OnNodeDragged` event of the TreeView component, where we can form an event object and save it using the `AddEvent` method.

```csharp
@using Syncfusion.Blazor.Schedule
@using Syncfusion.Blazor.Navigations

<div class="row">
    <div class="col-lg-8 e-droppable">
        <SfSchedule @ref="ScheduleRef" TValue="AppointmentData" Height="650px" SelectedDate="@(new DateTime(2020, 1, 31))">
            <ScheduleGroup Resources="@GroupData"></ScheduleGroup>
            <ScheduleResources>
                <ScheduleResource TValue="ResourceData" DataSource="@Consultants" Field="ConsultantID" Title="Consultant" Name="Consultants" TextField="Text" IdField="Id" ColorField="Color"></ScheduleResource>
            </ScheduleResources>
            <ScheduleEventSettings DataSource="@DataSource">
            </ScheduleEventSettings>
        </SfSchedule>
    </div>
    <div class="col-lg-4">
        <h3>Waiting list</h3>
        <SfTreeView TValue="EmployeeData" AllowDragAndDrop="true">
            <TreeViewFieldsSettings DataSource="@WaitingListData" Text="Name"></TreeViewFieldsSettings>
            <TreeViewEvents TValue="EmployeeData" OnNodeDragged="DragStop"></TreeViewEvents>
        </SfTreeView>
    </div>
</div>

@code{
    // Reference for Schedule
    SfSchedule<AppointmentData> ScheduleRef;
    public string[] GroupData = new string[] { "Consultants" };
    public List<ResourceData> Consultants { get; set; } = new List<ResourceData> {
        new ResourceData { Text = "Margaret", Id = 1, Color = "#1aaa55" },
        new ResourceData { Text = "Robert", Id = 2, Color = "#357cd2" },
        new ResourceData { Text = "Laura", Id = 3, Color = "#7fa900" },
        new ResourceData { Text = "Robson", Id = 4, Color = "#9e5fff" },
        new ResourceData { Text = "Laura", Id = 5, Color = "#bbdc00" }
    };
    public List<EmployeeData> WaitingListData { get; set; } = new List<EmployeeData>() {
        new EmployeeData { Id = 1, Name = "Johnson" },
        new EmployeeData { Id = 2, Name = "Sourav" },
        new EmployeeData { Id = 3,  Name = "Sanjay" }
    };
    List<AppointmentData> DataSource = new List<AppointmentData>
    {
        new AppointmentData{ Id = 1, Subject = "General-Check up", StartTime = new DateTime(2020, 1, 31, 9, 30, 0) , EndTime = new DateTime(2020, 1, 31, 11, 0, 0), ConsultantID=1 }
    };

    // Triggers when node drop is happened successfully
    async void DragStop(DragAndDropEventArgs args)
    {
        args.Cancel = true;
        object isScheduleSlot = await args.Target.GetAttribute("role");
        if (isScheduleSlot != null && isScheduleSlot.ToString() == "gridcell")
        {
            CellClickEventArgs cellData = await ScheduleRef.GetCellDetails(args.Target);
            var resourceDetails = await ScheduleRef.GetResourcesByIndex(cellData.GroupIndex);
            Random rnd = new Random();
            int Id = rnd.Next(1000);
            AppointmentData eventData = new AppointmentData
            {
                Id = Id,
                Subject = args.DraggedNodeData.Text,
                StartTime = cellData.StartTime,
                EndTime = cellData.EndTime,
                IsAllDay = cellData.IsAllDay,
                ConsultantID = resourceDetails.ResourceData.Id
            };
            await ScheduleRef.OpenEditor(eventData, CurrentAction.Add, true);
        }
    }

    public class AppointmentData
    {
        public int Id { get; set; }
        public string Subject { get; set; }
        public DateTime StartTime { get; set; }
        public DateTime EndTime { get; set; }
        public string RecurrenceRule { get; set; }
        public Nullable<int> RecurrenceID { get; set; }
        public string RecurrenceException { get; set; }
        public bool? IsAllDay { get; set; }
        public Nullable<int> ConsultantID { get; set; }
    }
    public class EmployeeData
    {
        public int Id { get; set; }
        public string Name { get; set; }
    }
    public class ResourceData
    {
        public int Id { get; set; }
        public string Text { get; set; }
        public string Color { get; set; }
    }
}
```

### Drag and drop items to external source

You can drag and drop the events to external source by setting the target to the property `EventDragArea`. In the following code example, we have two Scheduler and events from the first scheduler can be dropped to second scheduler. In the `Dragged` event of the first scheduler, the dragged event has been deleted from the first scheduler and added to the second scheduler.

```csharp
@using Syncfusion.Blazor.Schedule

<div class="row">
    <div class="col-lg-6">
        <SfSchedule @ref="Schedule1Ref" Height="550px" TValue="AppointmentData" EventDragArea=".ScheduleClass" SelectedDate="@(new DateTime(2020, 1, 6))">
            <ScheduleEvents TValue="AppointmentData" Dragged="OnDragged"></ScheduleEvents>
            <ScheduleEventSettings DataSource="@ScheduleData"></ScheduleEventSettings>
        </SfSchedule>
    </div>
    <div class="col-lg-6">
        <SfSchedule @ref="Schedule2Ref" Height="550px" TValue="AppointmentData" CssClass="ScheduleClass" SelectedDate="@(new DateTime(2020, 1, 6))">
        </SfSchedule>
    </div>
</div>


@code {
    SfSchedule<AppointmentData> Schedule1Ref;
    SfSchedule<AppointmentData> Schedule2Ref;
    List<AppointmentData> ScheduleData = new List<AppointmentData>
    {
        new AppointmentData { Id = 1, Subject = "Meeting", StartTime = new DateTime(2020, 1, 6, 9, 30, 0) , EndTime = new DateTime(2020, 1, 6, 11, 0, 0)}
    };
    public async Task OnDragged(DragEventArgs<AppointmentData> args)
    {
        await Schedule1Ref.DeleteEvent(args.Data.Id);
        Random random = new Random();
        args.Data.Id = Convert.ToInt32(random.Next());
        await Schedule2Ref.AddEvent(args.Data);
    }
    public class AppointmentData
    {
        public int Id { get; set; }
        public string Subject { get; set; }
        public string Location { get; set; }
        public string Description { get; set; }
        public DateTime StartTime { get; set; }
        public DateTime EndTime { get; set; }
        public Nullable<bool> IsAllDay { get; set; }
        public bool IsReadonly { get; set; }
        public string RecurrenceRule { get; set; }
        public Nullable<int> RecurrenceID { get; set; }
        public string RecurrenceException { get; set; }
        public string StartTimezone { get; set; }
        public string EndTimezone { get; set; }
    }
}
```

### Opening the editor window on drag stop

There are scenarios where you want to open the editor filled with data on newly dropped location and may need to proceed to save it, only when `Save` button is clicked on the editor. On clicking the cancel button should revert these changes. This can be achieved using the `Dragged` event of Scheduler.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" @ref="ScheduleRef" Height="550px" SelectedDate="@(new DateTime(2020, 1, 31))">
    <ScheduleEvents TValue="AppointmentData" Dragged="OnAppointmentDragStop"></ScheduleEvents>
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
</SfSchedule>

@code{
    SfSchedule<AppointmentData> ScheduleRef;
    public void OnAppointmentDragStop(DragEventArgs<AppointmentData> args)
    {
        args.Cancel = true;
        this.ScheduleRef.OpenEditor(args.Data, CurrentAction.Save, true);
    }
    List<AppointmentData> DataSource = new List<AppointmentData>
    {
        new AppointmentData{ Id = 1, Subject = "Meeting", StartTime = new DateTime(2020, 1, 31, 9, 30, 0) , EndTime = new DateTime(2020, 1, 31, 11, 0, 0)}
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

## Appointment Resizing

Another way of rescheduling an appointment can be done by resizing it through either of its handlers. To work with resizing functionality make sure that `AllowResizing` property is set to **true**.

### Disable the resize action

By default, resizing of events is allowed on all Scheduler views except Agenda and Month-Agenda view. To disable this event resizing action, set false to the `AllowResizing` property.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" Height="550px" AllowResizing="false" SelectedDate="@(new DateTime(2020, 1, 31))">
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
</SfSchedule>

@code{
    List<AppointmentData> DataSource = new List<AppointmentData>
    {
        new AppointmentData { Id = 1, Subject = "Meeting", StartTime = new DateTime(2020, 1, 31, 9, 30, 0) , EndTime = new DateTime(2020, 1, 31, 11, 0, 0)}
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

### Disable scrolling on resize action

By default, while resizing an appointment, when its handler reaches the extreme edges of the Scheduler, scrolling action will takes place along with event resizing. To prevent this scrolling action, set false to `Scroll` value within the `OnResizeStart` event.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" Height="550px" SelectedDate="@(new DateTime(2020, 1, 31))">
    <ScheduleEvents TValue="AppointmentData" OnResizeStart="OnAppointmentResize"></ScheduleEvents>
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
</SfSchedule>

@code{
    public void OnAppointmentResize(ResizeEventArgs<AppointmentData> args)
    {
        args.Scroll.Enable = false;
    }
    List<AppointmentData> DataSource = new List<AppointmentData>
    {
        new AppointmentData { Id = 1, Subject = "Meeting", StartTime = new DateTime(2020, 1, 31, 9, 30, 0) , EndTime = new DateTime(2020, 1, 31, 11, 0, 0)}
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

### Controlling scroll speed while resizing an event

The speed of the scrolling action while resizing an appointment to the Scheduler edges, can be controlled within the `OnResizeStart` event by setting the desired value to the `ScrollBy` option.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" Height="550px" SelectedDate="@(new DateTime(2020, 1, 31))">
    <ScheduleEvents TValue="AppointmentData" OnResizeStart="OnAppointmentResize"></ScheduleEvents>
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
</SfSchedule>

@code{
    public void OnAppointmentResize(ResizeEventArgs<AppointmentData> args)
    {
        args.Scroll.ScrollBy = 15;
    }
    List<AppointmentData> DataSource = new List<AppointmentData>
    {
        new AppointmentData { Id = 1, Subject = "Meeting", StartTime = new DateTime(2020, 1, 31, 9, 30, 0) , EndTime = new DateTime(2020, 1, 31, 11, 0, 0)}
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

### Setting resize time interval

By default, while resizing an appointment, it extends or shrinks at an interval of 30 minutes. To change this default resize interval, set appropriate values to `interval` option within the `resizeStart` event.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" Height="550px" SelectedDate="@(new DateTime(2020, 1, 31))">
    <ScheduleEvents TValue="AppointmentData" OnResizeStart="OnAppointmentResize"></ScheduleEvents>
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
</SfSchedule>

@code{
    public void OnAppointmentResize(ResizeEventArgs<AppointmentData> args)
    {
        args.Interval = 10;
    }
    List<AppointmentData> DataSource = new List<AppointmentData>
    {
        new AppointmentData { Id = 1, Subject = "Meeting", StartTime = new DateTime(2020, 1, 31, 9, 30, 0) , EndTime = new DateTime(2020, 1, 31, 11, 0, 0)}
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

## Appointment customization

The look and feel of the Scheduler events can be customized using any one of the following ways.

* [Using event template](#using-template)
* [Using eventRendered event](#using-eventrendered-event)
* [Using custom CSS class](#using-cssclass)

### Using template

Any kind of text, images and links can be added to customize the look of the events. The user can format and change the default appearance of the events by making use of the `Template` option available within the `ScheduleEventsettings` tag helper. The following code example customizes the appointment.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" Height="650px" SelectedDate= "@(new DateTime(2020, 1, 31))">
    <ScheduleEventSettings DataSource="@DataSource">
        <Template>
            <div>Subject: @((context as AppointmentData).Subject)</div>
            <div>StartTime: @((context as AppointmentData).StartTime.ToUniversalTime())</div>
            <div>EndTime:  @((context as AppointmentData).EndTime.ToUniversalTime())</div>
        </Template>
    </ScheduleEventSettings>
</SfSchedule>
@code {
     List<AppointmentData> DataSource = new List<AppointmentData>
    {
        new AppointmentData { Id = 1, Subject = "Meeting", StartTime = new DateTime(2020, 1, 31, 9, 30, 0) , EndTime = new DateTime(2020, 1, 31, 11, 0, 0) }
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

> All the built-in fields that are mapped to the appropriate field properties within the `ScheduleEventsettings`, as well as custom mapped fields from the Scheduler dataSource can be accessed within the template code.

### Using eventRendered event

The `EventRendered` event triggers before the appointment renders on the Scheduler. Therefore, this client-side event can be utilized to customize the look of events based on any specific criteria, before rendering them on the scheduler. Also, you can customize the appointment color by adding `CategoryColor` field to the `AppointmentData` and assign the required color code to that filed. In the below example, the background of appointments has been changed by customizing the `style` attribute of the appointment data.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" Height="650px" SelectedDate="@(new DateTime(2020, 1, 9))">
    <ScheduleEvents TValue="AppointmentData" EventRendered="OnEventRendered"></ScheduleEvents>
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
</SfSchedule>

@code{
    public async Task OnEventRendered(EventRenderedArgs<AppointmentData> args)
    {
        string style = (await args.Element.GetAttribute("style")).ToString();  // Get style attribute of the element
        style += "background:" + args.Data.CategoryColor;               // concatenate the background color
        args.Element.SetAttribute("style", style);                      // Reset the values of style attribute
    }
    List<AppointmentData> DataSource = new List<AppointmentData>
    {
        new AppointmentData { Id = 1, Subject = "Explosion of Betelgeuse Star", StartTime = new DateTime(2020, 1, 5, 9, 30, 0) , EndTime = new DateTime(2020, 1, 5, 11, 0, 0), CategoryColor= "#df5286" },
        new AppointmentData { Id = 2, Subject = "Thule Air Crash Report", StartTime = new DateTime(2020, 1, 6, 12, 0, 0) , EndTime = new DateTime(2020, 1, 6, 14, 0, 0), CategoryColor= "#7fa900" },
        new AppointmentData { Id = 3, Subject = "Blue Moon Eclipse", StartTime = new DateTime(2020, 1, 7, 9, 30, 0) , EndTime = new DateTime(2020, 1, 7, 11, 0, 0), CategoryColor= "#1aaa55" },
        new AppointmentData { Id = 4, Subject = "Meteor Showers in 2018", StartTime = new DateTime(2020, 1, 8, 13, 0, 0) , EndTime = new DateTime(2020, 1, 8, 14, 30, 0), CategoryColor= "#ea7a57", RecurrenceRule = "FREQ=DAILY;INTERVAL=1;COUNT=5" }
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
        public string CategoryColor { get; set; }
    }
}
```

### Using cssClass

The customization of events can also be achieved using `CssClass` property of the Scheduler. In the following example, the background of appointments has been changed using the cssClass.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" Height="550px" CssClass="custom-class" SelectedDate="@(new DateTime(2020, 1, 31))">
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
</SfSchedule>

<style>
    .custom-class.e-schedule .e-vertical-view .e-all-day-appointment-wrapper .e-appointment,
    .custom-class.e-schedule .e-vertical-view .e-day-wrapper .e-appointment,
    .custom-class.e-schedule .e-month-view .e-appointment {
        background: green;
    }
</style>

@code{
    List<AppointmentData> DataSource = new List<AppointmentData>
    {
        new AppointmentData { Id = 1, Subject = "Meeting", StartTime = new DateTime(2020, 1, 31, 9, 30, 0) , EndTime = new DateTime(2020, 1, 31, 11, 0, 0) }
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

## Block Date and Time

It is possible to block a set of dates or a particular time ranges on the Scheduler. To do so, define an appointment object within `EventSettings` along with the required time range to block and set the `IsBlock` field to **true**. Usually, the event objects defined with `IsBlock` field set to true will block the entire time cells lying within the appropriate time ranges specified through `StartTime` and `EndTime` fields.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" Height="550px" SelectedDate="@(new DateTime(2020, 1, 31))">
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
</SfSchedule>

@code{
    List<AppointmentData> DataSource = new List<AppointmentData>
    {
        new AppointmentData { Id = 1, Subject = "Meeting", StartTime = new DateTime(2020, 1, 31, 9, 30, 0) , EndTime = new DateTime(2020, 1, 31, 11, 0, 0),
        IsBlock = true }
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
        public bool IsBlock { get; set; }
        public string RecurrenceRule { get; set; }
        public string RecurrenceException { get; set; }
        public Nullable<int> RecurrenceID { get; set; }
    }
}
```

Block events can also be defined to repeat on several days as shown in the following code example.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" Height="550px" SelectedDate="@(new DateTime(2020, 1, 31))">
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
</SfSchedule>

@code{
    List<AppointmentData> DataSource = new List<AppointmentData>
    {
        new AppointmentData { Id = 1, Subject = "Meeting", StartTime = new DateTime(2020, 1, 31, 9, 30, 0) , EndTime = new DateTime(2020, 1, 31, 11, 0, 0),
        IsBlock = true, RecurrenceRule = "FREQ=DAILY;INTERVAL=1;COUNT=5" }
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
        public bool IsBlock { get; set; }
        public string RecurrenceRule { get; set; }
        public string RecurrenceException { get; set; }
        public Nullable<int> RecurrenceID { get; set; }
    }
}
```

## Readonly

An interaction with the appointments of Scheduler can be enabled/disabled using the `Readonly` property. With this property enabled, you can simply navigate between the Scheduler dates, views and can be able to view the appointment details in the quick info window. Most importantly, the users are not allowed to perform any CRUD actions on Scheduler, when this property is set to true. By default, it is set as **false**.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" Height="550px" Readonly="true" SelectedDate="@(new DateTime(2020, 1, 31))">
    <ScheduleEventSettings DataSource="DataSource"></ScheduleEventSettings>
</SfSchedule>

@code{
    List<AppointmentData> DataSource = new List<AppointmentData>
    {
        new AppointmentData { Id = 1, Subject = "Meeting", StartTime = new DateTime(2020, 1, 31, 9, 30, 0) , EndTime = new DateTime(2020, 1, 31, 11, 0, 0) }
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

## Make specific events readonly

There are scenarios where you need to restrict the CRUD action on specific appointments alone based on certain conditions. In the following example, the events that has occurred on the past hours from the current date of the Scheduler are made as read-only and the CRUD actions has been prevented only on those appointments. This can be achieved by setting `IsReadonly` field of read-only events to `true`.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" Height="550px" SelectedDate="@(new DateTime(2020, 1, 31))">
    <ScheduleEventSettings DataSource="DataSource"></ScheduleEventSettings>
</SfSchedule>

@code{
    List<AppointmentData> DataSource = new List<AppointmentData>
    {
        new AppointmentData { Id = 1, Subject = "Paris", StartTime = new DateTime(2020, 1, 28, 10, 0, 0) , EndTime = new DateTime(2020, 1, 28, 12, 0, 0),
        IsReadonly = true },
        new AppointmentData { Id = 2, Subject = "Germany", StartTime = new DateTime(2020, 1, 31, 10, 0, 0) , EndTime = new DateTime(2020, 1, 31, 12, 0, 0) }
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
        public bool IsReadonly { get; set; }
        public string RecurrenceRule { get; set; }
        public string RecurrenceException { get; set; }
        public Nullable<int> RecurrenceID { get; set; }
    }
}
```

> By default, the event editor is prevented to open on the read-only events when `IsReadonly` field is set to **true**.

## Differentiate the past time events

To differentiate the appearance of the appointments based on specific criteria such as displaying the past hour appointments with different colors on Scheduler, `EventRendered` event can be used which triggers before the appointment renders on the Scheduler.

In the following code example, the appointments beyond current date of the scheduler were differentiated with chocolate brown color.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" Width="100%" Height="550px" @bind-SelectedDate="@SelectedDate">
    <ScheduleViews>
        <ScheduleView Option="View.Day"></ScheduleView>
        <ScheduleView Option="View.Week"></ScheduleView>
        <ScheduleView Option="View.WorkWeek"></ScheduleView>
        <ScheduleView Option="View.Month"></ScheduleView>
    </ScheduleViews>
    <ScheduleEvents TValue="AppointmentData" EventRendered="OnEventRendered"></ScheduleEvents>
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
</SfSchedule>
<style>
    .e-schedule .e-vertical-view .e-day-wrapper .e-appointment.e-past-app, .e-schedule .e-month-view .e-appointment.e-past-app{
        background-color:chocolate;
    }
</style>

@code{
    public DateTime SelectedDate = new DateTime(2020,1,10);
    public string[] CustomClass { get; set; } = { "e-past-app" };
    public void OnEventRendered(EventRenderedArgs<AppointmentData> args)
    {
        if(args.Data.StartTime < SelectedDate)
        {
            args.Element.AddClass(CustomClass);
        }
    }
    List<AppointmentData> DataSource = new List<AppointmentData>
    {
        new AppointmentData { Id = 1, Subject = "Meeting", StartTime = new DateTime(2020, 1, 10, 9, 30, 0) , EndTime = new DateTime(2020, 1, 10, 11, 0, 0) },
        new AppointmentData { Id = 1, Subject = "Conference", StartTime = new DateTime(2020, 1, 9, 11, 30, 0) , EndTime = new DateTime(2020, 1, 9, 13, 0, 0) }
    };
    public class AppointmentData
    {
        public int Id { get; set; }
        public string Subject { get; set; }
        public DateTime StartTime { get; set; }
        public DateTime EndTime { get; set; }
    }
}
```

## Appointments occupying entire cell

The Scheduler allows the event to occupies the full height of the cell without its header part by setting `true` for `EnableMaxHeight` Property.

We can show more indicator if more than one appointment is available in a same cell by setting `true` to `EnableIndicator` property whereas its default value is false.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" Width="100%" Height="550px" SelectedDate="@(new DateTime(2020, 3, 11))" CurrentView="View.Month">
    <ScheduleViews>
        <ScheduleView Option="View.Week"></ScheduleView>
        <ScheduleView Option="View.Month"></ScheduleView>
        <ScheduleView Option="View.TimelineWeek"></ScheduleView>
        <ScheduleView Option="View.TimelineMonth"></ScheduleView>
    </ScheduleViews>
    <ScheduleEventSettings DataSource="@DataSource" EnableMaxHeight="true" EnableIndicator="true"></ScheduleEventSettings>
</SfSchedule>

@code{
    List<AppointmentData> DataSource = new List<AppointmentData>
    {
        new AppointmentData { Id = 1, Subject = "Meeting", StartTime = new DateTime(2020, 3, 11, 9, 30, 0) , EndTime = new DateTime(2020, 3, 11, 11, 0, 0) },
        new AppointmentData { Id = 2, Subject = "Conference", StartTime = new DateTime(2020, 3, 11, 9, 30, 0) , EndTime = new DateTime(2020, 3, 11, 11, 0, 0) }
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

> The `EnableIndicator` property will work, Only when the `EnableMaxHeight` property value is set to true.

## Display tooltip for appointments

The tooltip shows the Scheduler appointment's information in a formatted style by making use of the tooltip related options.

### Show or hide built-in tooltip

The tooltip can be displayed for appointments by setting `true` to the `EnableTooltip` option within the `ScheduleEventSettings` tag helper.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" Height="550px" SelectedDate="@(new DateTime(2020, 1, 10))">
    <ScheduleEventSettings DataSource="@DataSource" EnableTooltip="true"></ScheduleEventSettings>
</SfSchedule>

@code{
    List<AppointmentData> DataSource = new List<AppointmentData>
    {
        new AppointmentData { Id = 1, Subject = "Paris", StartTime = new DateTime(2020, 1, 8, 10, 0, 0) , EndTime = new DateTime(2020, 1, 8, 12, 0, 0),
        IsReadonly = true },
        new AppointmentData { Id = 2, Subject = "Germany", StartTime = new DateTime(2020, 1, 10, 10, 0, 0) , EndTime = new DateTime(2020, 1, 10, 12, 0, 0) }
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
        public bool IsReadonly { get; set; }
        public string RecurrenceRule { get; set; }
        public string RecurrenceException { get; set; }
        public Nullable<int> RecurrenceID { get; set; }
    }
}
```

### Customizing event tooltip using template

After enabling the default tooltip, it is possible to customize the display of needed event information on tooltip by making use of the `TooltipTemplate` option within the `ScheduleEventSettings`.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" Height="550px" SelectedDate="@(new DateTime(2020, 1, 13))">
    <ScheduleEventSettings DataSource="@DataSource" EnableTooltip="true">
        <TooltipTemplate>
            <div class="tooltip-wrap">
                <div>@((context as AppointmentData).Subject)</div>
                <div>From&nbsp;:&nbsp;@((context as AppointmentData).StartTime.ToLocalTime())</div>
                <div>To&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;:&nbsp;@((context as AppointmentData).EndTime.ToLocalTime()) </div>
            </div>
        </TooltipTemplate>
    </ScheduleEventSettings>
</SfSchedule>

@code{
    List<AppointmentData> DataSource = new List<AppointmentData>
    {
        new AppointmentData { Id = 1, Subject = "Paris", StartTime = new DateTime(2020, 1, 14, 10, 0, 0) , EndTime = new DateTime(2020, 1, 14, 12, 0, 0) },
        new AppointmentData { Id = 2, Subject = "Germany", StartTime = new DateTime(2020, 1, 15, 10, 0, 0) , EndTime = new DateTime(2020, 1, 15, 12, 0, 0) }
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

> All the field names that are mapped from the Scheduler dataSource to the appropriate field properties such as subject, description, location, startTime and endTime within the `ScheduleEventSettings` can be accessed within the template.

## Appointment selection

Appointment selection can be done either through mouse or keyboard actions. The selected events in UI will have a box shadow effect around to differentiate it from other appointments.

| Action | Description |
|-------|---------|
| Mouse click or Single tap on appointments | Selects single appointment. |
| Ctrl + [Mouse click] or [Single tap] on appointments | Selects multiple appointments.|

## Deleting multiple appointments

With the options available to select multiple appointments, it is also possible to delete the multiple selected appointments simply by pressing the `delete` key. In case of deleting multiple selected occurrences of an event series, only those occurrences will be deleted and not the entire series.

## Retrieve event details from the UI of an event

It is possible to access the information about the event fields of an appointment element displayed on the Scheduler UI. This can be achieved by passing an appointment element as argument to the public method `GetEventDetails`.

In the following example, the subject of the appointment clicked has been stored in eventData variable.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" @ref="ScheduleRef" Width="100%" Height="550px" SelectedDate="@(new DateTime(2020,1,10))">
    <ScheduleEvents TValue="AppointmentData" OnEventClick="EventClick"></ScheduleEvents>
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
</SfSchedule>

@code{
    SfSchedule<AppointmentData> ScheduleRef;
    public async void EventClick(EventClickArgs<AppointmentData> args)
    {
        AppointmentData eventData = await ScheduleRef.GetEventDetails(args.Element);
        //In the eventData we can get the currently clicked Appointments
    }
    List<AppointmentData> DataSource = new List<AppointmentData>
    {
        new AppointmentData { Id = 1, Subject = "Meeting", StartTime = new DateTime(2020, 1, 10, 9, 30, 0) , EndTime = new DateTime(2020, 1, 10, 11, 30, 0) },
        new AppointmentData { Id = 1, Subject = "Conference", StartTime = new DateTime(2020, 1, 9, 11, 30, 0) , EndTime = new DateTime(2020, 1, 9, 13, 0, 0) }
    };
    public class AppointmentData
    {
        public int Id { get; set; }
        public string Subject { get; set; }
        public DateTime StartTime { get; set; }
        public DateTime EndTime { get; set; }
    }
}
```

**Output:**

![Event details](images/event-details.png)

## Get the current view appointments

To retrieve the appointments present in the current view of the Scheduler, you can make use of the `GetCurrentViewEvents` public method. In the following example, current view appointment collection rendered has been traced in `DataBound` event.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" @ref="ScheduleRef" Width="100%" Height="550px" SelectedDate="@(new DateTime(2020, 1, 10))">
    <ScheduleEvents TValue="AppointmentData" DataBound="OnDataBound"></ScheduleEvents>
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
</SfSchedule>

@code{
    SfSchedule<AppointmentData> ScheduleRef;
    public async void OnDataBound(DataBoundEventArgs<AppointmentData> args)
    {
        List<AppointmentData> EventCollection = await ScheduleRef.GetCurrentViewEvents();
        //You can get the current view appointment collections in the EventCollection variable
    }
    List<AppointmentData> DataSource = new List<AppointmentData>
    {
        new AppointmentData { Id = 1, Subject = "Meeting", StartTime = new DateTime(2020, 1, 10, 9, 30, 0) , EndTime = new DateTime(2020, 1, 10, 11, 30, 0) },
        new AppointmentData { Id = 1, Subject = "Conference", StartTime = new DateTime(2020, 1, 9, 11, 30, 0) , EndTime = new DateTime(2020, 1, 9, 13, 0, 0) }
    };
    public class AppointmentData
    {
        public int Id { get; set; }
        public string Subject { get; set; }
        public DateTime StartTime { get; set; }
        public DateTime EndTime { get; set; }
    }
}
```

## Get the entire appointment collections

The entire collection of appointments rendered on the Scheduler can be accessed using the `GetEvents` public method. In the following example, entire appointment collection rendered on the Scheduler has been traced in `DataBound` event.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" @ref="ScheduleRef" Width="100%" Height="550px" SelectedDate="@(new DateTime(2020,1,10))">
    <ScheduleEvents TValue="AppointmentData" DataBound="OnDataBound"></ScheduleEvents>
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
</SfSchedule>

@code{
    SfSchedule<AppointmentData> ScheduleRef;
    public async void OnDataBound(DataBoundEventArgs<AppointmentData> args)
    {
        List<AppointmentData> EventCollection = await ScheduleRef.GetEvents();
        //You can get the entire appointment collections in the EventCollection variable
    }
    List<AppointmentData> DataSource = new List<AppointmentData>
    {
        new AppointmentData { Id = 1, Subject = "Meeting", StartTime = new DateTime(2020, 1, 10, 9, 30, 0) , EndTime = new DateTime(2020, 1, 10, 11, 30, 0) },
        new AppointmentData { Id = 1, Subject = "Conference", StartTime = new DateTime(2020, 2, 9, 11, 30, 0) , EndTime = new DateTime(2020, 2, 9, 13, 0, 0) }
    };
    public class AppointmentData
    {
        public int Id { get; set; }
        public string Subject { get; set; }
        public DateTime StartTime { get; set; }
        public DateTime EndTime { get; set; }
    }
}
```

## Refresh appointments

If your requirement is to simply refresh the appointments instead of refreshing the entire Scheduler elements from your application end, make use of the `RefreshEvents` public method.

```csharp
ScheduleRef.RefreshEvents();
```