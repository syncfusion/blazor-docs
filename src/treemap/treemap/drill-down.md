# Drill-down

The TreeMap component supports drill-down to expose the hierarchy achieved by clicking a node. If you click an item in TreeMap, the TreeMap will be moved to the next level or sub level. The TreeMap will be returned back to the previous level by clicking the node header. A single level of the TreeMap is visible at a time.

## Perform drill-down

The TreeMap elements can be drilled down by setting the [`EnableDrillDown`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeMap.SfTreeMap~EnableDrillDown.html) property to true. You can view the hierarchy of the TreeMap by clicking the TreeMap items and move to the previous level by clicking the drill-down header.

The drill-down concepts are shown in the following code example.

```csharp
@using Syncfusion.Blazor.TreeMap

<SfTreeMap WeightValuePath="EmployeeCount"
            TValue="Employee"
            DataSource="Employees"
            EnableDrillDown=true
            Palette='new string[] {"#f44336", "#29b6f6", "#ab47bc", "#ffc107", "#5c6bc0", "#009688"}'>
    <TreeMapLevels>
        <TreeMapLevel GroupPath="Country">
            <TreeMapLevelBorder Color="black" Width="0.5">
            </TreeMapLevelBorder>
        </TreeMapLevel>
        <TreeMapLevel GroupPath="JobDescription">
            <TreeMapLevelBorder Color="black" Width="0.5">
            </TreeMapLevelBorder>
        </TreeMapLevel>
        <TreeMapLevel GroupPath="JobGroup">
            <TreeMapLevelBorder Color="black" Width="0.5">
            </TreeMapLevelBorder>
        </TreeMapLevel>
    </TreeMapLevels>
</SfTreeMap>

@code{
    public class Employee
    {
        public string Country;
        public string JobDescription;
        public string JobGroup;
        public int EmployeeCount;
    };

    private List<Employee> Employees = new List<Employee> {
        new Employee { Country= "USA", JobDescription= "Sales", JobGroup= "Executive", EmployeeCount= 20 },
        new Employee { Country= "USA", JobDescription= "Sales", JobGroup= "Analyst", EmployeeCount= 30 },
        new Employee { Country= "USA", JobDescription= "Marketing", EmployeeCount= 40 },
        new Employee { Country= "USA", JobDescription= "Management", EmployeeCount= 80 },
        new Employee { Country= "India", JobDescription= "Technical", JobGroup= "Testers", EmployeeCount= 100 },
        new Employee { Country= "India", JobDescription= "HR Executives", EmployeeCount= 30 },
        new Employee { Country= "India", JobDescription= "Accounts", EmployeeCount= 40 },
        new Employee { Country= "UK", JobDescription= "Technical", JobGroup= "Testers", EmployeeCount= 30 },
        new Employee { Country= "UK", JobDescription= "HR Executives", EmployeeCount= 50 },
        new Employee { Country= "UK", JobDescription= "Accounts", EmployeeCount= 60 }
    };
}
```

![TreeMap with drill down option](images/drilldown/drilldown.png)

## On-demand data loading

In normal drill-down process, all the child items are rendered in DOM, and they are visible at initial time of TreeMap rendering. But, on-demand data loading, it will not render child items at initial time. The child nodes will be rendered on the drill-down process only. By setting the [`DrillDownView`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeMap.SfTreeMap~DrillDownView.html) property to true, you can enable the drill down view at a initial rendering.

In the following sample, on-demand data loading is shown.

```csharp
@using Syncfusion.Blazor.TreeMap

<SfTreeMap WeightValuePath="EmployeeCount"
             TValue="Employee"
            DataSource="Employees"
            EnableDrillDown=true
            DrillDownView="true"
            Palette='new string[] {"#f44336", "#29b6f6", "#ab47bc", "#ffc107", "#5c6bc0", "#009688"}'>
    <TreeMapLevels>
        <TreeMapLevel GroupPath="Country">
            <TreeMapLevelBorder Color="black" Width="0.5">
            </TreeMapLevelBorder>
        </TreeMapLevel>
        <TreeMapLevel GroupPath="JobDescription">
            <TreeMapLevelBorder Color="black" Width="0.5">
            </TreeMapLevelBorder>
        </TreeMapLevel>
        <TreeMapLevel GroupPath="JobGroup">
            <TreeMapLevelBorder Color="black" Width="0.5">
            </TreeMapLevelBorder>
        </TreeMapLevel>
    </TreeMapLevels>
</SfTreeMap>
```

> Refer [code block](#perform-drill-down) to know the property value of `Employees`.

![TreeMap with on demand data loading](images/drilldown/drilldownView.png)

## Breadcrumb support

Using breadcrumb navigation, you can directly drill up to any level of parent, and it displays the level from root parent to the current level at the top layout of TreeMap.

You can show or hide the breadcrumb using the [`EnableBreadcrumb`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeMap.SfTreeMap~EnableBreadcrumb.html) API. You can also customize the breadcrumb connector using the [`BreadcrumbConnector`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeMap.SfTreeMap~BreadcrumbConnector.html) property. By default, `-` is the connector.

```csharp
@using Syncfusion.Blazor.TreeMap

<SfTreeMap WeightValuePath="EmployeeCount"
             TValue="Employee"
            DataSource="Employees"
            EnableDrillDown=true
            EnableBreadcrumb="true"
            BreadcrumbConnector=" -> "
            Palette='new string[] {"#f44336", "#29b6f6", "#ab47bc", "#ffc107", "#5c6bc0", "#009688"}'>
    <TreeMapLevels>
        <TreeMapLevel GroupPath="Country">
            <TreeMapLevelBorder Color="black" Width="0.5">
            </TreeMapLevelBorder>
        </TreeMapLevel>
        <TreeMapLevel GroupPath="JobDescription">
            <TreeMapLevelBorder Color="black" Width="0.5">
            </TreeMapLevelBorder>
        </TreeMapLevel>
        <TreeMapLevel GroupPath="JobGroup">
            <TreeMapLevelBorder Color="black" Width="0.5">
            </TreeMapLevelBorder>
        </TreeMapLevel>
    </TreeMapLevels>
</SfTreeMap>
```

> Refer [code block](#perform-drill-down) to know the property value of `Employees`.

![TreeMap with breadcrumb](images/drilldown/Breadcrumb.png)