---
title: "Search"
component: "DataGrid"
description: "Learn how to search DataGrid content, change search operators, perform searches using external buttons, and search in particular fields."
---

# Search

You can search records in a DataGrid, by using the **Search** method with search key as a parameter. This also provides an option to integrate search text box in datagrid's toolbar by adding **Search** item to the [`Toolbar`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.SfGrid~Toolbar.html).

```csharp
@using Syncfusion.Blazor.Grids

@{
    var Tool = (new List<string>() { "Search" });
}
<SfGrid DataSource="@Orders" Toolbar=@Tool>
    <GridColumns>
        <GridColumn Field=@nameof(Order.OrderID) HeaderText="Order ID" TextAlign="TextAlign.Right" Width="120"></GridColumn>
        <GridColumn Field=@nameof(Order.CustomerID) HeaderText="Customer Name" Width="150"></GridColumn>
        <GridColumn Field=@nameof(Order.OrderDate) HeaderText=" Order Date" Format="d" Type="ColumnType.Date" TextAlign="TextAlign.Right" Width="130"></GridColumn>
        <GridColumn Field=@nameof(Order.Freight) HeaderText="Freight" Format="C2" TextAlign="TextAlign.Right" Width="120"></GridColumn>
    </GridColumns>
</SfGrid>

@code{
    public List<Order> Orders { get; set; }

    protected override void OnInitialized()
    {
        Orders = Enumerable.Range(1, 75).Select(x => new Order()
        {
            OrderID = 1000 + x,
            CustomerID = (new string[] { "ALFKI", "ANANTR", "ANTON", "BLONP", "BOLID" })[new Random().Next(5)],
            Freight = 2.1 * x,
            OrderDate = DateTime.Now.AddDays(-x),
        }).ToList();
    }

    public class Order {
        public int? OrderID { get; set; }
        public string CustomerID { get; set; }
        public DateTime? OrderDate { get; set; }
        public double? Freight { get; set; }
    }
}
```

The following GIF image represents a DataGrid Searching.

![Searching](images/searching.gif)

## Initial search

To apply search at initial rendering, set the **Fields**, **Operator**, **Key**, and **IgnoreCase** using [`GridSearchSettings`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.SfGrid~SearchSettings.html) component.

```csharp
@using Syncfusion.Blazor.Grids

@{
    var InitSearch = (new string[] { "CustomerID" });
    var Tool = (new List<string>() { "Search" });
}
<SfGrid DataSource="@Orders" Toolbar=@Tool>
    <GridSearchSettings Fields=@InitSearch Operator=Syncfusion.Blazor.Operator.Contains Key="anton" IgnoreCase="true"></GridSearchSettings>
            <GridColumns>
                <GridColumn Field=@nameof(Order.OrderID) HeaderText="Order ID" TextAlign="TextAlign.Right" Width="120"></GridColumn>
                <GridColumn Field=@nameof(Order.CustomerID) HeaderText="Customer Name" Width="150"></GridColumn>
                <GridColumn Field=@nameof(Order.OrderDate) HeaderText=" Order Date" Format="d" Type="ColumnType.Date" TextAlign="TextAlign.Right" Width="130"></GridColumn>
                <GridColumn Field=@nameof(Order.Freight) HeaderText="Freight" Format="C2" TextAlign="TextAlign.Right" Width="120"></GridColumn>
            </GridColumns>
</SfGrid>

@code{
    public List<Order> Orders { get; set; }

    protected override void OnInitialized()
    {
        Orders = Enumerable.Range(1, 75).Select(x => new Order()
        {
            OrderID = 1000 + x,
            CustomerID = (new string[] { "ALFKI", "ANANTR", "ANTON", "BLONP", "BOLID" })[new Random().Next(5)],
            Freight = 2.1 * x,
            OrderDate = DateTime.Now.AddDays(-x),
        }).ToList();
    }

    public class Order {
        public int? OrderID { get; set; }
        public string CustomerID { get; set; }
        public DateTime? OrderDate { get; set; }
        public double? Freight { get; set; }
    }
}
```

The following screenshot represents a DataGrid with initial searching.

![Initial Search](./images/grid-initialsearch.png)

> By default, datagrid searches all the bound column values. To customize this behavior define the [`Fields`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/Syncfusion~Syncfusion.Grids.GridSearchSettings~Fields.html) property of **GridSearchSettings** component.

## Search operators

The search operator can be defined in the [`Operator`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridSearchSettings~Operator.html) property of **GridSearchSettings** to configure specific searching.

The following operators are supported in searching:

Operator |Description
-----|-----
StartsWith |Checks whether a value begins with the specified value.
EndsWith |Checks whether a value ends with the specified value.
Contains |Checks whether a value contains the specified value.
Equal |Checks whether a value is equal to the specified value.
NotEqual |Checks for values not equal to the specified value.

> By default, the [`Operator`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridSearchSettings~Operator.html) value is **Contains**.

## Search by external button

To search datagrid records from an external button, invoke the **Search** method.

```csharp
@using Syncfusion.Blazor.Buttons
@using Syncfusion.Blazor.Grids

@{
    var Tool = (new List<string>() { "Search" });
}
<SfButton Content="Search" OnClick="SearchBtnHandler"></SfButton>
<SfGrid @ref="DefaultGrid" DataSource="@Orders" AllowSorting="true" Toolbar=@Tool>
    <GridColumns>
        <GridColumn Field=@nameof(Order.OrderID) HeaderText="Order ID" TextAlign="TextAlign.Right" Width="120"></GridColumn>
        <GridColumn Field=@nameof(Order.CustomerID) HeaderText="Customer Name" Width="120"></GridColumn>
        <GridColumn Field=@nameof(Order.OrderDate) HeaderText=" Order Date" Format="d" TextAlign="TextAlign.Right" Width="130" Type="ColumnType.Date"></GridColumn>
        <GridColumn Field=@nameof(Order.Freight) HeaderText="Freight" Format="C2" TextAlign="TextAlign.Right" Width="120"></GridColumn>
    </GridColumns>
</SfGrid>

@code{
    private SfGrid<Order> DefaultGrid;

    public List<Order> Orders { get; set; }

    protected override void OnInitialized()
    {
        Orders = Enumerable.Range(1, 75).Select(x => new Order()
        {
            OrderID = 1000 + x,
            CustomerID = (new string[] { "ALFKI", "ANANTR", "ANTON", "BLONP", "BOLID" })[new Random().Next(5)],
            Freight = 2.1 * x,
            OrderDate = DateTime.Now.AddDays(-x),
        }).ToList();
    }

    public class Order {
        public int? OrderID { get; set; }
        public string CustomerID { get; set; }
        public DateTime? OrderDate { get; set; }
        public double? Freight { get; set; }
    }

    public void SearchBtnHandler()
    {
        this.DefaultGrid.Search("1001");
    }
}
```

## Search specific columns

By default, datagrid searches all visible columns. You can search specific columns by defining the specific column's field names in the [`Fields`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridSearchSettings~Fields.html) property of **GridSearchSettings** component.

```csharp
@using Syncfusion.Blazor.Grids

@{
    var Tool = (new List<string>() { "Search" });
    var SpecificCols = (new string[] { "CustomerID","ShipName"});
}
<SfGrid DataSource="@Orders" Toolbar=@Tool>
    <GridSearchSettings Fields=@SpecificCols></GridSearchSettings>
            <GridColumns>
                <GridColumn Field=@nameof(Order.OrderID) HeaderText="Order ID" TextAlign="TextAlign.Right" Width="120"></GridColumn>
                <GridColumn Field=@nameof(Order.CustomerID) HeaderText="Customer Name" Width="150"></GridColumn>
                <GridColumn Field=@nameof(Order.OrderDate) HeaderText=" Order Date" Format="d" Type="ColumnType.Date" TextAlign="TextAlign.Right" Width="130"></GridColumn>
                <GridColumn Field=@nameof(Order.Freight) HeaderText="Freight" Format="C2" TextAlign="TextAlign.Right" Width="120"></GridColumn>
            </GridColumns>
</SfGrid>

@code{
    public List<Order> Orders { get; set; }

    protected override void OnInitialized()
    {
        Orders = Enumerable.Range(1, 75).Select(x => new Order()
        {
            OrderID = 1000 + x,
            CustomerID = (new string[] { "ALFKI", "ANANTR", "ANTON", "BLONP", "BOLID" })[new Random().Next(5)],
            Freight = 2.1 * x,
            OrderDate = DateTime.Now.AddDays(-x),
        }).ToList();
    }

    public class Order {
        public int? OrderID { get; set; }
        public string CustomerID { get; set; }
        public DateTime? OrderDate { get; set; }
        public double? Freight { get; set; }
    }
}
```
