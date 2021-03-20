# Scheduling Tasks

The Gantt provides support for automatic and manual task scheduling modes. It is used to indicate whether the start date and end date of all the tasks will be automatically validated or not. `TaskMode` is the property used to change the schedule mode of a task.

The Gantt control supports three types of mode. They are:

* `Auto`: All the tasks are automatically validate.
* `Manual`: All the tasks are manually validate by the user.
* `Custom`: Both Auto and Manual tasks are render by mapped from data source.

>Note: The default value of `TaskMode` is `Auto`.

## Automatically Scheduled Tasks

When the `TaskMode` property is set as `Auto`, the start date and end date of all the tasks in the project will be automatically validated. That is, dates are validated based on various factors such as working time, holidays, weekends and predecessors.

```csharp
@using Syncfusion.Blazor.Gantt
<SfGantt DataSource="@TaskCollection" Height="450px" TaskMode="ScheduleMode.Auto" Width="900px" TreeColumnIndex="1" Toolbar="@(new List<string>() { "Add", "Edit", "Update", "Delete", "Cancel", "ExpandAll", "CollapseAll" })">
    <GanttTaskFields Id="TaskId" Name="TaskName" StartDate="StartDate" EndDate="EndDate" Duration="Duration" Progress="Progress"
            ParentID="ParentId">
    </GanttTaskFields>
    <GanttEditSettings AllowEditing="true" AllowAdding="true" AllowDeleting="true"></GanttEditSettings>
</SfGantt>

@code{
    public List<TaskData> TaskCollection { get; set; }
    protected override void OnInitialized()
    {
        this.TaskCollection = GetTaskCollection();
    }
    public class TaskData
    {
        public int TaskId { get; set; }
        public string TaskName { get; set; }
        public DateTime StartDate { get; set; }
        public DateTime EndDate { get; set; }
        public string Duration { get; set; }
        public int Progress { get; set; }
        public int? ParentId { get; set; }
    }
    public static List <TaskData> GetTaskCollection() {
        List <TaskData> Tasks = new List <TaskData> () {
            new TaskData() {
                TaskId = 1,
                TaskName = "Project initiation",
                StartDate = new DateTime(2019, 03, 28),
                EndDate = new DateTime(2019, 07, 28),
                Duration="4"
            },
            new TaskData() {
                TaskId = 2,
                TaskName = "Identify Site location",
                StartDate = new DateTime(2019, 03, 29),
                Progress = 30,
                ParentId = 1,
                Duration="2"
            },
            new TaskData() {
                TaskId = 3,
                TaskName = "Perform soil test",
                StartDate = new DateTime(2019, 03, 29),
                ParentId = 1,
                Duration="4"
            },
            new TaskData() {
                TaskId = 4,
                TaskName = "Soil test approval",
                StartDate = new DateTime(2019, 03, 29),
                Duration = "1",
                Progress = 30,
                ParentId = 1,
            },
            new TaskData() {
                TaskId = 5,
                TaskName = "Project estimation",
                StartDate = new DateTime(2019, 03, 29),
                EndDate = new DateTime(2019, 04, 2),
                Duration="4"
            },
            new TaskData() {
                TaskId = 6,
                TaskName = "Develop floor plan for estimation",
                StartDate = new DateTime(2019, 03, 29),
                Duration = "3",
                Progress = 30,
                ParentId = 5
            },
            new TaskData() {
                TaskId = 7,
                TaskName = "List materials",
                StartDate = new DateTime(2019, 04, 01),
                Duration = "3",
                Progress = 30,
                ParentId = 5
            },
            new TaskData() {
                TaskId = 8,
                TaskName = "Estimation approval",
                StartDate = new DateTime(2019, 04, 01),
                Duration = "2",
                ParentId = 5
            }
        };
        return Tasks;
    }
}
```

## Manually Scheduled Tasks

When the `TaskMode` property is set as `Manual`, the start date and end date of all the tasks in the project will be same as given in the data source. That is, dates are not validated based on various factors such as dependencies between tasks, holidays, weekends, working time.
We can restrict this mode in predecessor validation alone. That is, we can automatically validate the dates based on predecessor values by enabling the `ValidateManualTasksOnLinking` property.

```csharp
@using Syncfusion.Blazor.Gantt
<SfGantt DataSource="@TaskCollection" Height="450px" TaskMode="ScheduleMode.Manual" ValidateManualTasksOnLinking="true" Width="900px" TreeColumnIndex="1" Toolbar="@(new List<string>() { "Add", "Edit", "Update", "Delete", "Cancel", "ExpandAll", "CollapseAll" })">
    <GanttTaskFields Id="TaskId" Name="TaskName" StartDate="StartDate" EndDate="EndDate" Duration="Duration" Progress="Progress"
            ParentID="ParentId" Dependency="Predecessor">
    </GanttTaskFields>
    <GanttEditSettings AllowEditing="true" AllowAdding="true" AllowDeleting="true" AllowTaskbarEditing="true"></GanttEditSettings>
</SfGantt>

@code{
    public List<TaskData> TaskCollection { get; set; }
    protected override void OnInitialized()
    {
        this.TaskCollection = GetTaskCollection();
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
        public int? ParentId { get; set; }
    }
    public static List <TaskData> GetTaskCollection() {
        List <TaskData> Tasks = new List <TaskData> () {
            new TaskData() {
                TaskId = 1,
                TaskName = "Project initiation",
                StartDate = new DateTime(2019, 03, 28),
                EndDate = new DateTime(2019, 07, 28),
                Duration="4"
            },
            new TaskData() {
                TaskId = 2,
                TaskName = "Identify Site location",
                StartDate = new DateTime(2019, 03, 29),
                Progress = 30,
                ParentId = 1,
                Duration="2"
            },
            new TaskData() {
                TaskId = 3,
                TaskName = "Perform soil test",
                StartDate = new DateTime(2019, 03, 29),
                ParentId = 1,
                Duration="4"
            },
            new TaskData() {
                TaskId = 4,
                TaskName = "Soil test approval",
                StartDate = new DateTime(2019, 03, 29),
                Duration = "4",
                Progress = 30,
                ParentId = 1,
            },
            new TaskData() {
                TaskId = 5,
                TaskName = "Project estimation",
                StartDate = new DateTime(2019, 03, 29),
                EndDate = new DateTime(2019, 04, 2),
                Duration="4"
            },
            new TaskData() {
                TaskId = 6,
                TaskName = "Develop floor plan for estimation",
                StartDate = new DateTime(2019, 03, 29),
                Duration = "3",
                Progress = 30,
                ParentId = 5
            },
            new TaskData() {
                TaskId = 7,
                TaskName = "List materials",
                StartDate = new DateTime(2019, 04, 01),
                Duration = "3",
                Progress = 30,
                ParentId = 5
            },
            new TaskData() {
                TaskId = 8,
                TaskName = "Estimation approval",
                StartDate = new DateTime(2019, 04, 01),
                Duration = "2",
                ParentId = 5
            }
        };
        return Tasks;
    }
}
```

## Custom

When the `TaskMode` property is set as `Custom`, the scheduling mode for each tasks will be mapped from the data source field. The `Boolean` property `GanttTaskFields.Manual` is used to map the manual scheduling mode field from the data source.

```csharp

import { Gantt, Toolbar, Edit, Selection } from '@syncfusion/ej2-gantt';

Gantt.Inject(Toolbar, Edit, Selection);
let GanttData: Object[]  = [
    {
        'TaskID': 1,
        'TaskName': 'Parent Task 1',
        'StartDate': new Date('02/27/2017'),
        'EndDate': new Date('03/03/2017'),
        'Progress': '40',
        'isManual' : true,
        'Children': [
             { 'TaskID': 2, 'TaskName': 'Child Task 1', 'StartDate': new Date('02/27/2017'),
             'EndDate': new Date('03/03/2017'), 'Progress': '40' },
             { 'TaskID': 3, 'TaskName': 'Child Task 2', 'StartDate': new Date('02/26/2017'),
             'EndDate': new Date('03/03/2017'), 'Progress': '40', 'isManual': true },
             { 'TaskID': 4, 'TaskName': 'Child Task 3', 'StartDate': new Date('02/27/2017'),
             'EndDate': new Date('03/03/2017'), 'Duration': 5, 'Progress': '40', }
        ]
    },
    {
        'TaskID': 5,
        'TaskName': 'Parent Task 2',
        'StartDate': new Date('03/05/2017'),
        'EndDate': new Date('03/09/2017'),
        'Progress': '40',
        'isManual': true,
        'Children': [
             { 'TaskID': 6, 'TaskName': 'Child Task 1', 'StartDate': new Date('03/06/2017'),
             'EndDate': new Date('03/09/2017'), 'Progress': '40' },
             { 'TaskID': 7, 'TaskName': 'Child Task 2', 'StartDate': new Date('03/06/2017'),
             'EndDate': new Date('03/09/2017'), 'Progress': '40', },
             { 'TaskID': 8, 'TaskName': 'Child Task 3', 'StartDate': new Date('02/28/2017'),
             'EndDate': new Date('03/05/2017'), 'Progress': '40', 'isManual': true },
             { 'TaskID': 9, 'TaskName': 'Child Task 4', 'StartDate': new Date('03/04/2017'),
             'EndDate': new Date('03/09/2017'), 'Progress': '40', 'isManual': true }
        ]
    },
    {
        'TaskID': 10,
        'TaskName': 'Parent Task 3',
        'StartDate': new Date('03/13/2017'),
        'EndDate': new Date('03/17/2017'),
        'Progress': '40',
        'Children': [
             { 'TaskID': 11, 'TaskName': 'Child Task 1', 'StartDate': new Date('03/13/2017'),
             'EndDate': new Date('03/17/2017'), 'Progress': '40' },
             { 'TaskID': 12, 'TaskName': 'Child Task 2', 'StartDate': new Date('03/13/2017'),
             'EndDate': new Date('03/17/2017'), 'Progress': '40', },
             { 'TaskID': 13, 'TaskName': 'Child Task 3', 'StartDate': new Date('03/13/2017'),
             'EndDate': new Date('03/17/2017'), 'Progress': '40', },
             { 'TaskID': 14, 'TaskName': 'Child Task 4', 'StartDate': new Date('03/12/2017'),
             'EndDate': new Date('03/17/2017'), 'Progress': '40', 'isManual': true },
             { 'TaskID': 15, 'TaskName': 'Child Task 5', 'StartDate': new Date('03/13/2017'),
             'EndDate': new Date('03/17/2017'), 'Progress': '40' }
        ]
    }
];
let gantt: Gantt = new Gantt({
    dataSource: GanttData,
    taskFields: {
        id: 'TaskID',
        name: 'TaskName',
        startDate: 'StartDate',
        duration: 'Duration',
        progress: 'Progress',
        endDate: 'EndDate',
        dependency: 'Predecessor',
        child: 'Children',
        manual: 'isManual',
    },
    taskMode : 'Custom',
    height: '450px',
    toolbar: ['Add', 'Edit', 'Update', 'Delete', 'Cancel', 'ExpandAll', 'CollapseAll', 'Search'],
    columns: [
        { field: 'TaskID', visible: false},
        {field: 'TaskName'},
        { field: 'isManual'}
    ],
    validateManualTasksOnLinking: true,
    treeColumnIndex: 1,
    editSettings: {
        allowEditing: true,
        allowDeleting: true,
        allowTaskbarEditing: true,
        showDeleteConfirmDialog: true
    },
});
gantt.appendTo('#Gantt');

```

## Unscheduled Tasks

Unscheduled tasks are planned for a project without any definite schedule dates. The Gantt Chart component supports rendering the unscheduled tasks. You can create or update the tasks with anyone of start date, end date, and duration values or none. You can enable or disable the unscheduled tasks by using the `AllowUnscheduledTasks` property. The following images represent the various types of unscheduled tasks in Gantt Chart.

### Start Date Only

![Alt text](images/startDate-only.png)

### End Date Only

![Alt text](images/endDate-only.png)

### Duration Only

![Alt text](images/duration-only.png)

### Milestone

A milestone is a task that has no start and end dates, but it has a duration value of zero. It is represented as follows.

![Alt text](images/milestone.png)

## Define unscheduled tasks in data source

You can define the various types of unscheduled tasks in the data source as follows

```csharp
@using Syncfusion.Blazor.Gantt
<SfGantt DataSource="@TaskCollection" Height="450px" Width="700px" AllowUnscheduledTasks="true">
    <GanttTaskFields Id="TaskId" Name="TaskName" StartDate="StartDate" EndDate="EndDate"
            Duration="Duration" Progress="Progress" Child="SubTasks">
    </GanttTaskFields>
</SfGantt>

@code{
    public List<TaskData> TaskCollection { get; set; }
    protected override void OnInitialized()
    {
        this.TaskCollection = GetTaskCollection();
    }

    public class TaskData
    {
        public int TaskId { get; set; }
        public string TaskName { get; set; }
        public DateTime? StartDate { get; set; }
        public DateTime? EndDate { get; set; }
        public string Duration { get; set; }
        public int Progress { get; set; }
    }

    public static List <TaskData> GetTaskCollection() {
    List <TaskData> Tasks = new List <TaskData> () {
        new TaskData() {
            TaskId = 1,
            TaskName = "Project initiation",
            Duration = "4"
        },
        new TaskData() {
            TaskId = 2,
            TaskName = "Identify site location",
            StartDate = new DateTime(2019, 04, 02)
        },
        new TaskData() {
            TaskId = 3,
            TaskName = "Perform soil test",
            EndDate = new DateTime(2019, 04, 08)
        },
        new TaskData() {
            TaskId = 4,
            TaskName = "Soil test approval",
            StartDate = new DateTime(2019, 04, 02),
            EndDate = new DateTime(2019, 04, 06),
            Progress = 50
        },
        new TaskData() {
            TaskId = 5,
            TaskName = "Project estimation",
            Duration = "0"
        }
    };

    return Tasks;
}
}
```

![Alt text](images/unscheduledTasks.png)

> NOTE
> If the `AllowUnscheduledTasks` property is set to false, then the Gantt Chart component automatically calculates the scheduled date values with a default value of duration 1 and the project start date is considered as the start date for the task.

## Working Time Range

In the Gantt Chart component, working hours in a day for a project can be defined by using the `DayWorkingTime` property. Based on the working hours, automatic date scheduling and duration validations for a task are performed.

The following code snippet explains how to define the working time range for the project in Gantt Chart.

```csharp
@using Syncfusion.Blazor.Gantt
<SfGantt DataSource="@TaskCollection" Height="450px" Width="700px">
    <GanttTaskFields Id="TaskId" Name="TaskName" StartDate="StartDate" EndDate="EndDate"
              Duration="Duration" Progress="Progress" Child="SubTasks">
    </GanttTaskFields>
    <GanttDayWorkingTimeCollection>
        <GanttDayWorkingTime From="9" To="18"></GanttDayWorkingTime>
    </GanttDayWorkingTimeCollection>
    <GanttTimelineSettings TimelineUnitSize="60">
        <GanttTopTierSettings Unit="TimelineViewMode.Day" Format="MMM dd,yyyy"></GanttTopTierSettings>
        <GanttBottomTierSettings Unit="TimelineViewMode.Hour" Format="h.mm a"></GanttBottomTierSettings>
    </GanttTimelineSettings>
</SfGantt>

@code{
    public List<TaskData> TaskCollection { get; set; }
    protected override void OnInitialized()
    {
        this.TaskCollection = GetTaskCollection();
    }

    public class TaskData
    {
        public int TaskId { get; set; }
        public string TaskName { get; set; }
        public DateTime StartDate { get; set; }
        public DateTime EndDate { get; set; }
        public string Duration { get; set; }
        public int Progress { get; set; }
        public List<TaskData> SubTasks { get; set; }
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
                    TaskName = "Identify site location",
                    StartDate = new DateTime(2019, 04, 02),
                    Duration = "1",
                    Progress = 70,
                },
                new TaskData() {
                    TaskId = 3,
                    TaskName = "Perform soil test",
                    StartDate = new DateTime(2019, 04, 02),
                    Duration = "1",
                    Progress = 50
                },
                new TaskData() {
                    TaskId = 4,
                    TaskName = "Soil test approval",
                    StartDate = new DateTime(2019, 04, 02),
                    Duration = "1",
                    Progress = 50
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
                    Duration = "1",
                    Progress = 70
                },
                new TaskData() {
                    TaskId = 7,
                    TaskName = "List materials",
                    StartDate = new DateTime(2019, 04, 04),
                    Duration = "1",
                    Progress = 50
                },
            })
        }
    };

    return Tasks;
}
}
```

The following screen shot shows working time range in Gantt Chart component.

![Alt text](images/working-time-range.png)

> NOTE
>* Individual tasks can lie between any time within the defined working time range of the project.
>* The `DayWorkingTime` property is used to define the working time for the whole project.

## Weekend/Non-working days

Non-working days/weekend are used to represent the non-productive days in a project. You can define the non-working days in a week using the `WorkWeek` property in Gantt Chart.

```csharp
@using Syncfusion.Blazor.Gantt
<SfGantt DataSource="@TaskCollection" WorkWeek="@(new string[] { "Sunday", "Monday", "Tuesday", "Wednesday", "Thursday" })"
          HighlightWeekends="true" Height="450px" Width="900px">
    <GanttTaskFields Id="TaskId" Name="TaskName" StartDate="StartDate" EndDate="EndDate"
              Duration="Duration" Progress="Progress" Child="SubTasks">
    </GanttTaskFields>
</SfGantt>

@code{
    public List<TaskData> TaskCollection { get; set; }
    protected override void OnInitialized()
    {
        this.TaskCollection = GetTaskCollection();
    }

    public class TaskData
    {
        public int TaskId { get; set; }
        public string TaskName { get; set; }
        public DateTime StartDate { get; set; }
        public DateTime EndDate { get; set; }
        public string Duration { get; set; }
        public int Progress { get; set; }
        public List<TaskData> SubTasks { get; set; }
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
                },
                new TaskData() {
                    TaskId = 3,
                    TaskName = "Perform soil test",
                    StartDate = new DateTime(2019, 04, 02),
                    Duration = "4",
                    Progress = 40,
                },
                new TaskData() {
                    TaskId = 4,
                    TaskName = "Soil test approval",
                    StartDate = new DateTime(2019, 04, 02),
                    Duration = "0",
                    Progress = 30
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
                },
                new TaskData() {
                    TaskId = 7,
                    TaskName = "List materials",
                    StartDate = new DateTime(2019, 04, 04),
                    Duration = "3",
                    Progress = 40
                },
                new TaskData() {
                    TaskId = 8,
                    TaskName = "Estimation approval",
                    StartDate = new DateTime(2019, 04, 04),
                    Duration = "0",
                    Progress = 30,
                }
            })
        }
    };

    return Tasks;
}
}
```

![Alt text](images/changeWorkweek.png)

> By default, Saturdays and Sundays are considered as non-working days/weekend in a project.
> In the Gantt Chart component, you can make weekend as working day by setting the `IncludeWeekend` property to `true`.