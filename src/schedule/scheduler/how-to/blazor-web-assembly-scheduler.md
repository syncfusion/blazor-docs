# Getting Started with Blazor WebAssembly Scheduler Using Visual Studio

This article provides a step-by-step instructions to configure Syncfusion Blazor Scheduler in a simple Blazor WebAssembly application using [Visual Studio 2019](https://visualstudio.microsoft.com/vs/).

**Note**: Starting with version 17.4.0.39 (2019 Volume 4), you need to include a valid license key (either paid or trial key) within your applications. Please refer to this help topic for more information.

## Prerequisites

* [Visual Studio 2019](https://visualstudio.microsoft.com/vs/)
* [.NET Core SDK 3.1.3](https://dotnet.microsoft.com/download/dotnet-core/3.1)

**Note**: .NET Core SDK 3.1.3 requires Visual Studio 2019 16.6 or later.

Syncfusion Blazor components are compatible with .NET Core 5.0 Preview 6 and it requires Visual Studio 16.7 Preview 1 or later.

## Create a Blazor WebAssembly project in Visual Studio 2019

1. Install the essential project templates in the Visual Studio 2019 by running the below command line in the command prompt.

    ```bash
      dotnet new -i Microsoft.AspNetCore.Components.WebAssembly.Templates::3.2.0-rc1.20223.4
    ```

2. Choose **Create a new project** from the Visual Studio dashboard.

   ![new project in aspnetcore blazor](../images/new-project.png)

3. Select **Blazor App** from the template and click **Next** button.

   ![blazor template](../images/blazor-template.png)

4. Now, the project configuration window will popup. Click Create button to create a new project with the default project configuration.

   ![asp.net core project configuration](../images/project-configuration.png)

5. Choose **Blazor WebAssembly App** from the dashboard and click **Create** button to create a new Blazor WebAssembly application. Make sure **.NET Core** and **ASP.NET Core 3.1** is selected at the top.

   ![wasm template](../images/blazor-client-template.png)

**Note**: ASP.NET Core 3.1 available in Visual Studio 2019 version.

## Importing Syncfusion Blazor component in the application

1. Now, install **Syncfusion.Blazor** NuGet package to the newly created application by using the `NuGet Package Manager`. Right-click the project and select Manage NuGet Packages.

   ![nuget explorer](../images/nuget-explorer.png)

2. Search **Syncfusion.Blazor** keyword in the Browser tab and install **Syncfusion.Blazor** NuGet package in the application.

   ![select nuget](../images/select-nuget-schedule-package.png)

3. Install **Syncfusion.Blazor.Schedule** NuGet package to the application using the **NuGet Package Manager**.

4. You can add the client-side style resources from NuGet package in the `<head>` element of the **~/Pages/_Host.cshtml** page.

```html
<head>
    ....
    ....
    <link href="_content/Syncfusion.Blazor.Themes/bootstrap4.css" rel="stylesheet" />
</head>
```

## Adding component package to the application

Open **~/_Imports.razor** file and import the **Syncfusion.Blazor.Schedule** package.

```csharp
  @using Syncfusion.Blazor.Schedule
```

## Add SyncfusionBlazor service in Startup file

Open the **Startup.cs** file and add services required by Syncfusion components using **services.AddSyncfusionBlazor()** method. Add this method in the **ConfigureServices** function as follows.

```csharp
 using Syncfusion.Blazor;

 namespace BlazorApplication
{
    public class Startup
{
    ....
    ....
        public void ConfigureServices(IServiceCollection services)
    {
        ....
        ....
        services.AddSyncfusionBlazor();
    }
}
}

```

## Initialize the Scheduler component

The [Blazor Scheduler](https://www.syncfusion.com/blazor-components/blazor-scheduler/) component can be rendered on the page by defining the `SfSchedule` tag helper. Add the following code example to your `index.razor` page which is available within the `~/Pages/` folder, to initialize the Scheduler component.

```csharp
@using Syncfusion.Blazor.Schedule

<SfSchedule TValue="AppointmentData" Height="650px" @bind-SelectedDate="@CurrentDate">
    <ScheduleEventSettings DataSource="@DataSource"></ScheduleEventSettings>
</SfSchedule>

@code{
    DateTime CurrentDate = new DateTime(2020, 2, 14);
    List<AppointmentData> DataSource = new List<AppointmentData>
    {
        new AppointmentData { Id = 1, Subject = "Paris", StartTime = new DateTime(2020, 2, 13, 10, 0, 0) , EndTime = new DateTime(2020, 2, 13, 12, 0, 0) },
        new AppointmentData { Id = 2, Subject = "Germany", StartTime = new DateTime(2020, 2, 15, 10, 0, 0) , EndTime = new DateTime(2020, 2, 15, 12, 0, 0) }
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

The scheduler with the appointments will be rendered as shown in the following image.

![Scheduler with appointments](../images/appointments.png)

> You can refer to our [Blazor Scheduler](https://www.syncfusion.com/blazor-components/blazor-scheduler/) feature tour page for its groundbreaking feature representations. You can also explore our [Blazor Scheduler example](https://blazor.syncfusion.com/demos/scheduler/overview?theme=bootstrap4/) to understand how to manage appointments with multiple resources.
