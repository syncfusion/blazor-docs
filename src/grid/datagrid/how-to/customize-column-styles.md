---
title: "Customize Column Styles"
component: "DataGrid"
description: "Learn how to Customize Column Styles in Blazor DataGrid Component."
---

# Customize Column Styles

You can customise the appearance of the header and content of a particular column using the [`CustomAttributes`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridColumn~CustomAttributes.html) property.

To customize the datagrid column, follow the given steps:

**Step 1**:

Create a CSS class with custom style to override the default style for rowcell and headercell.

```css
.e-attr{
        background: #5DADE2;
        font-family: "Bell MT";
        color: red;
        font-size: 5px;
    }
```

**Step 2**:

Add the custom CSS class to the specified column by using the [`CustomAttributes`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridColumn~CustomAttributes.html) property.

```csharp
@using Syncfusion.Blazor
@using Syncfusion.Blazor.Grids

<SfGrid DataSource="@Orders" AllowPaging="true" Height="200" @ref="Grid">
    <GridColumns>
        <GridColumn Field=@nameof(Order.OrderID) HeaderText="Order ID" TextAlign="TextAlign.Right" Width="120"></GridColumn>
        <GridColumn Field=@nameof(Order.CustomerID) HeaderText="Customer Name" Width="150" ></GridColumn>
        <GridColumn Field=@nameof(Order.OrderDate) HeaderText=" Order Date" Format="d" Type="ColumnType.Date" CustomAttributes="@(new { @class="e-attr"})"  TextAlign="TextAlign.Right" Width="130"></GridColumn>
        <GridColumn Field=@nameof(Order.Freight) HeaderText="Freight" Format="C2" TextAlign="TextAlign.Right" Width="120"></GridColumn>
    </GridColumns>
</SfGrid>
<style>
    .e-attr{
        background: #5DADE2;
        font-family: "Bell MT";
        color: red;
        font-size: 5px;
    }
</style>

@code{
    SfGrid<Order> Grid;
    public List<Order> Orders { get; set; }
    protected override void OnInitialized()
    {
        Orders = Enumerable.Range(1, 10).Select(x => new Order()
        {
            OrderID = 1000 + x,
            CustomerID = (new string[] { "ALFKI", "ANANTR", "ANTON", "BLONP", "BOLID" })[new Random().Next(5)],
            Freight = 2.1 * x,
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
}
```

Output be like the below.

![`Final output`](../images/changecolumnstyle.PNG)