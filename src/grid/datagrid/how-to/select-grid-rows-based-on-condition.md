---
title: "Select datagrid rows based on certain condition"
component: "DataGrid"
description: "Learn how to select datagrid rows based on certain condition in the Blazor DataGrid component"
---

# Select datagrid rows based on certain condition

You can select specific rows in the datagrid based on some conditions by using the [`SelectRows`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.SfGrid%601~SelectRows.html) method in the [`DataBound`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridEvents%601~DataBound.html) event of the DataGrid component.

This is demonstrated in the below sample code where the index value of datagrid rows with **Freight** column value greater than 10 are stored in the [`RowDataBound`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridEvents%601~RowDataBound.html) event and then selected in the [`DataBound`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridEvents%601~DataBound.html) event,

```csharp
@using Syncfusion.Blazor.Grids

<SfGrid @ref="DefaultGrid" DataSource="@Orders" AllowPaging="true">
    <GridSelectionSettings Type="SelectionType.Multiple"></GridSelectionSettings>
    <GridEvents RowDataBound="OnRowDataBound" DataBound="OnDataBound" TValue="Order"></GridEvents>
    <GridPageSettings PageSize="8"></GridPageSettings>
    <GridColumns>
        <GridColumn Field=@nameof(Order.OrderID) HeaderText="Order ID" TextAlign="TextAlign.Right" Width="120"></GridColumn>
        <GridColumn Field=@nameof(Order.CustomerID) HeaderText="Customer Name" TextAlign="TextAlign.Right" Width="120"></GridColumn>
        <GridColumn Field=@nameof(Order.OrderDate) HeaderText=" Order Date" Format="d" Type=ColumnType.Date TextAlign="TextAlign.Right" Width="120"></GridColumn>
        <GridColumn Field=@nameof(Order.Freight) HeaderText="Freight" Format="C2" TextAlign="TextAlign.Right" Width="120"></GridColumn>
    </GridColumns>
</SfGrid>

@code{
    private SfGrid<Order> DefaultGrid;

    public List<Order> Orders { get; set; }

    public List<int> SelectedNodeIndex = new List<int>();

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
    public class Order
    {
        public int? OrderID { get; set; }
        public string CustomerID { get; set; }
        public DateTime? OrderDate { get; set; }
        public double? Freight { get; set; }
    }

    public void OnDataBound(object args)
    {
        // The filtered index values are selected
        this.DefaultGrid.SelectRows(SelectedNodeIndex);
    }

    public void OnRowDataBound(RowDataBoundEventArgs<Order> args)
    {
        // Freight values greater than 10 are filtered by comparing the primary column values
        if (args.Data.Freight > 10)
        {
            var dataSource = this.DefaultGrid.DataSource;
            var index = 0;
            foreach (var data in dataSource)
            {
                if (data.OrderID == args.Data.OrderID)
                {
                    SelectedNodeIndex.Add(index);
                    break;
                }
                index++;
            }
        }
    }
}
```
