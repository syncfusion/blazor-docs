---
title: "Data binding"
component: "Tree Grid"
description: "Learn how to bind list and remote service data in the Blazor Tree Grid component."
---

# Data binding

The Tree Grid uses **SfDataManager**, which supports both RESTful Web Services binding and List binding. The [`DataSource`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.SfTreeGrid~DataSource.html) property can be assigned either using the **SfDataManager** as child component of the Tree Grid Blazor component or list of business objects.
It supports two kinds of data binding method:
* List binding
* Remote service binding

## List binding

In List binding, data source for rendering the Tree Grid component is retrieved from the same application locally.

Two types of Data binding are possible with the Tree Grid component.

* Self-Referential Data binding (Flat Data)
* Hierarchical Data binding

For Self-Referential data binding, you can assign list of business objects to the [`DataSource`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.SfTreeGrid~DataSource.html) property.

For Hierarchy Data binding, the data-source should be assigned as a object array to the **Json** property of the **SfDataManager** and the **Adaptor** property of the SfDataManager should be either **RemoteSaveAdaptor** or **JsonAdaptor**.

### Self-Referential data binding/Flat Data

Tree Grid is rendered from Self-Referential data structures by providing two fields, [`IdMapping`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.SfTreeGrid~IdMapping.html) field and [`ParentIdMapping`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.SfTreeGrid~ParentIdMapping.html) field.

* [`IdMapping`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.SfTreeGrid~IdMapping.html): This field contains unique values used to identify nodes.
* [`ParentIdMapping`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.SfTreeGrid~ParentIdMapping.html): This field contains values that indicate parent nodes.

```csharp

@using Syncfusion.Blazor.TreeGrid;

<SfTreeGrid DataSource="@TreeData" IdMapping="TaskId" ParentIdMapping="ParentId" TreeColumnIndex="1">
    <TreeGridColumns>
        <TreeGridColumn Field="TaskId" HeaderText="Task ID" Width="80" TextAlign="Syncfusion.Blazor.Grids.TextAlign.Right"></TreeGridColumn>
        <TreeGridColumn Field="TaskName" HeaderText="Task Name" Width="160"></TreeGridColumn>
        <TreeGridColumn Field="Duration" HeaderText="Duration" Width="100" TextAlign="Syncfusion.Blazor.Grids.TextAlign.Right"></TreeGridColumn>
        <TreeGridColumn Field="Progress" HeaderText="Progress" Width="100" TextAlign="Syncfusion.Blazor.Grids.TextAlign.Right"></TreeGridColumn>
    </TreeGridColumns>
</SfTreeGrid>

@code{
   public class BusinessObject
    {
        public int TaskId { get; set; }
        public string TaskName { get; set; }
        public int Duration { get; set; }
        public int Progress { get; set; }
        public string Priority { get; set; }
        public int? ParentId { get; set; }
    }

    public List<BusinessObject> TreeData = new List<BusinessObject>();

    protected override void OnInitialized()
    {
        TreeData.Add(new BusinessObject() { TaskId = 1, TaskName = "Parent Task 1", Duration = 10, Progress = 70, ParentId = null, Priority = "High" });
        TreeData.Add(new BusinessObject() { TaskId = 2, TaskName = "Child task 1", Duration = 4, Progress = 80, ParentId = 1, Priority = "Normal" });
        TreeData.Add(new BusinessObject() { TaskId = 3, TaskName = "Child Task 2", Duration = 5, Progress = 65, ParentId = 1, Priority = "Critical" });
        TreeData.Add(new BusinessObject() { TaskId = 4, TaskName = "Parent Task 2", Duration = 6, Progress = 77, ParentId = null, Priority = "Low" });
        TreeData.Add(new BusinessObject() { TaskId = 5, TaskName = "Child Task 5", Duration = 9, Progress = 25, ParentId = 4, Priority = "Normal" });
        TreeData.Add(new BusinessObject() { TaskId = 6, TaskName = "Child Task 6", Duration = 9, Progress = 7, ParentId = 5, Priority = "Normal" });
        TreeData.Add(new BusinessObject() { TaskId = 7, TaskName = "Parent Task 3", Duration = 4, Progress = 45, ParentId = null, Priority = "High" });
        TreeData.Add(new BusinessObject() { TaskId = 8, TaskName = "Child Task 7", Duration = 3, Progress = 38, ParentId = 7, Priority = "Critical" });
        TreeData.Add(new BusinessObject() { TaskId = 9, TaskName = "Child Task 8", Duration = 7, Progress = 70, ParentId = 7, Priority = "Low" });
    }
}
```

### Hierarchy data binding

The [`ChildMapping`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.SfTreeGrid~ChildMapping.html) property is used to map the child records in hierarchy data source.

The following code example shows you how to bind the hierarchical list data into the Tree Grid component.

```csharp

@using Syncfusion.Blazor.TreeGrid;
@using Syncfusion.Blazor.Data;

<SfTreeGrid ChildMapping="Children" TreeColumnIndex="1" DataSource="@TreeData" TValue="BusinessObject" >
    <TreeGridColumns>
        <TreeGridColumn Field="TaskID" HeaderText="Task ID" Width="80" TextAlign="Syncfusion.Blazor.Grids.TextAlign.Right"></TreeGridColumn>
        <TreeGridColumn Field="TaskName" HeaderText="Task Name" Width="160"></TreeGridColumn>
        <TreeGridColumn Field="Duration" HeaderText="Duration" Width="100" TextAlign="Syncfusion.Blazor.Grids.TextAlign.Right"></TreeGridColumn>
        <TreeGridColumn Field="Progress" HeaderText="Progress" Width="100" TextAlign="Syncfusion.Blazor.Grids.TextAlign.Right"></TreeGridColumn>
        <TreeGridColumn Field="Priority" HeaderText="Priority" Width="80"></TreeGridColumn>
    </TreeGridColumns>
</SfTreeGrid>

@code{
    public class BusinessObject
    {
        public int TaskId { get; set; }
        public string TaskName { get; set; }
        public int Duration { get; set; }
        public int Progress { get; set; }
        public string Priority { get; set; }
        public List<BusinessObject> Children { get; set; }
    }
    public List<BusinessObject> TreeData = new List<BusinessObject>();
    protected override void OnInitialized()
    {
        List<BusinessObject> Record1 = new List<BusinessObject>();
        BusinessObject Child1 = new BusinessObject() { TaskId = 2, TaskName = "Plan timeline", Progress = 100, Duration = 5, Priority = "Normal" };
        BusinessObject Child2 = new BusinessObject() { TaskId = 3, TaskName = "Plan budget", Duration = 5, Progress = 100, Priority = "Low" };
        BusinessObject Child3 = new BusinessObject() { TaskId = 4, TaskName = "Allocate resources", Duration = 5, Progress = 100, Priority = "Critical" };
        Record1.Add(Child1);
        Record1.Add(Child2);
        Record1.Add(Child3);
        TreeData.Add(new BusinessObject() { TaskId = 1, TaskName = "Planning", Duration = 10, Progress = 70, Children = Record1, Priority = "High" });


        List<BusinessObject> Record2 = new List<BusinessObject>();
        BusinessObject Child4 = new BusinessObject() { TaskId = 6, TaskName = "Software Specification", Progress = 60, Duration = 3, Priority = "Normal" };
        BusinessObject Child5 = new BusinessObject() { TaskId = 7, TaskName = "Develop Prototype", Duration = 3, Progress = 100, Priority = "Critical" };


        Record2.Add(Child4);
        Record2.Add(Child5);
        TreeData.Add(new BusinessObject() { TaskId = 5, TaskName = "Design", Duration = 3, Progress = 86, Children = Record2, Priority = "High" });
    }
}

```

> ExpandCollapse State maintenance is not supported for Hierarchy Data.
> Batch Editing is not supported for Hierarchy Data.
> `PageSizeMode` --> `All` is not supported for Hierarchy Data.

## Remote Service binding

To bind remote data to Tree Grid component, assign service data as an instance of **SfDataManager** to the [`DataSource`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.SfTreeGrid~DataSource.html) property. To interact with remote data source,  provide the endpoint **url** and define the [`HasChildMapping`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.SfTreeGrid~HasChildMapping.html) property of tree grid.

The Tree Grid provides **Load on Demand** support for rendering remote data. The Load on demand is considered in Tree Grid for the following actions.

* Expanding root nodes.
* Navigating pages, with paging enabled in Tree Grid.

When load on demand is enabled, all the root nodes are rendered in collapsed state at initial load.

When load on demand support is enabled in Tree Grid with paging, the current or active page’s root node alone will be rendered in collapsed state. On expanding the root node, the child nodes will be loaded from the remote server.

When a root node is expanded, its child nodes are rendered and are cached locally, such that on consecutive expand/collapse actions on root node, the child nodes are loaded from the cache instead from the remote server.

Similarly, if the user navigates to a new page, the root nodes of that specific page, will be rendered with request to the remote server.

```csharp

@using Syncfusion.Blazor.TreeGrid;
@using Syncfusion.Blazor.Data;

<SfTreeGrid IdMapping="TaskID" TValue="BusinessObject" ParentIdMapping="ParentItem" HasChildMapping="isParent" AllowPaging="true" TreeColumnIndex="1">
    <SfDataManager Url="https://ej2services.syncfusion.com/production/web-services/api/SelfReferenceData" CrossDomain="true" Adaptor="Syncfusion.Blazor.Adaptors.WebApiAdaptor"></SfDataManager>
    <TreeGridColumns>
        <TreeGridColumn Field="TaskID" HeaderText="Task ID" Width="80" TextAlign="Syncfusion.Blazor.Grids.TextAlign.Right"></TreeGridColumn>
        <TreeGridColumn Field="TaskName" HeaderText="Task Name" Width="160"></TreeGridColumn>
        <TreeGridColumn Field="Duration" HeaderText="Duration" Width="100" TextAlign="Syncfusion.Blazor.Grids.TextAlign.Right"></TreeGridColumn>
        <TreeGridColumn Field="Progress" HeaderText="Progress" Width="100" TextAlign="Syncfusion.Blazor.Grids.TextAlign.Right"></TreeGridColumn>
        <TreeGridColumn Field="Priority" HeaderText="Priority" Width="80"></TreeGridColumn>
    </TreeGridColumns>
</SfTreeGrid>

@code{
    public class BusinessObject
    {
        public int TaskID { get; set; }
        public string TaskName { get; set; }
        public DateTime? StartDate { get; set; }
        public DateTime? EndDate { get; set; }
        public String Progress { get; set; }
        public String Priority { get; set; }
        public double? Duration { get; set; }
        public int? ParentID { get; set; }
        public bool? isParent { get; set; }
        public bool? Approved { get; set; }
        public int? ParentItem { get; set; }
    }
}

```

> * By default, **SfDataManager** uses **ODataAdaptor** for remote data-binding.
> * Based on the RESTful web services, set the corresponding adaptor to SfDataManager. Refer [`here`](https://ej2.syncfusion.com/documentation/data/adaptors/?no-cache=1) for more details.
> * Filtering and searching server-side data operations are not supported in load on demand

### Offline mode

On remote data binding, all tree grid actions such as paging, loading child on-demand, will be processed on server-side. To avoid postback, set the tree grid to load all data on initialization and make the actions process in client-side. To enable this behavior, use the *offline* property of **SfDataManager**.

```csharp

@using Syncfusion.Blazor.TreeGrid;
@using Syncfusion.Blazor.Data;

<SfTreeGrid IdMapping="TaskID" TValue="BusinessObject" ParentIdMapping="ParentItem" HasChildMapping="isParent" AllowPaging="true" TreeColumnIndex="1">
    <SfDataManager Url="https://ej2services.syncfusion.com/production/web-services/api/SelfReferenceData" Offline="true" CrossDomain="true" Adaptor="Syncfusion.Blazor.Adaptors.WebApiAdaptor"></SfDataManager>
    <TreeGridColumns>
        <TreeGridColumn Field="TaskID" HeaderText="Task ID" Width="80" TextAlign="Syncfusion.Blazor.Grids.TextAlign.Right"></TreeGridColumn>
        <TreeGridColumn Field="TaskName" HeaderText="Task Name" Width="160"></TreeGridColumn>
        <TreeGridColumn Field="Duration" HeaderText="Duration" Width="100" TextAlign="Syncfusion.Blazor.Grids.TextAlign.Right"></TreeGridColumn>
        <TreeGridColumn Field="Progress" HeaderText="Progress" Width="100" TextAlign="Syncfusion.Blazor.Grids.TextAlign.Right"></TreeGridColumn>
        <TreeGridColumn Field="Priority" HeaderText="Priority" Width="80"></TreeGridColumn>
    </TreeGridColumns>
</SfTreeGrid>

```

<!-- Custom Adaptor

You can create your own adaptor by extending the built-in adaptors. The following demonstrates custom adaptor approach and how to add a serial number for the records by overriding the built-in response processing using the **processResponse** method of the **ODataAdaptor**.

{% aspTab template="tree-grid/data-binding-mvc/customadaptor", sourceFiles="customadaptor.cs" %}

{% endaspTab %}
-->

### Sending additional parameters to the Rest Web Services

To add a custom parameter to the data request, use the **addParams** method of **Query**. Assign the **Query** object with additional parameters to the tree grid [`Query`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.SfTreeGrid~Query.html) property.

```csharp

@using Syncfusion.Blazor.TreeGrid;
@using Syncfusion.Blazor.Data;

<SfTreeGrid IdMapping="TaskID" TValue="BusinessObject" ParentIdMapping="ParentItem" HasChildMapping="isParent" Query=@TreeGridQuery AllowPaging="true" TreeColumnIndex="1">
    <SfDataManager Url="https://ej2services.syncfusion.com/production/web-services/api/SelfReferenceData" CrossDomain="true" Adaptor="Syncfusion.Blazor.Adaptors.WebApiAdaptor"></SfDataManager>
    <TreeGridColumns>
        <TreeGridColumn Field="TaskID" HeaderText="Task ID" Width="80" TextAlign="Syncfusion.Blazor.Grids.TextAlign.Right"></TreeGridColumn>
        <TreeGridColumn Field="TaskName" HeaderText="Task Name" Width="160"></TreeGridColumn>
        <TreeGridColumn Field="Duration" HeaderText="Duration" Width="100" TextAlign="Syncfusion.Blazor.Grids.TextAlign.Right"></TreeGridColumn>
        <TreeGridColumn Field="Progress" HeaderText="Progress" Width="100" TextAlign="Syncfusion.Blazor.Grids.TextAlign.Right"></TreeGridColumn>
        <TreeGridColumn Field="Priority" HeaderText="Priority" Width="80"></TreeGridColumn>
    </TreeGridColumns>
</SfTreeGrid>
@code{
    public string ParamValue = "true";
    public Query TreeGridQuery { get; set; }

    protected override void  OnInitialized()
    {
        TreeGridQuery = new Query().AddParams("ej2treegrid", ParamValue);
    }
     public class BusinessObject
    {
        public int TaskID { get; set; }
        public string TaskName { get; set; }
        public DateTime? StartDate { get; set; }
        public DateTime? EndDate { get; set; }
        public String Progress { get; set; }
        public String Priority { get; set; }
        public double? Duration { get; set; }
        public int? ParentID { get; set; }
        public bool? isParent { get; set; }
        public bool? Approved { get; set; }
        public int? ParentItem { get; set; }
    }
}

```

<!--Handling HTTP error

During server interaction from the tree grid, some server-side exceptions may occur, and you can acquire those error messages or exception details
in client-side using the [`ActionFailure`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/Syncfusion.EJ2~Syncfusion.EJ2.TreeGrid.TreeGridBuilder~ActionFailure.html) event.

The argument passed to the [`ActionFailure`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/Syncfusion.EJ2~Syncfusion.EJ2.TreeGrid.TreeGridBuilder~ActionFailure.html) event contains the error details returned from the server.

{% aspTab template="tree-grid/data-binding-mvc/http-error", sourceFiles="http-error.cs" %}

{% endaspTab %}

> The [`ActionFailure`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/Syncfusion.EJ2~Syncfusion.EJ2.TreeGrid.TreeGridBuilder~ActionFailure.html) event will be triggered not only for the server errors, but
also when there is an exception while processing the tree grid actions.

-->

## Entity Framework

You need to follow the below steps to consume data from the **Entity Framework** in the Tree Grid component.

### Create DBContext class

The first step is to create a DBContext class called **TasksContext** to connect to a Microsoft SQL Server database.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Threading.Tasks;
using Microsoft.EntityFrameworkCore;

namespace TreeGridWebApiEFSample.Shared.DataAccess
{
    public class TasksContext: DbContext
    {
        public virtual DbSet<Shared.Models.Task> Tasks { get; set; }

        protected override void OnConfiguring(DbContextOptionsBuilder optionsBuilder)
        {
            if (!optionsBuilder.IsConfigured)
            {
                optionsBuilder.UseSqlServer(@"Data Source=(LocalDB)\MSSQLLocalDB;AttachDbFilename=D:\Documentation\TreeGridWebApiEFSample\TreeGridWebApiEFSample\Shared\App_Data\TreeGridDB.mdf;Integrated Security=True;Connect Timeout=30");
            }
        }
    }
}
```

### Create data access layer to perform data operation

Now you need to create a class named **TasksDataAccessLayer**, which act as data access layer for retrieving the records and also insert, update and delete the records from the database table.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Threading.Tasks;
using TreeGridWebApiEFSample.Shared.Models;
using Microsoft.EntityFrameworkCore;

namespace TreeGridWebApiEFSample.Shared.DataAccess
{
    public class TasksDataAccessLayer
    {
        TasksContext treedb = new TasksContext();

        //To Get all Task details
        public IEnumerable<Shared.Models.Task> GetAllRecords()
        {
            try
            {
                return treedb.Tasks.ToList();
            }
            catch
            {
                throw;
            }
        }
    }
}
```

### Creating Web API Controller

 A Web API Controller has to be created which allows Tree Grid directly to consume data from the Entity framework.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Threading.Tasks;
using Microsoft.AspNetCore.Mvc;
using TreeGridWebApiEFSample.Shared.Models;
using TreeGridWebApiEFSample.Shared.DataAccess;
using Microsoft.Extensions.Primitives;
using System.Web;
using Microsoft.AspNetCore.Http;
using Newtonsoft.Json.Linq;


namespace TreeGridWebApiEFSample.Controllers
{
    [Route("api/[controller]")]
    [ApiController]

    public class TreeGridController : ControllerBase
    {
        TasksDataAccessLayer db = new TasksDataAccessLayer();

        // GET: api/<TreeGridController>
        [HttpGet]
        public object Get()
        {
            var queryString = Request.Query;
            IQueryable<TreeGridWebApiEFSample.Shared.Models.Task> data1 = db.GetAllRecords().AsQueryable();
            if (queryString.Keys.Contains("$filter") && !queryString.Keys.Contains("$top"))
            {
                StringValues filter;
                queryString.TryGetValue("$filter", out filter);
                int fltr = Int32.Parse(filter[0].ToString().Split("eq")[1]);
                data1 = data1.Where(f => f.ParentID == fltr).AsQueryable();
                return new { Items = data1, Count = data1.Count() };
            }
            if (queryString.Keys.Contains("$select"))
            {
                data1 = (from ord in data1
                         select new TreeGridWebApiEFSample.Shared.Models.Task
                         {
                             ParentID = ord.ParentID
                         }
                        );
                return data1;
            }

            data1 = data1.Where(p => p.ParentID == null);
            var count = data1.Count();

            if (queryString.Keys.Contains("$inlinecount"))
            {
                StringValues Skip;
                StringValues Take;
                int skip = (queryString.TryGetValue("$skip", out Skip)) ? Convert.ToInt32(Skip[0]) : 0;
                int top = (queryString.TryGetValue("$top", out Take)) ? Convert.ToInt32(Take[0]) : data1.Count();
                return new { Items = data1.Skip(skip).Take(top), Count = count };
            }
            else
            {
                return data1;
            }
        }
    }
}
```

### Configure Tree Grid component using Web API adaptor

Now you can configure the Tree Grid using the **'SfDataManager'** to interact with the created Web API and consume the data appropriately. To interact with web api, you need to use WebApiAdaptor.

```csharp
@using Syncfusion.Blazor.Grids
@using Syncfusion.Blazor.Data
@using Syncfusion.Blazor.Buttons
@using Syncfusion.Blazor.TreeGrid
@using Shared.Models

    <SfTreeGrid TValue="Shared.Models.Task"  @ref="treeGrid" IdMapping="TaskID" AllowPaging="true"
                ParentIdMapping="ParentID" HasChildMapping="IsParent"
                TreeColumnIndex="0">
        <SfDataManager Url="api/TreeGrid" Adaptor="Adaptors.WebApiAdaptor" CrossDomain="true"></SfDataManager>
        <TreeGridColumns>
            <TreeGridColumn Field="TaskID" HeaderText="Task ID" Width="80" IsPrimaryKey="true" Type=ColumnType.Number></TreeGridColumn>
            <TreeGridColumn Field="TaskName" HeaderText="Task Name" Width="160" Type=ColumnType.String></TreeGridColumn>
            <TreeGridColumn Field="Duration" HeaderText="Duration" Width="160" Type=ColumnType.Number></TreeGridColumn>
            <TreeGridColumn Field="Progress" HeaderText="Progress" Width="160" Type=ColumnType.Number></TreeGridColumn>

        </TreeGridColumns>
    </SfTreeGrid>

@code{

    SfTreeGrid<Shared.Models.Task> treeGrid { get; set; }

}
```

To perform Tree Grid CRUD operation using Entity Framework. You can refer [`here`](./editing/#entity-framework).
>You can find the fully working sample [`here`](https://github.com/SyncfusionExamples/Blazor-TreeGrid-With-EntityFramework).