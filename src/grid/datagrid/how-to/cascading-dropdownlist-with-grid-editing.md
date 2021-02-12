---
component: "DataGrid"
---

# Cascading DropDownList with DataGrid editing

You can achieve the Cascading DropDownList with datagrid editing by using the [`EditTemplate`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Grids.GridColumn.html) property of the [`GridColumn`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Grids.GridColumn.html) component.

This is demonstrated in the below sample code where cascading dropdownlist is rendered for the **ShipCountry** and **ShipState** column when perform editing in datagrid.

```csharp
@page "/"

@using Syncfusion.Blazor.Grids
@using Syncfusion.Blazor.DropDowns

<SfGrid AllowPaging="true" DataSource="@GridData" ShowColumnChooser="true" Toolbar="@(new List<string>() { "Add","Edit","Delete","Update","Cancel" })">
    <GridEvents OnActionBegin="OnActionBegin" TValue="Orders"></GridEvents>
    <GridEditSettings AllowEditing="true" AllowDeleting="true" AllowAdding="true" Mode="@EditMode.Normal"></GridEditSettings>
    <GridColumns>
        <GridColumn Field=@nameof(Orders.OrderID) HeaderText="Order ID" IsPrimaryKey="true" TextAlign="@TextAlign.Center" Width="140"></GridColumn>
        <GridColumn Field=@nameof(Orders.Freight) HeaderText="Freight" EditType="EditType.NumericEdit" Format="C2" Width="140" TextAlign="@TextAlign.Right"></GridColumn>
        <GridColumn Field=@nameof(Orders.OrderDate) HeaderText="Order Date" EditType="EditType.DatePickerEdit" Format="d" Type="ColumnType.Date" Width="160"></GridColumn>
        <GridColumn Field=@nameof(Orders.ShipCountry) HeaderText="Ship Country" EditType="EditType.DropDownEdit" Width="150">
            <EditTemplate>
                <SfDropDownList ID="ShipCountry" Placeholder="Select a Country" TItem="string" TValue="string" @bind-Value="@((context as Orders).ShipCountry)" DataSource="@Countries">
                    <DropDownListEvents TValue="string" ValueChange="ValueChange"></DropDownListEvents>
                    <DropDownListFieldSettings Text="ShipCountry" Value="ShipCountry"></DropDownListFieldSettings>
                </SfDropDownList>
            </EditTemplate>
        </GridColumn>
        <GridColumn Field=@nameof(Orders.ShipState) HeaderText=" ShipState" EditType="EditType.DropDownEdit" Width="150">
            <EditTemplate>
                <SfDropDownList ID="ShipState" Placeholder="Select a State" TItem="string" Enabled="@Enabled" TValue="string" @bind-Value="@((context as Orders).ShipState)" DataSource="@States">
                    <DropDownListFieldSettings Text="ShipState" Value="ShipState"></DropDownListFieldSettings>
                </SfDropDownList>
            </EditTemplate>
        </GridColumn>
    </GridColumns>
</SfGrid>

@code{
    public List<Orders> GridData { get; set; } = new List<Orders>();
    public List<string> Countries = new List<string>() { "United States", "Australia" };
    public List<string> States = new List<string>() { "New York", "Virginia", "Washington", "Queensland", "Tasmania", "Victoria" };
    public bool Enabled = false;
    protected override void OnInitialized()
    {
        if (GridData.Count() == 0)
        {
            int code = 10000;
            for (int i = 1; i < 10; i++)
            {
                GridData.Add(new Orders(code + 1, "ALFKI", i + 0, 2.3 * i, new DateTime(1991, 05, 15), "United States", "New York"));
                GridData.Add(new Orders(code + 2, "ANATR", i + 2, 3.3 * i, new DateTime(1990, 04, 04), "Australia", "Queensland"));
                GridData.Add(new Orders(code + 3, "ANTON", i + 1, 4.3 * i, new DateTime(1957, 11, 30), "United States", "Virginia"));
                GridData.Add(new Orders(code + 4, "BLONP", i + 3, 5.3 * i, new DateTime(1930, 10, 22), "United States", "Washington"));
                GridData.Add(new Orders(code + 5, "BOLID", i + 4, 6.3 * i, new DateTime(1953, 02, 18), "Australia", "Victoria"));
                code += 5;
            }
        }
    }

    public class Orders
    {
        public Orders()
        {

        }
        public Orders(long OrderId, string CustomerId, int EmployeeId, double Freight, DateTime OrderDate, string ShipCountry, string ShipState)
        {
            this.OrderID = OrderId;
            this.CustomerID = CustomerId;
            this.EmployeeID = EmployeeId;
            this.Freight = Freight;
            this.OrderDate = OrderDate;
            this.ShipCountry = ShipCountry;
            this.ShipState = ShipState;
        }
        public long OrderID { get; set; }
        public string CustomerID { get; set; }
        public int EmployeeID { get; set; }
        public double Freight { get; set; }
        public DateTime OrderDate { get; set; }
        public string ShipCountry { get; set; }
        public string ShipState { get; set; }
    }
    public void ValueChange(@Syncfusion.Blazor.DropDowns.ChangeEventArgs<string> args)
    {
        if (args.Value == "United States")
        {
            States = new List<string>() { "New York", "Virginia", "Washington" };
        }
        else if (args.Value == "Australia")
        {
            States = new List<string>() { "Queensland", "Tasmania", "Victoria" };
        }
        Enabled = true;
    }
    public void OnActionBegin(ActionEventArgs<Orders> args)
    {
        if (args.RequestType == Syncfusion.Blazor.Grids.Action.BeginEdit)
        {
            Enabled = false;
        }
    }
}
```
