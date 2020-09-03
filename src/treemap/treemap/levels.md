# Levels

You can give 'n' number of levels to the TreeMap. Each level is separated using the [`GroupPath`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.TreeMap.TreeMapLevel.html#Syncfusion_Blazor_TreeMap_TreeMapLevel_GroupPath) property.

The following customization options are available to customize the TreeMap levels.

## Group path

The [`GroupPath`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.TreeMap.TreeMapLevel.html#Syncfusion_Blazor_TreeMap_TreeMapLevel_GroupPath) property is used to separate each level in the TreeMap. The GroupPath accepts a field name in [`DataSource`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.TreeMap.SfTreeMap-1.html#Syncfusion_Blazor_TreeMap_SfTreeMap_1_DataSource).

In the following example, three levels are added and each level is configured using the [`GroupPath`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.TreeMap.TreeMapLevel.html#Syncfusion_Blazor_TreeMap_TreeMapLevel_GroupPath) property.

```csharp
@using Syncfusion.Blazor.TreeMap

<SfTreeMap WeightValuePath="EmployeeCount"
            TValue="Employee"
            DataSource="Employees"
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

![TreeMap with multiple levels](images/Levels/grouppath.png)

## Gap between groups

The [`GroupGap`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.TreeMap.TreeMapLevel.html#Syncfusion_Blazor_TreeMap_TreeMapLevel_GroupGap) property is used to separate an item from every group or another item to differentiate the levels mentioned in the TreeMap.

```csharp
@using Syncfusion.Blazor.TreeMap

<SfTreeMap WeightValuePath="EmployeeCount"
            TValue="Employee"
            DataSource="Employees"
            Palette='new string[] {"#f44336", "#29b6f6", "#ab47bc", "#ffc107", "#5c6bc0", "#009688"}'>
    <TreeMapLevels>
        <TreeMapLevel GroupPath="Country" GroupGap="10">
            <TreeMapLevelBorder Color="black" Width="0.5">
            </TreeMapLevelBorder>
        </TreeMapLevel>
        <TreeMapLevel GroupPath="JobDescription" GroupGap="10">
            <TreeMapLevelBorder Color="black" Width="0.5">
            </TreeMapLevelBorder>
        </TreeMapLevel>
        <TreeMapLevel GroupPath="JobGroup" GroupGap="10">
            <TreeMapLevelBorder Color="black" Width="0.5">
            </TreeMapLevelBorder>
        </TreeMapLevel>
    </TreeMapLevels>
</SfTreeMap>
```

> Refer [code block](#group-path) to know the property value of `Employees`.

![TreeMap items with group gap](images/Levels/groupgap.png)

## Header format and alignment

You can customize header using the [`HeaderFormat`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.TreeMap.TreeMapLevel.html#Syncfusion_Blazor_TreeMap_TreeMapLevel_HeaderFormat) property in which the fields are mapping from the [`DataSource`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.TreeMap.SfTreeMap-1.html#Syncfusion_Blazor_TreeMap_SfTreeMap_1_DataSource). You can also align the header using the [`HeaderAlignment`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.TreeMap.TreeMapLevel.html#Syncfusion_Blazor_TreeMap_TreeMapLevel_HeaderAlignment) property.

```csharp
@using Syncfusion.Blazor.TreeMap

<SfTreeMap WeightValuePath="EmployeeCount"
            TValue="Employee"
            DataSource="Employees"
            Palette='new string[] {"#f44336", "#29b6f6", "#ab47bc", "#ffc107", "#5c6bc0", "#009688"}'>
    <TreeMapLevels>
        <TreeMapLevel GroupPath="Country" HeaderFormat="${Country}-${EmployeeCount}" HeaderAlignment="Alignment.Center">
            <TreeMapLevelBorder Color="black" Width="0.5">
            </TreeMapLevelBorder>
        </TreeMapLevel>
        <TreeMapLevel GroupPath="JobDescription" GroupGap="10" HeaderFormat="${JobDescription}-${EmployeeCount}" HeaderAlignment="Alignment.Far">
            <TreeMapLevelBorder Color="black" Width="0.5">
            </TreeMapLevelBorder>
        </TreeMapLevel>
        <TreeMapLevel GroupPath="JobGroup" GroupGap="10" HeaderFormat="${JobGroup}-${EmployeeCount}" HeaderAlignment="Alignment.Near">
            <TreeMapLevelBorder Color="black" Width="0.5">
            </TreeMapLevelBorder>
        </TreeMapLevel>
    </TreeMapLevels>
</SfTreeMap>
```

> Refer [code block](#group-path) to know the property value of `Employees`.

![TreeMap with customized header](images/Levels/headeralignment.png)

## Header height and style

You can customize the font color, family, weight, and size using the [`TreeMapHeaderStyle`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.TreeMap.TreeMapLevel.html#Syncfusion_Blazor_TreeMap_TreeMapLevel_HeaderStyle) tag. Based on font size, the header height can be given using the [`HeaderHeight`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.TreeMap.TreeMapLevel.html#Syncfusion_Blazor_TreeMap_TreeMapLevel_HeaderHeight) property in levels.

```csharp
@using Syncfusion.Blazor.TreeMap

<SfTreeMap WeightValuePath="EmployeeCount"
            TValue="Employee"
            DataSource="Employees"
            Palette='new string[] {"#f44336", "#29b6f6", "#ab47bc", "#ffc107", "#5c6bc0", "#009688"}'>
    <TreeMapLevels>
        <TreeMapLevel GroupPath="Country" HeaderHeight="35">
            <TreeMapHeaderStyle Size="15px"></TreeMapHeaderStyle>
            <TreeMapLevelBorder Color="black" Width="0.5">
            </TreeMapLevelBorder>
        </TreeMapLevel>
        <TreeMapLevel GroupPath="JobDescription" HeaderHeight="45">
            <TreeMapHeaderStyle Size="15px"></TreeMapHeaderStyle>
            <TreeMapLevelBorder Color="black" Width="0.5">
            </TreeMapLevelBorder>
        </TreeMapLevel>
        <TreeMapLevel GroupPath="JobGroup" HeaderHeight="40">
            <TreeMapHeaderStyle Size="15px"></TreeMapHeaderStyle>
            <TreeMapLevelBorder Color="black" Width="0.5">
            </TreeMapLevelBorder>
        </TreeMapLevel>
    </TreeMapLevels>
</SfTreeMap>
```

> Refer [code block](#group-path) to know the property value of `Employees`.

![TreeMap with custom header height and style](images/Levels/headerHeight.png)
