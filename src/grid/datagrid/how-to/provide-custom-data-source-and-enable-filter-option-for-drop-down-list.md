---
title: "Provide custom data source and enable filter option for DropDownList"
component: "DataGrid"
description: "Learn how to provide custom data source and enable filter option for DropDownList"
---

# Provide custom data source and enable filter option for DropDownList

You can provide custom data source and enable filter option for DropDownList while performing DataGrid editing by using the [`Edit`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridColumn~Edit.html) params property.

While setting new data source for DropDownList using [`Edit`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridColumn~Edit.html) params, you must also specify a new [`Query`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.DropDowns.IDropDownList~Query.html) property for DropDownList.

This is demonstrated in the below sample code,

```csharp
@using Syncfusion.Blazor.Grids
@using Syncfusion.Blazor.DropDowns

<SfGrid DataSource="@Orders" AllowPaging="true" Toolbar="@(new List<string>(){"Add","Edit","Delete","Update","Cancel"})">
    <GridEditSettings AllowAdding="true" AllowEditing="true" AllowDeleting="true"></GridEditSettings>
    <GridColumns>
        <GridColumn Field=@nameof(Order.OrderID) HeaderText="Order ID" IsPrimaryKey="true" TextAlign="TextAlign.Right" Width="120"></GridColumn>
        <GridColumn Field=@nameof(Order.CustomerID) HeaderText="Customer Name" EditType="EditType.DropDownEdit" Edit="@CustomerIDEditParams" Width="120"></GridColumn>
        <GridColumn Field=@nameof(Order.OrderDate) HeaderText=" Order Date" Format="d" Type=ColumnType.Date Width="120"></GridColumn>
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
            Freight = 2.5 * x,
            OrderDate = DateTime.Now.AddDays(-x),
        }).ToList();
        }
        public object CustomerIDEditParams = new
        {
            @@params = new SfDropDownList<string, Country>() { DataSource = @LocalData, AllowFiltering = true, Query = new Query(), Fields = new DropDownListFieldSettings() { Text = "ShipCountry", Value = "ShipCountry" } }
        };
        public class Order
        {
            public int? OrderID { get; set; }
            public string CustomerID { get; set; }
            public DateTime? OrderDate { get; set; }
            public double? Freight { get; set; }
        }
        public class Country
        {
            public string ShipCountry { get; set; }
            public int? CountryId { get; set; }
        }
        public static List<Country> LocalData = new List<Country> {
                new Country() { ShipCountry= "United States", CountryId= 1 },
                new Country() { ShipCountry= "Australia", CountryId= 2 },
                new Country() { ShipCountry= "India", CountryId= 3 }
        };
    }
```
