---
title: "Single click editing with Batch mode"
component: "DataGrid"
description: "Learn how to make a cell editable on a single click with batch mode of editing"
---

# Single click editing with Batch mode

You can make a cell editable on a single click with a [`Batch`](https://blazor.syncfusion.com/blazor/documentation/datagrid/editing/#batch) mode of editing in DataGrid, by using the [`EditCell`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.SfGrid%601~EditCell.html) method.

Set the [`Mode`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridSelectionSettings~Mode.html) property of **GridSelectionSettings** component to **Both** and bind the [`CellSelected`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridEvents%601~CellSelected.html) event to DataGrid. In the [`CellSelected`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridEvents%601~CellSelected.html) event handler, call the [`EditCell`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.SfGrid%601~EditCell.html) method based on the clicked cell.

This is demonstrated in the below sample code,

```csharp
@using Syncfusion.Blazor.Grids
@using Newtonsoft.Json

<SfGrid @ref="GridInstance" AllowPaging="true" DataSource="@Orders" Toolbar="@(new List<string>() { "Cancel", "Update" })">
    <GridSelectionSettings Mode="Syncfusion.Blazor.Grids.SelectionMode.Both"></GridSelectionSettings>
    <GridEditSettings AllowEditing="true" Mode="EditMode.Batch"></GridEditSettings>
    <GridEvents CellSelected="CellSelectHandler" TValue="Order"></GridEvents>
    <GridColumns>
        <GridColumn Field=@nameof(Order.OrderID) HeaderText="Order ID" IsPrimaryKey="true" ValidationRules="@(new { required=true})" TextAlign="TextAlign.Right" Width="120"></GridColumn>
        <GridColumn Field=@nameof(Order.CustomerID) HeaderText="Customer Name" ValidationRules="@(new { required=true})" Width="120"></GridColumn>
        <GridColumn Field=@nameof(Order.OrderDate) HeaderText=" Order Date" EditType="EditType.DatePickerEdit" Format="d" TextAlign="TextAlign.Right" Width="130" Type="ColumnType.Date"></GridColumn>
        <GridColumn Field=@nameof(Order.Freight) HeaderText="Freight" Format="C2" TextAlign="TextAlign.Right" EditType="EditType.NumericEdit" Width="120"></GridColumn>
        <GridColumn Field=@nameof(Order.ShipCountry) HeaderText="Ship Country" EditType="EditType.DropDownEdit" Width="150"></GridColumn>
    </GridColumns>
</SfGrid>

@code{
    public static SfGrid<Order> GridInstance { get; set; }
    protected override void OnInitialized()
    {
         Orders = Enumerable.Range(1, 75).Select(x => new Order()
        {
            OrderID = 1000 + x,
            CustomerID = (new string[] { "ALFKI", "ANANTR", "ANTON", "BLONP", "BOLID" })[new Random().Next(5)],
            Freight = 2.1 * x,
            OrderDate = DateTime.Now.AddDays(-x),
            ShipCountry = (new string[] { "USA", "UK", "CHINA", "RUSSIA", "INDIA" })[new Random().Next(5)]
        }).ToList();
    }
    public async void CellSelectHandler(CellSelectEventArgs<Order> args)
    {
        var EditCellIndex = JsonConvert.DeserializeObject<Dictionary<string, object>>(args.CellIndex.ToString());
        var CurrentEditCellIndex = 0;
        var CurrentEditRowIndex = 0;
        foreach (var key in EditCellIndex)
        {
            if (key.Key == "rowIndex")
            {
                CurrentEditRowIndex = Convert.ToInt32(key.Value);
            }
            if (key.Key == "cellIndex")
            {
                CurrentEditCellIndex = Convert.ToInt32(key.Value);
            }
        }
        var fied = await GridInstance.GetColumnFieldNames();
        GridInstance.EditCell(CurrentEditRowIndex, fied[CurrentEditCellIndex]);
    }
    public List<Order> Orders { get; set; }
    public class Order {
        public int? OrderID { get; set; }
        public string CustomerID { get; set; }
        public DateTime? OrderDate { get; set; }
        public double? Freight { get; set; }
        public string ShipCountry { get; set; }
    }
}
```