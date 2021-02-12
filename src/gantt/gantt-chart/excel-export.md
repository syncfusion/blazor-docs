---
component: "Gantt Chart"
---

# Excel Export

Gantt Chart supports client-side exporting, which allows you to export its data to the Excel and CSV formats. Use the `ExcelExport` and `CsvExport` methods for exporting. To enable Excel export in the Gantt Chart, set the `AllowExcelExport` to true.

```csharp
@using Syncfusion.Blazor.Gantt
<SfGantt Id="GanttContainer" @ref="Gantt" AllowExcelExport="true" Toolbar="@(new List<string>() { "ExcelExport", "CsvExport" })" DataSource="@TaskCollection" ResourceNameMapping="ResourceName" ResourceIDMapping="ResourceId" Resources="@ResourceCollection" Height="450px" Width="700px">
    <GanttTaskFields Id="TaskId" Name="TaskName" StartDate="StartDate" EndDate="EndDate" Duration="Duration" Progress="Progress" Dependency="Predecessor" ResourceInfo="ResourceId" Child="SubTasks"></GanttTaskFields>
    <GanttEvents OnToolbarClick="ToolbarClickHandler" TValue="TaskData"></GanttEvents>
</SfGantt>

@code{
    public SfGantt<TaskData> Gantt;
    public List<TaskData> TaskCollection { get; set; }
    public List<TaskResource> ResourceCollection { get; set; }
    public void ToolbarClickHandler(ClickEventArgs args)
    {
        if (args.Item.Id == "GanttContainer_excelexport")
        {
            this.Gantt.ExcelExport();
        }
        else if (args.Item.Id == "GanttContainer_csvexport")
        {
            this.Gantt.CsvExport();
        }
    }
    protected override void OnInitialized()
    {
        this.TaskCollection = GetTaskCollection();
        this.ResourceCollection = GetResourceCollection();
    }

    public class TaskData
    {
        public int TaskId { get; set; }
        public string TaskName { get; set; }
        public DateTime StartDate { get; set; }
        public DateTime EndDate { get; set; }
        public string Duration { get; set; }
        public int Progress { get; set; }
        public string Predecessor { get; set; }
        public List<TaskData> SubTasks { get; set; }
        public int[] ResourceId { get; set; }
    }

    public static List <TaskData> GetTaskCollection() {
        List <TaskData> Tasks = new List <TaskData> () {
            new TaskData() {
                TaskId = 1,
                TaskName = "Project initiation",
                StartDate = new DateTime(2019, 04, 02),
                EndDate = new DateTime(2019, 04, 21),
                SubTasks = (new List <TaskData> () {
                    new TaskData() {
                        TaskId = 2,
                        TaskName = "Identify Site location",
                        StartDate = new DateTime(2019, 04, 02),
                        Duration = "0",
                        Progress = 30,
                        ResourceId = new int[] { 1 },
                    },
                    new TaskData() {
                        TaskId = 3,
                        TaskName = "Perform soil test",
                        StartDate = new DateTime(2019, 04, 02),
                        Duration = "4",
                        Predecessor = "2",
                        ResourceId = new int[] {2,3},
                    },
                    new TaskData() {
                        TaskId = 4,
                        TaskName = "Soil test approval",
                        StartDate = new DateTime(2019, 04, 02),
                        Duration = "0",
                        Progress = 30,
                        Predecessor = "3"
                    },
                })
            },
            new TaskData() {
                TaskId = 5,
                TaskName = "Project estimation",
                StartDate = new DateTime(2019, 04, 02),
                EndDate = new DateTime(2019, 04, 21),
                SubTasks = (new List <TaskData> () {
                    new TaskData() {
                        TaskId = 6,
                        TaskName = "Develop floor plan for estimation",
                        StartDate = new DateTime(2019, 04, 04),
                        Duration = "3",
                        Progress = 30,
                        Predecessor = "4",
                        ResourceId = new int[] {4},
                    },
                    new TaskData() {
                        TaskId = 7,
                        TaskName = "List materials",
                        StartDate = new DateTime(2019, 04, 04),
                        Duration = "3",
                        Predecessor = "6",
                        ResourceId = new int[] {2,1},
                    },
                    new TaskData() {
                        TaskId = 8,
                        TaskName = "Estimation approval",
                        StartDate = new DateTime(2019, 04, 04),
                        Duration = "0",
                        Predecessor = "7",
                        ResourceId = new int[] {1,3},
                    }
                })
            }
        };
    return Tasks;
}

    public class TaskResource
    {
        public int ResourceId { get; set; }
        public string ResourceName { get; set; }
    }
    public static List <TaskResource> GetResourceCollection() {
    List <TaskResource> Resources = new List <TaskResource> () {
        new TaskResource() {
            ResourceId = 1,
            ResourceName = "Martin Tamer"
        },
        new TaskResource() {
            ResourceId = 2,
            ResourceName = "Rose Fuller"
        },
        new TaskResource() {
            ResourceId = 3,
            ResourceName = "Margaret Buchanan"
        },
        new TaskResource() {
            ResourceId = 4,
            ResourceName = "Fuller King"
        }
    };
    return Resources;
}
}
```

## Customize the Excel export

Gantt Chart Excel export allows the users to customize the exported document based on requirement.

### Export hidden columns

In Gantt Chart, the Excel export provides an option to export hidden columns by defining `IncludeHiddenColumn` as `true`.

```csharp
@using Syncfusion.Blazor.Gantt
<SfGantt Id="GanttContainer" @ref="Gantt" AllowExcelExport="true" Toolbar="@(new List<string>() { "ExcelExport", "CsvExport" })" DataSource="@TaskCollection" ResourceNameMapping="ResourceName" ResourceIDMapping="ResourceId" Resources="@ResourceCollection" Height="450px" Width="700px">
    <GanttTaskFields Id="TaskId" Name="TaskName" StartDate="StartDate" EndDate="EndDate" Duration="Duration" Progress="Progress" Dependency="Predecessor" ResourceInfo="ResourceId" Child="SubTasks"></GanttTaskFields>
    <GanttEvents OnToolbarClick="ToolbarClickHandler" TValue="TaskData"></GanttEvents>
    <GanttColumns>
        <GanttColumn Field="TaskId" HeaderText="Task Id" Width="150"></GanttColumn>
        <GanttColumn Field="TaskName" HeaderText="Task Name" Width="250"></GanttColumn>
        <GanttColumn Field="ResourceId" Width="150" HeaderText="Resource" Visible="false"></GanttColumn>
        <GanttColumn Field="StartDate" HeaderText="StartDate" Width="250" Visible="false"></GanttColumn>
        <GanttColumn Field="Duration" Width="150" HeaderText="Duration"></GanttColumn>
        <GanttColumn Field="Progress" HeaderText="Progress" Width="250"></GanttColumn>
    </GanttColumns>
</SfGantt>

@code{
    public SfGantt<TaskData> Gantt;
    public List<TaskData> TaskCollection { get; set; }
    public List<TaskResource> ResourceCollection { get; set; }
    public void ToolbarClickHandler(ClickEventArgs args)
    {
        Syncfusion.Blazor.Grids.ExcelExportProperties ExportProperties = new Syncfusion.Blazor.Grids.ExcelExportProperties();
        ExportProperties.IncludeHiddenColumn = true;
        if (args.Item.Id == "GanttContainer_excelexport")
        {
            this.Gantt.ExcelExport(ExportProperties);
        }
        else if (args.Item.Id == "GanttContainer_csvexport")
        {
            this.Gantt.CsvExport(ExportProperties);
        }
    }
    protected override void OnInitialized()
    {
        this.TaskCollection = GetTaskCollection();
        this.ResourceCollection = GetResourceCollection();
    }

    public class TaskData
    {
        public int TaskId { get; set; }
        public string TaskName { get; set; }
        public DateTime StartDate { get; set; }
        public DateTime EndDate { get; set; }
        public string Duration { get; set; }
        public int Progress { get; set; }
        public string Predecessor { get; set; }
        public List<TaskData> SubTasks { get; set; }
        public int[] ResourceId { get; set; }
    }

    public static List <TaskData> GetTaskCollection() {
        List <TaskData> Tasks = new List <TaskData> () {
            new TaskData() {
                TaskId = 1,
                TaskName = "Project initiation",
                StartDate = new DateTime(2019, 04, 02),
                EndDate = new DateTime(2019, 04, 21),
                SubTasks = (new List <TaskData> () {
                    new TaskData() {
                        TaskId = 2,
                        TaskName = "Identify Site location",
                        StartDate = new DateTime(2019, 04, 02),
                        Duration = "0",
                        Progress = 30,
                        ResourceId = new int[] { 1 },
                    },
                    new TaskData() {
                        TaskId = 3,
                        TaskName = "Perform soil test",
                        StartDate = new DateTime(2019, 04, 02),
                        Duration = "4",
                        Predecessor = "2",
                        ResourceId = new int[] {2,3},
                    },
                    new TaskData() {
                        TaskId = 4,
                        TaskName = "Soil test approval",
                        StartDate = new DateTime(2019, 04, 02),
                        Duration = "0",
                        Progress = 30,
                        Predecessor = "3"
                    },
                })
            },
            new TaskData() {
                TaskId = 5,
                TaskName = "Project estimation",
                StartDate = new DateTime(2019, 04, 02),
                EndDate = new DateTime(2019, 04, 21),
                SubTasks = (new List <TaskData> () {
                    new TaskData() {
                        TaskId = 6,
                        TaskName = "Develop floor plan for estimation",
                        StartDate = new DateTime(2019, 04, 04),
                        Duration = "3",
                        Progress = 30,
                        Predecessor = "4",
                        ResourceId = new int[] {4},
                    },
                    new TaskData() {
                        TaskId = 7,
                        TaskName = "List materials",
                        StartDate = new DateTime(2019, 04, 04),
                        Duration = "3",
                        Predecessor = "6",
                        ResourceId = new int[] {2,1},
                    },
                    new TaskData() {
                        TaskId = 8,
                        TaskName = "Estimation approval",
                        StartDate = new DateTime(2019, 04, 04),
                        Duration = "0",
                        Predecessor = "7",
                        ResourceId = new int[] {1,3},
                    }
                })
            }
        };
    return Tasks;
}

    public class TaskResource
    {
        public int ResourceId { get; set; }
        public string ResourceName { get; set; }
    }
    public static List <TaskResource> GetResourceCollection() {
    List <TaskResource> Resources = new List <TaskResource> () {
        new TaskResource() {
            ResourceId = 1,
            ResourceName = "Martin Tamer"
        },
        new TaskResource() {
            ResourceId = 2,
            ResourceName = "Rose Fuller"
        },
        new TaskResource() {
            ResourceId = 3,
            ResourceName = "Margaret Buchanan"
        },
        new TaskResource() {
            ResourceId = 4,
            ResourceName = "Fuller King"
        }
    };
    return Resources;
}
}
```

### Theme

The Excel export also provides an option to include custom theme for exported Excel document.

To apply theme in exported Excel, define the `Theme` in `ExcelExportProperties`.

```csharp
@using Syncfusion.Blazor.Gantt
<SfGantt Id="GanttContainer" @ref="Gantt" AllowExcelExport="true" Toolbar="@(new List<string>() { "ExcelExport" })" DataSource="@TaskCollection" ResourceNameMapping="ResourceName" ResourceIDMapping="ResourceId" Resources="@ResourceCollection" Height="450px" Width="700px">
    <GanttTaskFields Id="TaskId" Name="TaskName" StartDate="StartDate" EndDate="EndDate" Duration="Duration" Progress="Progress" Dependency="Predecessor" ResourceInfo="ResourceId" Child="SubTasks"></GanttTaskFields>
    <GanttEvents OnToolbarClick="ToolbarClickHandler" TValue="TaskData"></GanttEvents>
</SfGantt>

@code{
    public SfGantt<TaskData> Gantt;
    public List<TaskData> TaskCollection { get; set; }
    public List<TaskResource> ResourceCollection { get; set; }
    public void ToolbarClickHandler(ClickEventArgs args)
    {
        Syncfusion.Blazor.Grids.ExcelExportProperties ExportProperties = new Syncfusion.Blazor.Grids.ExcelExportProperties();
        Syncfusion.Blazor.Grids.ExcelTheme Theme = new Syncfusion.Blazor.Grids.ExcelTheme();

        Syncfusion.Blazor.Grids.ExcelStyle ThemeStyle = new Syncfusion.Blazor.Grids.ExcelStyle()
        {
            FontName = "Segoe UI",
            FontColor = "#666666",
            FontSize = 12
        };

        Theme.Header = ThemeStyle;
        Theme.Record = ThemeStyle;
        ExportProperties.Theme = Theme;
        if (args.Item.Id == "GanttContainer_excelexport")
        {
            this.Gantt.ExcelExport(ExportProperties);
        }
    }
    protected override void OnInitialized()
    {
        this.TaskCollection = GetTaskCollection();
        this.ResourceCollection = GetResourceCollection();
    }

    public class TaskData
    {
        public int TaskId { get; set; }
        public string TaskName { get; set; }
        public DateTime StartDate { get; set; }
        public DateTime EndDate { get; set; }
        public string Duration { get; set; }
        public int Progress { get; set; }
        public string Predecessor { get; set; }
        public List<TaskData> SubTasks { get; set; }
        public int[] ResourceId { get; set; }
    }

    public static List <TaskData> GetTaskCollection() {
        List <TaskData> Tasks = new List <TaskData> () {
            new TaskData() {
                TaskId = 1,
                TaskName = "Project initiation",
                StartDate = new DateTime(2019, 04, 02),
                EndDate = new DateTime(2019, 04, 21),
                SubTasks = (new List <TaskData> () {
                    new TaskData() {
                        TaskId = 2,
                        TaskName = "Identify Site location",
                        StartDate = new DateTime(2019, 04, 02),
                        Duration = "0",
                        Progress = 30,
                        ResourceId = new int[] { 1 },
                    },
                    new TaskData() {
                        TaskId = 3,
                        TaskName = "Perform soil test",
                        StartDate = new DateTime(2019, 04, 02),
                        Duration = "4",
                        Predecessor = "2",
                        ResourceId = new int[] {2,3},
                    },
                    new TaskData() {
                        TaskId = 4,
                        TaskName = "Soil test approval",
                        StartDate = new DateTime(2019, 04, 02),
                        Duration = "0",
                        Progress = 30,
                        Predecessor = "3"
                    },
                })
            },
            new TaskData() {
                TaskId = 5,
                TaskName = "Project estimation",
                StartDate = new DateTime(2019, 04, 02),
                EndDate = new DateTime(2019, 04, 21),
                SubTasks = (new List <TaskData> () {
                    new TaskData() {
                        TaskId = 6,
                        TaskName = "Develop floor plan for estimation",
                        StartDate = new DateTime(2019, 04, 04),
                        Duration = "3",
                        Progress = 30,
                        Predecessor = "4",
                        ResourceId = new int[] {4},
                    },
                    new TaskData() {
                        TaskId = 7,
                        TaskName = "List materials",
                        StartDate = new DateTime(2019, 04, 04),
                        Duration = "3",
                        Predecessor = "6",
                        ResourceId = new int[] {2,1},
                    },
                    new TaskData() {
                        TaskId = 8,
                        TaskName = "Estimation approval",
                        StartDate = new DateTime(2019, 04, 04),
                        Duration = "0",
                        Predecessor = "7",
                        ResourceId = new int[] {1,3},
                    }
                })
            }
        };
    return Tasks;
}

    public class TaskResource
    {
        public int ResourceId { get; set; }
        public string ResourceName { get; set; }
    }
    public static List <TaskResource> GetResourceCollection() {
    List <TaskResource> Resources = new List <TaskResource> () {
        new TaskResource() {
            ResourceId = 1,
            ResourceName = "Martin Tamer"
        },
        new TaskResource() {
            ResourceId = 2,
            ResourceName = "Rose Fuller"
        },
        new TaskResource() {
            ResourceId = 3,
            ResourceName = "Margaret Buchanan"
        },
        new TaskResource() {
            ResourceId = 4,
            ResourceName = "Fuller King"
        }
    };
    return Resources;
}
}
```

> By default, material theme is applied to the exported Excel document.

### File name for exported document

You can set the required file name for the exported document by defining the `FileName` property in `ExcelExportProperties`.

```csharp
@using Syncfusion.Blazor.Gantt
<SfGantt Id="GanttContainer" @ref="Gantt" AllowExcelExport="true" Toolbar="@(new List<string>() { "ExcelExport", "CsvExport" })" DataSource="@TaskCollection" ResourceNameMapping="ResourceName" ResourceIDMapping="ResourceId" Resources="@ResourceCollection" Height="450px" Width="700px">
    <GanttTaskFields Id="TaskId" Name="TaskName" StartDate="StartDate" EndDate="EndDate" Duration="Duration" Progress="Progress" Dependency="Predecessor" ResourceInfo="ResourceId" Child="SubTasks"></GanttTaskFields>
    <GanttEvents OnToolbarClick="ToolbarClickHandler" TValue="TaskData"></GanttEvents>
</SfGantt>

@code{
    public SfGantt<TaskData> Gantt;
    public List<TaskData> TaskCollection { get; set; }
    public List<TaskResource> ResourceCollection { get; set; }
    public void ToolbarClickHandler(ClickEventArgs args)
    {
        if (args.Item.Id == "GanttContainer_excelexport")
        {
            Syncfusion.Blazor.Grids.ExcelExportProperties ExportProperties = new Syncfusion.Blazor.Grids.ExcelExportProperties();
            ExportProperties.FileName = "Gantt.xlsx";
            this.Gantt.ExcelExport(ExportProperties);
        }
        else if (args.Item.Id == "GanttContainer_csvexport")
        {
            Syncfusion.Blazor.Grids.ExcelExportProperties ExportProperties = new Syncfusion.Blazor.Grids.ExcelExportProperties();
            ExportProperties.FileName = "Gantt.csv";
            this.Gantt.CsvExport(ExportProperties);
        }
    }
    protected override void OnInitialized()
    {
        this.TaskCollection = GetTaskCollection();
        this.ResourceCollection = GetResourceCollection();
    }

    public class TaskData
    {
        public int TaskId { get; set; }
        public string TaskName { get; set; }
        public DateTime StartDate { get; set; }
        public DateTime EndDate { get; set; }
        public string Duration { get; set; }
        public int Progress { get; set; }
        public string Predecessor { get; set; }
        public List<TaskData> SubTasks { get; set; }
        public int[] ResourceId { get; set; }
    }

    public static List <TaskData> GetTaskCollection() {
        List <TaskData> Tasks = new List <TaskData> () {
            new TaskData() {
                TaskId = 1,
                TaskName = "Project initiation",
                StartDate = new DateTime(2019, 04, 02),
                EndDate = new DateTime(2019, 04, 21),
                SubTasks = (new List <TaskData> () {
                    new TaskData() {
                        TaskId = 2,
                        TaskName = "Identify Site location",
                        StartDate = new DateTime(2019, 04, 02),
                        Duration = "0",
                        Progress = 30,
                        ResourceId = new int[] { 1 },
                    },
                    new TaskData() {
                        TaskId = 3,
                        TaskName = "Perform soil test",
                        StartDate = new DateTime(2019, 04, 02),
                        Duration = "4",
                        Predecessor = "2",
                        ResourceId = new int[] {2,3},
                    },
                    new TaskData() {
                        TaskId = 4,
                        TaskName = "Soil test approval",
                        StartDate = new DateTime(2019, 04, 02),
                        Duration = "0",
                        Progress = 30,
                        Predecessor = "3"
                    },
                })
            },
            new TaskData() {
                TaskId = 5,
                TaskName = "Project estimation",
                StartDate = new DateTime(2019, 04, 02),
                EndDate = new DateTime(2019, 04, 21),
                SubTasks = (new List <TaskData> () {
                    new TaskData() {
                        TaskId = 6,
                        TaskName = "Develop floor plan for estimation",
                        StartDate = new DateTime(2019, 04, 04),
                        Duration = "3",
                        Progress = 30,
                        Predecessor = "4",
                        ResourceId = new int[] {4},
                    },
                    new TaskData() {
                        TaskId = 7,
                        TaskName = "List materials",
                        StartDate = new DateTime(2019, 04, 04),
                        Duration = "3",
                        Predecessor = "6",
                        ResourceId = new int[] {2,1},
                    },
                    new TaskData() {
                        TaskId = 8,
                        TaskName = "Estimation approval",
                        StartDate = new DateTime(2019, 04, 04),
                        Duration = "0",
                        Predecessor = "7",
                        ResourceId = new int[] {1,3},
                    }
                })
            }
        };
    return Tasks;
}

    public class TaskResource
    {
        public int ResourceId { get; set; }
        public string ResourceName { get; set; }
    }
    public static List <TaskResource> GetResourceCollection() {
    List <TaskResource> Resources = new List <TaskResource> () {
        new TaskResource() {
            ResourceId = 1,
            ResourceName = "Martin Tamer"
        },
        new TaskResource() {
            ResourceId = 2,
            ResourceName = "Rose Fuller"
        },
        new TaskResource() {
            ResourceId = 3,
            ResourceName = "Margaret Buchanan"
        },
        new TaskResource() {
            ResourceId = 4,
            ResourceName = "Fuller King"
        }
    };
    return Resources;
}
}
```