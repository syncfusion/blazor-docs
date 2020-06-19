---
title: " Chart Working With Data | ASP.NET Core Blazor "

component: "Chart"

description: "Chart can be rendered by using different types of data source. They are called local data, remote data and empty points. "
---

<!-- markdownlint-disable MD036 -->

# Woking with Data

The Chart uses [`SfDataManager`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Data.EjsDataManager.html), which supports both RESTful JSON data services binding and IEnumerable binding. The [`DataSource`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartSeries~DataSource.html) value can be assigned either with the property values from [`SfDataManager`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Data.EjsDataManager.html) or list of business objects.
It supports the following kinds of data binding method:
* List binding
* Remote data

## List binding

To bind list to the chart, you can assign a IEnumerable object to the [`DataSource`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartSeries~DataSource.html) property. The list data source can also be provided as an instance of [`SfDataManager`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Data.EjsDataManager.html) or by using [`SfDataManager`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Data.EjsDataManager.html) component. Now map the fields in list to
[`XName`](https://help.syncfusion.com/cr/cref_files/aspnetmvc-js2/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartSeries~XName.html) and [`YName`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartSeries~YName.html)
properties.

{% aspTab template="chart/axis/working-data/local-data", sourceFiles="local-data.razor" %}

{% endaspTab %}

![Local Data](images/working-data/local-data.png)

## Remote Data

To bind remote data to chart component, assign service data as an instance of [`SfDataManager`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Data.EjsDataManager.html) to the DataSource property or by using EjsDataManager component. To interact with remote data source, provide the endpoint Url.

{% aspTab template="chart/axis/working-data/remote-data", sourceFiles="remote-data.razor" %}

{% endaspTab %}

### Binding with OData services

[OData](http://www.odata.org/documentation/odata-version-3-0/) is a standardized protocol for creating and consuming data. You can retrieve data from OData service using the [`SfDataManager`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Data.EjsDataManager.html). Refer to the following code example for remote Data binding using **OData** service.

### Binding with OData v4 services

The ODataV4 is an improved version of OData protocols, and the [`SfDataManager`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Data.EjsDataManager.html) can also retrieve and consume OData v4 services. For more details on OData v4 services, refer to the [OData documentation](http://docs.oasis-open.org/odata/odata/v4.0/errata03/os/complete/part1-protocol/odata-v4.0-errata03-os-part1-protocol-complete.html#_Toc453752197). To bind OData v4 service, use the **ODataV4Adaptor**.

![Remote Data](images/working-data/remote-data.png)

### Web API

You can use **WebApiAdaptor** to bind chart with Web API created using [OData](http://www.odata.org/documentation/odata-version-3-0/) endpoint.

```csharp
@using Syncfusion.Blazor.Data
@using Syncfusion.Blazor.Charts

<SfChart>
    <SfDataManager Url="https://ej2services.syncfusion.com/production/web-services/api/Orders" Adaptor="Adaptors.WebApiAdaptor"></SfDataManager>

    <ChartPrimaryXAxis Title="Orders" ValueType="Syncfusion.Blazor.Charts.ValueType.Category"
                       RangePadding="ChartRangePadding.Additional"></ChartPrimaryXAxis>

    <ChartSeriesCollection>
        <ChartSeries XName="OrderID" YName="Freight" Type="ChartSeriesType.Column"></ChartSeries>
    </ChartSeriesCollection>
</SfChart>
```

![Web API](images/working-data/webapi.png)

### Enable EjsDataManager after initial rendering

It is possible to render the datasource in Chart after initial rendering. This can be achieved by conditionally enabling the [`SfDataManager`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Data.EjsDataManager.html) component after Chart rendering.

The following sample code demonstrates enabling data manager condition in the Chart on button click,

```csharp
@using Syncfusion.Blazor.Buttons
@using Syncfusion.Blazor.Data
@using Syncfusion.Blazor.Charts

<SfChart>
    @if (IsInitialRender)
    {
        <SfDataManager Url="https://ej2services.syncfusion.com/production/web-services/api/Orders" Adaptor="Adaptors.WebApiAdaptor">
        </SfDataManager>
    }

    <ChartPrimaryXAxis Title="Orders" ValueType="Syncfusion.Blazor.Charts.ValueType.Category"
                       RangePadding="ChartRangePadding.Additional"></ChartPrimaryXAxis>

    <ChartSeriesCollection>
        <ChartSeries XName="OrderID" YName="Freight" Type="ChartSeriesType.Column"></ChartSeries>
    </ChartSeriesCollection>
</SfChart>

<SfButton OnClick="Enable" CssClass="e-primary" IsPrimary="true" Content="Enable data manager"></SfButton>

@code{
    public bool IsInitialRender = false;

    public void Enable()
    {
        // Enabling condition to render the data manager
        this.IsInitialRender = true;
    }
}
```

### Sending additional parameters to the server

To add a custom parameter to the data request. Assign the Query object with additional parameters to the Chart's [`Query`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartSeries~Query.html) property.

The following sample code demonstrates sending parameters using the Query property in the series,

```csharp
@using Syncfusion.Blazor.Data
@using Syncfusion.Blazor.Charts

<SfChart>
    <SfDataManager Url="https://mvc.syncfusion.com/Services/Northwnd.svc/Tasks/">
    </SfDataManager>

    <ChartPrimaryXAxis Title="Assignee" ValueType="Syncfusion.Blazor.Charts.ValueType.Category"
                       RangePadding="ChartRangePadding.Additional"></ChartPrimaryXAxis>

    <ChartSeriesCollection>
        <ChartSeries Query="new ej.data.Query().take(10).where('Estimate', 'lessThan', 3, false)" XName="Assignee" YName="Estimate" Type="ChartSeriesType.Column"></ChartSeries>
    </ChartSeriesCollection>
</SfChart>
```

### Change Query parameter value dynamically

It is possible to dynamically modify Chart's [`Query`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartSeries~Query.html) property value.

The following sample code demonstrates achieving this,

```csharp
@using Syncfusion.Blazor.Buttons
@using Syncfusion.Blazor.Data
@using Syncfusion.Blazor.Charts

<SfButton Content="Modify query data" OnClick="BtnClick"></SfButton>
<SfChart>
    <SfDataManager Url="https://mvc.syncfusion.com/Services/Northwnd.svc/Tasks/">
    </SfDataManager>

    <ChartPrimaryXAxis Title="Assignee" ValueType="Syncfusion.Blazor.Charts.ValueType.Category"
                       RangePadding="ChartRangePadding.Additional"></ChartPrimaryXAxis>

    <ChartSeriesCollection>
        <ChartSeries Query="@QueryData" XName="Assignee" YName="Estimate" Type="ChartSeriesType.Column"></ChartSeries>
    </ChartSeriesCollection>
</SfChart>

@code{
    private string QueryData = "new ej.data.Query().take(10).where('Estimate', 'lessThan', 3, false)";
    private string UpdatedQueryData = "new ej.data.Query().take(5).where('Estimate', 'lessThan', 3, false)";

    public void BtnClick(UIMouseEventArgs args)
    {
        QueryData = UpdatedQueryData;
    }
}
```

Before modify:

![Before Modify query dynamically](images/working-data/query.png)

After modified:

![After Modify query dynamically](images/working-data/query-update.png)

## Empty points

The Data points that contains `NaN` value are considered as empty points. By using [`EmptyPointSettings`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartSeries~EmptyPointSettings.html) property in series, you can customize the empty point. Default `Mode` of the empty point is `Gap`.

{% aspTab template="chart/axis/working-data/empty-points", sourceFiles="empty-points.razor" %}

{% endaspTab %}

**Customizing empty point**

Specific color for empty point can be set by `Fill` property in [`EmptyPointSettings`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartSeries~EmptyPointSettings.html). Border for a empty point can be set by
`Border` property.

{% aspTab template="chart/axis/working-data/custom-emptypoint", sourceFiles="custom-emptypoint.razor" %}

{% endaspTab %}

![Empty points](images/working-data/custom-emptypoint.png)

## Entity Framework

Entity Framework acts as a modern object-database mapper for .NET. This section explains how to consume data from the **Microsoft SQL Server** database and bind it to the chart component.

### Create DBContext class

The first step is to create a DBContext class called **OrderContext** for establishing connection to a Microsoft SQL Server database.

```csharp
    using System;
    using System.Collections.Generic;
    using System.Linq;
    using System.Threading.Tasks;
    using Microsoft.EntityFrameworkCore;
    using System.ComponentModel.DataAnnotations;
    using EFChart.Data;

    namespace EFChart.Data
    {
        public class OrderContext : DbContext
        {
            public virtual DbSet<Order> Orders { get; set; }

            protected override void OnConfiguring(DbContextOptionsBuilder optionsBuilder)
            {
                if (!optionsBuilder.IsConfigured)
                {
                    // Configures the context to connect to a Microsoft SQL Serve database
                    optionsBuilder.UseSqlServer(@"Data Source=(LocalDB)\MSSQLLocalDB;AttachDbFilename='D:\blazor\EFTreeMap\App_Data\NORTHWND.MDF';Integrated Security=True;Connect Timeout=30");
                }
            }
        }

        public class Order
        {
            [Key]
            public int? OrderID { get; set; }
            [Required]
            public string CustomerID { get; set; }
            [Required]
            public int EmployeeID { get; set; }
        }
    }

```

### Create data access layer to perform data operation

Now need to create a class called **OrderDataAccessLayer**, which acts as a data access layer to retrieve the records from the database table.

```csharp
    using Microsoft.EntityFrameworkCore;
    using System;
    using System.Collections.Generic;
    using System.Linq;
    using System.Threading.Tasks;
    using static BlazorApp1.Data.OrderContext;
    using EFChart.Data;

    namespace EFChart.Data
    {
        public class OrderDataAccessLayer
        {
            OrderContext db = new OrderContext();

            //To Get all Orders details
            public DbSet<Order> GetAllOrders()
            {
                try
                {
                    return db.Orders;
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

A Web API Controller must be created which allows the chart to directly consume data from the Entity framework.

```csharp
    using System;
    using System.Collections;
    using System.Collections.Generic;
    using System.Linq;
    using System.Threading.Tasks;
    using Microsoft.AspNetCore.Http;
    using Microsoft.AspNetCore.Mvc;
    using Microsoft.Extensions.Primitives;
    using static BlazorApp1.Data.OrderContext;
    using EFChart.Data;

    namespace EFChart.Controller
    {
        [Route("api/[controller]")]
        [ApiController]
        public class DefaultController : ControllerBase
        {
            OrderDataAccessLayer db = new OrderDataAccessLayer();
            [HttpGet]
            public object Get()
            {
                IQueryable<Order> data = db.GetAllOrders().AsQueryable();
                var count = data.Count();
                var queryString = Request.Query;
                if (queryString.Keys.Contains("$inlinecount"))
                {
                    StringValues Skip;
                    StringValues Take;
                    int skip = (queryString.TryGetValue("$skip", out Skip)) ? Convert.ToInt32(Skip[0]) : 0;
                    int top = (queryString.TryGetValue("$top", out Take)) ? Convert.ToInt32(Take[0]) : data.Count();
                    return new { Items = data.Skip(skip).Take(top), Count = count };
                }
                else
                {
                    return data;
                }
            }
        }
    }

```

### Add Web API Controller services in Startup.cs

Open the **Startup.cs** file and add services and endpoints required for Web API Controller as follows.

```csharp
using EFChart.Data;
using Newtonsoft.Json.Serialization;

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
            services.AddSingleton<OrderDataAccessLayer>();

            // Adds services for controllers to the specified Microsoft.Extensions.DependencyInjection.IServiceCollection.
            services.AddControllers().AddNewtonsoftJson(options =>
            {
                options.SerializerSettings.ContractResolver = new DefaultContractResolver();
            });
        }

        public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
        {
            ....
            ....
            app.UseEndpoints(endpoints =>
            {
                // Adds endpoints for controller actions to the Microsoft.AspNetCore.Routing.IEndpointRouteBuilder
                endpoints.MapDefaultControllerRoute();
                .....
                .....
            });
        }
    }
}
```

### Configure chart component

Configure the chart to bind data using either [`DataSource`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.SfChart~DataSource.html) property or [`SfDataManager`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.DataManager.html).

For instance, to bind data directly from the data access layer class **OrderDataAccessLayer**, assign the [`DataSource`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.SfChart~DataSource.html) property to be **OrderData.GetAllOrders()**.

```csharp

    @using EFChart.Data;
    @inject OrderDataAccessLayer OrderData;

    @using Syncfusion.Blazor.Charts

    <SfChart DataSource="@OrderData.GetAllOrders()">
      <ChartPrimaryXAxis ValueType="Syncfusion.Blazor.Charts.ValueType.Category">
      </ChartPrimaryXAxis>
      <ChartSeriesCollection>
        <ChartSeries XName="CustomerID" YName="OrderID" Type="ChartSeriesType.Column">
        </ChartSeries>
      </ChartSeriesCollection>
    </SfChart>
    @code{

    }
```

On the other hand, to configure the chart using Web API, provide the appropriate endpoint Url within [`SfDataManager`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.DataManager.html) along with [`Adaptor`](https://blazor.syncfusion.com/documentation/data/adaptors). Here, need to use [`WebApiAdaptor`](https://blazor.syncfusion.com/documentation/data/adaptors/?no-cache=1#web-api-adaptor) in-order to interact with the Web API to consume data from the entity framework appropriately.

```csharp
@using Syncfusion.Blazor.Charts
@using Syncfusion.Blazor.Data

<div class="control-section">
    <div>
        <SfChart>
          <SfDataManager Url="api/Default" Adaptor="Syncfusion.Blazor.Adaptors.WebApiAdaptor">
          </SfDataManager>
          <ChartPrimaryXAxis ValueType="Syncfusion.Blazor.Charts.ValueType.Category">
          </ChartPrimaryXAxis>
          <ChartSeriesCollection>
             <ChartSeries XName="CustomerID" YName="OrderID" Type="ChartSeriesType.Column">
             </ChartSeries>
          </ChartSeriesCollection>
        </SfChart>
    </div>
</div>
@code{

}
```

## See Also

* [Data label](./data-labels)
* [Tooltip](./tool-tip)
* [Marker](./data-markers)