# Render DataGrid inside the Tab with specific height

By default, DataGrid will occupy the entire space of the parent element when DataGrid [`Height`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Grids.SfGrid-1.html#Syncfusion_Blazor_Grids_SfGrid_1_Height) and [`Width`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Grids.SfGrid-1.html#Syncfusion_Blazor_Grids_SfGrid_1_Width) property is defined as 100%. But if you render the similar DataGrid inside the Tab control, it will consider the entire page and render the DataGrid without horizontal scroller.

To overcome this behavior we suggest you to render Tab element inside a specific container and define the [`HeightAdjustMode`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartSeries.html#Syncfusion_Blazor_Charts_ChartSeries_DashArray) of tab as **Fill**. Now the DataGrid inside the Tab element will occupy the specific height.

```csharp
@using Syncfusion.Blazor
@using Syncfusion.Blazor.Navigations
@using Syncfusion.Blazor.Grids

<div style="height:300px">
    <SfTab ID="Ej2Tab" Width="100%">
        <TabItems>
            <TabItem>
                <ChildContent>
                    <TabHeader Text="Grid 1"></TabHeader>
                </ChildContent>
                <ContentTemplate>
                    <SfGrid DataSource="@Orders" Height="100%" Width="100%">
                        <GridColumns>
                            <GridColumn Field=@nameof(Order.OrderID) HeaderText="Order ID" TextAlign="TextAlign.Right" Width="120"></GridColumn>
                            <GridColumn Field=@nameof(Order.CustomerID) HeaderText="Customer Name" Width="150"></GridColumn>
                            <GridColumn Field=@nameof(Order.OrderDate) HeaderText=" Order Date" Format="d" Type="ColumnType.Date" TextAlign="TextAlign.Right" Width="130"></GridColumn>
                            <GridColumn Field=@nameof(Order.Freight) HeaderText="Freight" Format="C2" TextAlign="TextAlign.Right" Width="120"></GridColumn>
                        </GridColumns>
                    </SfGrid>
                </ContentTemplate>
            </TabItem>
            <TabItem>
                <ChildContent>
                    <TabHeader Text="Grid 2"></TabHeader>
                </ChildContent>
                <ContentTemplate>
                    <SfGrid DataSource="@Employees" Height="100%" Width="100%">
                        <GridColumns>
                            <GridColumn Field=@nameof(EmployeeData.EmployeeID) HeaderText="ID" Visible="false" TextAlign="TextAlign.Right" Width="120"></GridColumn>
                            <GridColumn Field=@nameof(EmployeeData.FirstName) HeaderText="First Name" Width="150"></GridColumn>
                            <GridColumn Field=@nameof(EmployeeData.LastName) HeaderText="last Name" Width="150"></GridColumn>
                            <GridColumn Field=@nameof(EmployeeData.HireDate) HeaderText="Hire Date" Format="d" Type="ColumnType.Date" TextAlign="TextAlign.Right" Width="130"></GridColumn>
                            <GridColumn Field=@nameof(EmployeeData.Role) HeaderText="Position" Width="120"></GridColumn>
                        </GridColumns>
                    </SfGrid>
                </ContentTemplate>
            </TabItem>
        </TabItems>
    </SfTab>
</div>

@code {

    public List<Order> Orders { get; set; }
    public List<EmployeeData> Employees { get; set; }
    protected override void OnInitialized()
    {
        Orders = Enumerable.Range(1, 75).Select(x => new Order()
        {
            OrderID = 1000 + x,
            CustomerID = (new string[] { "ALFKI", "ANANTR", "ANTON", "BLONP", "BOLID" })[new Random().Next(5)],
            Freight = 2.1 * x,
            OrderDate = DateTime.Now.AddDays(-x),
        }).ToList();
        Employees = Enumerable.Range(1, 75).Select(x => new EmployeeData()
        {
            EmployeeID = x,
            FirstName = (new string[] { "Nancy", "Andrew", "Janet", "Margaret", "Steven" })[new Random().Next(5)],
            LastName = (new string[] { "Davolio", "Fuller", "Leveringg", "peacock", "Smith" })[new Random().Next(5)],
            Role = (new string[] { "Sales Representative", "Sales Representative", "Sales Manager", "HR Manager", "Inside Sales Coordinator" })[new Random().Next(5)],
            HireDate = DateTime.Now.AddDays(-x),
        }).ToList();
    }
    public class Order
    {
        public int? OrderID { get; set; }
        public string CustomerID { get; set; }
        public DateTime? OrderDate { get; set; }
        public double? Freight { get; set; }
    }
    public class EmployeeData
    {
        public int? EmployeeID { get; set; }
        public string FirstName { get; set; }
        public string LastName { get; set; }
        public string Role { get; set; }
        public DateTime? HireDate { get; set; }

    }
}
```
