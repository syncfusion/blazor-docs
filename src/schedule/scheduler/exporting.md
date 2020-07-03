---
title: "Exporting and importing of events"
component: "Scheduler"
description: "Learn how to export Scheduler events to an excel/ICS file and import events from ICS."
---

# Exporting

The Scheduler supports exporting all its appointments both to an Excel or ICS extension file. It offers different methods to export its appointments in an Excel or ICal format file. Let's look onto the ways on how to implement the exporting functionality in Scheduler.

## Excel Exporting

The Scheduler allows you to export all its events into an Excel format file by setting `true` to `AllowExcelExport` property whereas its default value is false and use the `ExportToExcel` method. By default, it exports all the default fields of Scheduler mapped through `<ScheduleEventSettings>` property.

```csharp
@using Syncfusion.Blazor.Schedule
@using Syncfusion.Blazor.Buttons

<SfButton Content="Excel Export" OnClick="OnExportToExcel"></SfButton>
<SfSchedule @ref="ScheduleRef" TValue="AppointmentData" AllowExcelExport="true" Height="650px" SelectedDate="@(new DateTime(2020, 1, 10))">
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
    <ScheduleViews>
        <ScheduleView Option="View.Week"></ScheduleView>
    </ScheduleViews>
</SfSchedule>

@code{
    SfSchedule<AppointmentData> ScheduleRef;
    List<AppointmentData> DataSource = new List<AppointmentData>
    {
        new AppointmentData { Id = 1, Subject = "Explosion of Betelgeuse Star", Location = "Dallas",  StartTime = new DateTime(2020, 1, 8, 9, 30, 0), EndTime = new DateTime(2020, 1, 8, 11, 0, 0)  },
        new AppointmentData { Id = 2, Subject = "Thule Air Crash Report", Location = "Texas", StartTime = new DateTime(2020, 1, 9, 12, 0, 0), EndTime = new DateTime(2020, 1, 9, 14, 0, 0)  },
        new AppointmentData { Id = 3, Subject = "Blue Moon Eclipse", Location = "Australia", StartTime = new DateTime(2020, 1, 10, 10, 30, 0), EndTime = new DateTime(2020, 1, 10, 11, 0, 0)  },
        new AppointmentData { Id = 4, Subject = "Meteor Showers in 2020", Location = "Canada", StartTime = new DateTime(2020, 1, 11, 13, 0, 0), EndTime = new DateTime(2020, 1, 11, 14, 30, 0)  },
        new AppointmentData { Id = 5, Subject = "Milky Way as Melting pot", Location = "Mexico", StartTime = new DateTime(2020, 1, 12, 12, 0, 0), EndTime = new DateTime(2020, 1, 12, 14, 0, 0)  }
    };
    public class AppointmentData
    {
        public int Id { get; set; }
        public string Subject { get; set; }
        public string Location { get; set; }
        public DateTime StartTime { get; set; }
        public DateTime EndTime { get; set; }
    }
    public void OnExportToExcel()
    {
        ScheduleRef.ExportToExcel();
    }
}

```

Exported Excel file be like below

![Excel Exporting](images/excel-export.png)

### Exporting with custom fields

By default, Scheduler exports all the default event fields that are mapped to it through the `<ScheduleEventSettings>` property. To limit the number of fields on the exported excel file, it provides an option to export only the custom fields of the event data. To export such custom fields alone, define the required `Fields` and pass it as argument to the `ExportToExcel` method as shown in the following example. For example: `['Id', 'Subject', 'StartTime', 'EndTime', 'Location']`.

```csharp

@using Syncfusion.Blazor.Schedule
@using Syncfusion.Blazor.Buttons

<SfButton Content="Excel Export" OnClick="OnExportToExcel"></SfButton>
<SfSchedule @ref="ScheduleRef" TValue="AppointmentData" AllowExcelExport="true" Height="650px" SelectedDate="@(new DateTime(2020, 1, 10))">
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
    <ScheduleViews>
        <ScheduleView Option="View.Week"></ScheduleView>
    </ScheduleViews>
</SfSchedule>

@code{
    SfSchedule<AppointmentData> ScheduleRef;
    List<AppointmentData> DataSource = new List<AppointmentData>
    {
        new AppointmentData { Id = 1, Subject = "Explosion of Betelgeuse Star", Location = "Dallas",  StartTime = new DateTime(2020, 1, 8, 9, 30, 0), EndTime = new DateTime(2020, 1, 8, 11, 0, 0)  },
        new AppointmentData { Id = 2, Subject = "Thule Air Crash Report", Location = "Texas", StartTime = new DateTime(2020, 1, 9, 12, 0, 0), EndTime = new DateTime(2020, 1, 9, 14, 0, 0)  },
        new AppointmentData { Id = 3, Subject = "Blue Moon Eclipse", Location = "Australia", StartTime = new DateTime(2020, 1, 10, 10, 30, 0), EndTime = new DateTime(2020, 1, 10, 11, 0, 0)  },
        new AppointmentData { Id = 4, Subject = "Meteor Showers in 2020", Location = "Canada", StartTime = new DateTime(2020, 1, 11, 13, 0, 0), EndTime = new DateTime(2020, 1, 11, 14, 30, 0)  },
        new AppointmentData { Id = 5, Subject = "Milky Way as Melting pot", Location = "Mexico", StartTime = new DateTime(2020, 1, 12, 12, 0, 0), EndTime = new DateTime(2020, 1, 12, 14, 0, 0)  }
    };
    public class AppointmentData
    {
        public int Id { get; set; }
        public string Subject { get; set; }
        public string Location { get; set; }
        public DateTime StartTime { get; set; }
        public DateTime EndTime { get; set; }
    }
    public void OnExportToExcel()
    {
        ExportOptions Options = new ExportOptions() { ExportType = ExcelFormat.Xlsx, Fields = new string[] { "Id", "Subject", "StartTime", "EndTime", "Location" } };
        ScheduleRef.ExportToExcel(Options);
    }
}

```

Exported Excel file with custom fields be like below

![Excel Exporting with custom fields](images/excel-export-customfields.png)

### Exporting individual occurrences of a recurring series

By default, the Scheduler exports recurring events as a single data by exporting only its parent record into the excel file. If you want to export each individual occurrences of a recurring series appointment as separate records in an Excel file, define the `IncludeOccurrences` option as `true` and pass it as argument to the `ExportToExcel` method. By default, the `IncludeOccurrences` option is set to `false`.

```csharp

@using Syncfusion.Blazor.Schedule
@using Syncfusion.Blazor.Buttons

<SfButton Content="Excel Export" OnClick="OnExportToExcel"></SfButton>
<SfSchedule @ref="ScheduleRef" TValue="AppointmentData" AllowExcelExport="true" Height="650px" SelectedDate="@(new DateTime(2020, 1, 10))">
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
    <ScheduleViews>
        <ScheduleView Option="View.Week"></ScheduleView>
    </ScheduleViews>
</SfSchedule>

@code{
    SfSchedule<AppointmentData> ScheduleRef;
    List<AppointmentData> DataSource = new List<AppointmentData>
    {
        new AppointmentData { Id = 1, Subject = "Explosion of Betelgeuse Star", Location = "Dallas",  StartTime = new DateTime(2020, 1, 8, 9, 30, 0), EndTime = new DateTime(2020, 1, 8, 11, 0, 0)  },
        new AppointmentData { Id = 2, Subject = "Thule Air Crash Report", Location = "Texas", StartTime = new DateTime(2020, 1, 9, 12, 0, 0), EndTime = new DateTime(2020, 1, 9, 14, 0, 0)  },
        new AppointmentData { Id = 3, Subject = "Blue Moon Eclipse", Location = "Australia", StartTime = new DateTime(2020, 1, 10, 10, 30, 0), EndTime = new DateTime(2020, 1, 10, 11, 0, 0)  },
        new AppointmentData { Id = 4, Subject = "Meteor Showers in 2020", Location = "Canada", StartTime = new DateTime(2020, 1, 11, 13, 0, 0), EndTime = new DateTime(2020, 1, 11, 14, 30, 0)  },
        new AppointmentData { Id = 5, Subject = "Milky Way as Melting pot", Location = "Mexico", StartTime = new DateTime(2020, 1, 12, 12, 0, 0), EndTime = new DateTime(2020, 1, 12, 14, 0, 0)  }
    };
    public class AppointmentData
    {
        public int Id { get; set; }
        public string Subject { get; set; }
        public string Location { get; set; }
        public DateTime StartTime { get; set; }
        public DateTime EndTime { get; set; }
    }
    public ExportOptions ExportValues = new ExportOptions { IncludeOccurrences = true };
    public void OnExportToExcel()
    {
       ScheduleRef.ExportToExcel(ExportValues);
    }
}

```

### Exporting custom event data

By default, the whole event collection bound to the Scheduler gets exported as an excel file. To export only specific events of Scheduler or some custom event collection, you need to pass those custom data collection as a parameter to the `ExportToExcel` method as shown in this following example, through the `CustomData` option.

> By default, the event data are taken from Scheduler dataSource.

```csharp

@using Syncfusion.Blazor.Schedule
@using Syncfusion.Blazor.Buttons

<SfButton Content="Excel Export" OnClick="OnExportToExcel"></SfButton>
<SfSchedule @ref="ScheduleRef" TValue="AppointmentData" AllowExcelExport="true" Width="100%" Height="650px" SelectedDate="@(new DateTime(2020, 1, 10))">
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
    <ScheduleViews>
        <ScheduleView Option="View.Week"></ScheduleView>
    </ScheduleViews>
</SfSchedule>s

@code{
    SfSchedule<AppointmentData> ScheduleRef;
    List<AppointmentData> DataSource = new List<AppointmentData>
    {
        new AppointmentData { Id = 1, Subject = "Explosion of Betelgeuse Star", Location = "Dallas",  StartTime = new DateTime(2020, 1, 8, 9, 30, 0), EndTime = new DateTime(2020, 1, 8, 11, 0, 0)  },
        new AppointmentData { Id = 2, Subject = "Thule Air Crash Report", Location = "Texas", StartTime = new DateTime(2020, 1, 9, 12, 0, 0), EndTime = new DateTime(2020, 1, 9, 14, 0, 0)  },
        new AppointmentData { Id = 3, Subject = "Blue Moon Eclipse", Location = "Australia", StartTime = new DateTime(2020, 1, 10, 10, 30, 0), EndTime = new DateTime(2020, 1, 10, 11, 0, 0)  },
        new AppointmentData { Id = 4, Subject = "Meteor Showers in 2020", Location = "Canada", StartTime = new DateTime(2020, 1, 11, 13, 0, 0), EndTime = new DateTime(2020, 1, 11, 14, 30, 0)  },
        new AppointmentData { Id = 5, Subject = "Milky Way as Melting pot", Location = "Mexico", StartTime = new DateTime(2020, 1, 12, 12, 0, 0), EndTime = new DateTime(2020, 1, 12, 14, 0, 0)  }
    };
    public class AppointmentData
    {
        public int Id { get; set; }
        public string Subject { get; set; }
        public string Location { get; set; }
        public DateTime StartTime { get; set; }
        public DateTime EndTime { get; set; }
    }
    public ExportOptions ExportValues = new ExportOptions { CustomData = customData };
    static List<AppointmentData> customData = new List<AppointmentData>()
    {
        new AppointmentData
        {
            Id = 1,
            Subject = "Explosion of Betelgeuse Star",
            Location = "Space Centre USA",
            StartTime = new DateTime(2020, 1, 31, 9, 30, 0) ,
            EndTime = new DateTime(2020, 1, 31, 11, 0, 0)
        },
        new AppointmentData
        {
            Id = 2,
            Subject = "Thule Air Crash Report",
            Location = "Newyork City",
            StartTime = new DateTime(2020, 1, 31, 12, 0, 0) ,
            EndTime = new DateTime(2020, 1, 31, 11, 0, 0)
        }
    };
    public void OnExportToExcel()
    {
        ScheduleRef.ExportToExcel(ExportValues);
    }
}

```

### Export with custom file name

By default, the Scheduler allows you to download the exported Excel file with a name `Schedule.xlsx`. It also provides an option to export the excel file with a custom file name, define the desired `FileName` and passing it as an argument to the `ExportToExcel` method.

```csharp

@using Syncfusion.Blazor.Schedule
@using Syncfusion.Blazor.Buttons

<SfButton Content="Excel Export" OnClick="OnExportToExcel"></SfButton>
<SfSchedule @ref="ScheduleRef" TValue="AppointmentData" AllowExcelExport="true" Height="650px" SelectedDate="@(new DateTime(2020, 1, 10))">
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
    <ScheduleViews>
        <ScheduleView Option="View.Week"></ScheduleView>
    </ScheduleViews>
</SfSchedule>

@code{
    SfSchedule<AppointmentData> ScheduleRef;
    List<AppointmentData> DataSource = new List<AppointmentData>
    {
        new AppointmentData { Id = 1, Subject = "Explosion of Betelgeuse Star", Location = "Dallas",  StartTime = new DateTime(2020, 1, 8, 9, 30, 0), EndTime = new DateTime(2020, 1, 8, 11, 0, 0)  },
        new AppointmentData { Id = 2, Subject = "Thule Air Crash Report", Location = "Texas", StartTime = new DateTime(2020, 1, 9, 12, 0, 0), EndTime = new DateTime(2020, 1, 9, 14, 0, 0)  },
        new AppointmentData { Id = 3, Subject = "Blue Moon Eclipse", Location = "Australia", StartTime = new DateTime(2020, 1, 10, 10, 30, 0), EndTime = new DateTime(2020, 1, 10, 11, 0, 0)  },
        new AppointmentData { Id = 4, Subject = "Meteor Showers in 2020", Location = "Canada", StartTime = new DateTime(2020, 1, 11, 13, 0, 0), EndTime = new DateTime(2020, 1, 11, 14, 30, 0)  },
        new AppointmentData { Id = 5, Subject = "Milky Way as Melting pot", Location = "Mexico", StartTime = new DateTime(2020, 1, 12, 12, 0, 0), EndTime = new DateTime(2020, 1, 12, 14, 0, 0)  }
    };
    public class AppointmentData
    {
        public int Id { get; set; }
        public string Subject { get; set; }
        public string Location { get; set; }
        public DateTime StartTime { get; set; }
        public DateTime EndTime { get; set; }
    }
    public ExportOptions ExportValues = new ExportOptions { FileName = "SchedulerData" };
    public void OnExportToExcel()
    {
        ScheduleRef.ExportToExcel(ExportValues);
    }
}

```

### Excel file formats

By default, the Scheduler exports event data to an excel file in the `.xlsx` format. You can also export the Scheduler data in either of the file type such as `.xlsx` or `csv` formats, by defining the `ExportType` option as either `csv` or `xlsx`. By default, the `ExportType` is set to `xlsx`.

```csharp

@using Syncfusion.Blazor.Schedule
@using Syncfusion.Blazor.Buttons

<SfButton Content="Excel Export" OnClick="OnExportToExcel"></SfButton>
<SfSchedule @ref="ScheduleRef" TValue="AppointmentData" AllowExcelExport="true" Height="650px" SelectedDate="@(new DateTime(2020, 1, 10))">
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
    <ScheduleViews>
        <ScheduleView Option="View.Week"></ScheduleView>
    </ScheduleViews>
</SfSchedule>

@code{
    SfSchedule<AppointmentData> ScheduleRef;
    List<AppointmentData> DataSource = new List<AppointmentData>
    {
        new AppointmentData { Id = 1, Subject = "Explosion of Betelgeuse Star", Location = "Dallas",  StartTime = new DateTime(2020, 1, 8, 9, 30, 0), EndTime = new DateTime(2020, 1, 8, 11, 0, 0)  },
        new AppointmentData { Id = 2, Subject = "Thule Air Crash Report", Location = "Texas", StartTime = new DateTime(2020, 1, 9, 12, 0, 0), EndTime = new DateTime(2020, 1, 9, 14, 0, 0)  },
        new AppointmentData { Id = 3, Subject = "Blue Moon Eclipse", Location = "Australia", StartTime = new DateTime(2020, 1, 10, 10, 30, 0), EndTime = new DateTime(2020, 1, 10, 11, 0, 0)  },
        new AppointmentData { Id = 4, Subject = "Meteor Showers in 2020", Location = "Canada", StartTime = new DateTime(2020, 1, 11, 13, 0, 0), EndTime = new DateTime(2020, 1, 11, 14, 30, 0)  },
        new AppointmentData { Id = 5, Subject = "Milky Way as Melting pot", Location = "Mexico", StartTime = new DateTime(2020, 1, 12, 12, 0, 0), EndTime = new DateTime(2020, 1, 12, 14, 0, 0)  }
    };
    public class AppointmentData
    {
        public int Id { get; set; }
        public string Subject { get; set; }
        public string Location { get; set; }
        public DateTime StartTime { get; set; }
        public DateTime EndTime { get; set; }
    }
    public ExportOptions ExportValues = new ExportOptions { ExportType = ExcelFormat.Csv };
    public void OnExportToExcel()
    {
        ScheduleRef.ExportToExcel(ExportValues);
    }
}

```

## Exporting calendar events as ICS file

You can export the Scheduler events to a calendar (.ics) file format, and open it on any of the other default calendars such as Google or Outlook.

The following code example shows how the Scheduler events are exported to a calendar (.ics) file by making use of the `ExportToICalendars` public method.

```csharp

@using Syncfusion.Blazor.Schedule
@using Syncfusion.Blazor.Buttons

<SfButton Content="Excel Export" OnClick="OnExportToIcs"></SfButton>
<SfSchedule @ref="ScheduleRef" TValue="AppointmentData" Height="650px" SelectedDate="@(new DateTime(2020, 1, 10))">
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
    <ScheduleViews>
        <ScheduleView Option="View.Week"></ScheduleView>
    </ScheduleViews>
</SfSchedule>

@code{
    SfSchedule<AppointmentData> ScheduleRef;
    List<AppointmentData> DataSource = new List<AppointmentData>
    {
        new AppointmentData { Id = 1, Subject = "Explosion of Betelgeuse Star", Location = "Dallas",  StartTime = new DateTime(2020, 1, 8, 9, 30, 0), EndTime = new DateTime(2020, 1, 8, 11, 0, 0)  },
        new AppointmentData { Id = 2, Subject = "Thule Air Crash Report", Location = "Texas", StartTime = new DateTime(2020, 1, 9, 12, 0, 0), EndTime = new DateTime(2020, 1, 9, 14, 0, 0)  },
        new AppointmentData { Id = 3, Subject = "Blue Moon Eclipse", Location = "Australia", StartTime = new DateTime(2020, 1, 10, 10, 30, 0), EndTime = new DateTime(2020, 1, 10, 11, 0, 0)  },
        new AppointmentData { Id = 4, Subject = "Meteor Showers in 2020", Location = "Canada", StartTime = new DateTime(2020, 1, 11, 13, 0, 0), EndTime = new DateTime(2020, 1, 11, 14, 30, 0)  },
        new AppointmentData { Id = 5, Subject = "Milky Way as Melting pot", Location = "Mexico", StartTime = new DateTime(2020, 1, 12, 12, 0, 0), EndTime = new DateTime(2020, 1, 12, 14, 0, 0)  }
    };
    public class AppointmentData
    {
        public int Id { get; set; }
        public string Subject { get; set; }
        public string Location { get; set; }
        public DateTime StartTime { get; set; }
        public DateTime EndTime { get; set; }
    }
    public void OnExportToIcs()
    {
        ScheduleRef.ExportToICalendar();
    }
}

```

### Exporting calendar with custom file name

By default, the calendar is exported with a file name `Calendar.ics`. To change this file name on export, pass the custom string value as `FileName` to the method argument so as to get the file downloaded with this provided name.

The following example downloads the iCal file with a name `ScheduleEvents.ics`.

```csharp

@using Syncfusion.Blazor.Schedule
@using Syncfusion.Blazor.Buttons

<SfButton Content="Excel Export" OnClick="OnExportToIcs"></SfButton>
<SfSchedule @ref="ScheduleRef" TValue="AppointmentData" Height="650px" SelectedDate="@(new DateTime(2020, 1, 10))">
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
    <ScheduleViews>
        <ScheduleView Option="View.Week"></ScheduleView>
    </ScheduleViews>
</SfSchedule>

@code{
    SfSchedule<AppointmentData> ScheduleRef;
    List<AppointmentData> DataSource = new List<AppointmentData>
    {
        new AppointmentData { Id = 1, Subject = "Explosion of Betelgeuse Star", Location = "Dallas",  StartTime = new DateTime(2020, 1, 8, 9, 30, 0), EndTime = new DateTime(2020, 1, 8, 11, 0, 0)  },
        new AppointmentData { Id = 2, Subject = "Thule Air Crash Report", Location = "Texas", StartTime = new DateTime(2020, 1, 9, 12, 0, 0), EndTime = new DateTime(2020, 1, 9, 14, 0, 0)  },
        new AppointmentData { Id = 3, Subject = "Blue Moon Eclipse", Location = "Australia", StartTime = new DateTime(2020, 1, 10, 10, 30, 0), EndTime = new DateTime(2020, 1, 10, 11, 0, 0)  },
        new AppointmentData { Id = 4, Subject = "Meteor Showers in 2020", Location = "Canada", StartTime = new DateTime(2020, 1, 11, 13, 0, 0), EndTime = new DateTime(2020, 1, 11, 14, 30, 0)  },
        new AppointmentData { Id = 5, Subject = "Milky Way as Melting pot", Location = "Mexico", StartTime = new DateTime(2020, 1, 12, 12, 0, 0), EndTime = new DateTime(2020, 1, 12, 14, 0, 0)  }
    };
    public class AppointmentData
    {
        public int Id { get; set; }
        public string Subject { get; set; }
        public string Location { get; set; }
        public DateTime StartTime { get; set; }
        public DateTime EndTime { get; set; }
    }
    public void OnExportToIcs()
    {
        ScheduleRef.ExportToICalendar("ScheduleEvents");
    }
}

```

## Importing events from other calendars

The events from external calendars (ICS files) can be imported into Scheduler by using the `ImportICalendar` method. In the following code example events has been imported from an ICS file into Scheduler with the help of Uploader. In `ImportICalendar` public method, ics file is passed as string format.

```csharp
@using Syncfusion.Blazor.Schedule
@using Syncfusion.Blazor.Inputs
@using System.IO

<SfUploader AllowedExtensions=".ics" CssClass="calendar-import" Multiple="false" Buttons="@BrowseBtn">
    <UploaderEvents ValueChange="OnChange"></UploaderEvents>
</SfUploader>
<SfSchedule @ref="ScheduleRef" TValue="AppointmentData" Width="100%" Height="650px" SelectedDate="@(new DateTime(2020, 3, 10))">
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
</SfSchedule>
<style>
    .calendar-import.e-upload {
        border: 0;
    }
    .calendar-import.e-upload .e-file-select-wrap {
        padding: 0
    }
    .calendar-import.e-upload .e-file-select-wrap .e-file-drop, .calendar-import .e-upload-files {
        display: none;
    }
</style>
@code{
    SfSchedule<AppointmentData> ScheduleRef;
    private UploaderButtonsProps BrowseBtn { get; set; } = new UploaderButtonsProps()
    {
        Browse = "Choose File"
    };
    public async Task OnChange(UploadChangeEventArgs args)
    {
        foreach (var file in args.Files)
        {
            file.Stream.Position = 0;
            StreamReader reader = new StreamReader(file.Stream);
            await ScheduleRef.ImportICalendar(reader.ReadToEnd());
        }
    }
    List<AppointmentData> DataSource = new List<AppointmentData>
    {
        new AppointmentData { Id = 1, Subject = "Explosion of Betelgeuse Star", Location = "Dallas",  StartTime = new DateTime(2020, 3, 10, 9, 30, 0), EndTime = new DateTime(2020, 3, 10, 11, 0, 0)  },
        new AppointmentData { Id = 2, Subject = "Thule Air Crash Report", Location = "Texas", StartTime = new DateTime(2020, 3, 13, 12, 0, 0), EndTime = new DateTime(2020, 3, 13, 14, 0, 0)  },
        new AppointmentData { Id = 3, Subject = "Blue Moon Eclipse", Location = "Australia", StartTime = new DateTime(2020, 3, 11, 10, 30, 0), EndTime = new DateTime(2020, 3, 11, 13, 0, 0)  },
        new AppointmentData { Id = 4, Subject = "Meteor Showers in 2020", Location = "Canada", StartTime = new DateTime(2020, 3, 9, 13, 0, 0), EndTime = new DateTime(2020, 3, 9, 14, 30, 0)  },
        new AppointmentData { Id = 5, Subject = "Milky Way as Melting pot", Location = "Mexico", StartTime = new DateTime(2020, 3, 12, 9, 0, 0), EndTime = new DateTime(2020, 3, 12, 10, 30, 0)  }
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