---
title: "Editing"
component: "DataGrid"
description: "Learn how to perform CRUD operations in various edit modes, use different cell editors in the Blazor DataGrid component."
---

# Editing

The DataGrid component has options to dynamically insert, delete and update records.
Editing feature requires a primary key column for CRUD operations.
To define the primary key, set [`Columns.IsPrimaryKey`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridColumn~IsPrimaryKey.html) to **true** in particular column.

You can start the edit action either by double clicking the particular row or by selecting the required row and click on **Edit** button in the toolbar. Similarly, you can add a new record to datagrid either by clicking on **Add** button in the toolbar or on an external button which is bound to invoke the [`AddRecord`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.SfGrid~AddRecord.html) method of the datagrid, **Save** and **Cancel** while in edit mode is possible using respective toolbar icon in datagrid.

Deletion of the record is possible by selecting the required row and click on **Delete** button in the toolbar.

```csharp
@using Syncfusion.Blazor.Grids

<SfGrid DataSource="@Orders" AllowPaging="true" Toolbar="@(new List<string>() { "Add", "Edit", "Delete", "Cancel", "Update" })" Height ="315">
   <GridEditSettings AllowAdding="true" AllowEditing="true" AllowDeleting="true"></GridEditSettings>
    <GridColumns>
        <GridColumn Field=@nameof(Order.OrderID) HeaderText="Order ID" IsPrimaryKey="true" TextAlign="TextAlign.Right" Width="120"></GridColumn>
        <GridColumn Field=@nameof(Order.CustomerID) HeaderText="Customer Name" Width="120"></GridColumn>
        <GridColumn Field=@nameof(Order.OrderDate) HeaderText=" Order Date" EditType="EditType.DatePickerEdit" Format="d" TextAlign="TextAlign.Right" Width="130" Type="ColumnType.Date"></GridColumn>
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

The following screenshot represents Editing with Default Mode.
![Edit Action](./images/edit-action.png)

> * If [`Columns.IsIdentity`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridColumn~IsIdentity.html) is enabled, then it will be considered as a read-only column when editing and adding a record.
> * You can disable editing for a particular column, by specifying
[`Columns.AllowEditing`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridColumn~AllowEditing.html) to **false**.

## Toolbar with edit option

The datagrid toolbar has the  following built-in items to execute editing actions.

* Add - Adds a new record.
* Edit - Edits the selected record.
* Update - Updates the edited record.
* Delete - Deletes the selected record.
* Cancel - Cancels the edit state.

You can define this by using the [`Toolbar`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.SfGrid~Toolbar.html) property.

```csharp
@using Syncfusion.Blazor.Grids

<SfGrid DataSource="@Orders" AllowPaging="true" Toolbar="@(new List<string>() { "Add", "Edit", "Delete", "Cancel", "Update" })">
   <GridEditSettings AllowAdding="true" AllowEditing="true" AllowDeleting="true"></GridEditSettings>
    <GridColumns>
        <GridColumn Field=@nameof(Order.OrderID) HeaderText="Order ID" IsPrimaryKey="true" TextAlign="TextAlign.Right" Width="120"></GridColumn>
        <GridColumn Field=@nameof(Order.CustomerID) HeaderText="Customer Name" Width="120" ></GridColumn>
        <GridColumn Field=@nameof(Order.OrderDate) HeaderText=" Order Date" EditType="EditType.DatePickerEdit" Format="d" TextAlign="TextAlign.Right" Width="130" Type="ColumnType.Date"></GridColumn>
        <GridColumn Field=@nameof(Order.Freight) HeaderText="Freight" Format="C2" TextAlign="TextAlign.Right" Width="120" ></GridColumn>
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

The following screenshot represents Toolbar with Edit option.
![Edit Action](./images/edit-action.png)

## Edit Modes

DataGrid supports the following types of edit modes, they are:

* Normal
* Dialog
* Batch

### Normal

In Normal edit mode, when you start editing the currently selected record is changed to edit state.
You can change the cell values and save edited data to the data source.
To enable Normal edit, set the [`EditSettings.Mode`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridEditSettings~Mode.html) as **Normal**.

```csharp
@using Syncfusion.Blazor.Grids

<SfGrid DataSource="@Orders" AllowPaging="true" Toolbar="@(new List<string>() { "Add", "Edit", "Delete", "Cancel", "Update" })" Height="315">
    <GridEditSettings AllowAdding="true" AllowEditing="true" AllowDeleting="true" Mode="EditMode.Normal"></GridEditSettings>
    <GridColumns>
        <GridColumn Field=@nameof(Order.OrderID) HeaderText="Order ID" IsPrimaryKey="true" ValidationRules="@(new { required=true})" TextAlign="TextAlign.Right" Width="120"></GridColumn>
        <GridColumn Field=@nameof(Order.CustomerID) HeaderText="Customer Name" ValidationRules="@(new { required=true})" Width="120"></GridColumn>
        <GridColumn Field=@nameof(Order.OrderDate) HeaderText=" Order Date" EditType="EditType.DatePickerEdit" Format="d" TextAlign="TextAlign.Right" Width="130" Type="ColumnType.Date"></GridColumn>
        <GridColumn Field=@nameof(Order.Freight) HeaderText="Freight" Format="C2" TextAlign="TextAlign.Right" EditType="EditType.NumericEdit" Width="120"></GridColumn>
        <GridColumn Field=@nameof(Order.ShipCountry) HeaderText="Ship Country"  EditType="EditType.DropDownEdit" Width="150"></GridColumn>
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
            ShipCountry = (new string[] { "USA", "UK", "CHINA", "RUSSIA", "INDIA" })[new Random().Next(5)]
        }).ToList();
    }

    public class Order {
        public int? OrderID { get; set; }
        public string CustomerID { get; set; }
        public DateTime? OrderDate { get; set; }
        public double? Freight { get; set; }
        public string ShipCountry { get; set; }
    }
}
```

The following screenshot represents Editing in Normal Mode.
![Normal Editing](./images/normal-editing.png)

> Normal edit mode is default mode of editing.

### Dialog

In dialog edit mode, when you start editing the currently selected row data will be shown on a dialog.
You can change the cell values and save edited data to the data source.
To enable Dialog edit, set the [`EditSettings.Mode`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridEditSettings~Mode.html) as **Dialog**.

```csharp
@using Syncfusion.Blazor.Grids

<SfGrid DataSource="@Orders" AllowPaging="true" Toolbar="@(new List<string>() { "Add", "Edit", "Delete", "Update", "Cancel" })" Height="315">
    <GridEditSettings AllowAdding="true" AllowEditing="true" AllowDeleting="true" Mode="EditMode.Dialog"></GridEditSettings>
    <GridColumns>
        <GridColumn Field=@nameof(Order.OrderID) HeaderText="Order ID" IsPrimaryKey="true" ValidationRules="@(new { required=true})" TextAlign="TextAlign.Right" Width="120"></GridColumn>
        <GridColumn Field=@nameof(Order.CustomerID) HeaderText="Customer Name" ValidationRules="@(new { required=true})" Width="120"></GridColumn>
        <GridColumn Field=@nameof(Order.OrderDate) HeaderText=" Order Date" EditType="EditType.DatePickerEdit" Format="d" TextAlign="TextAlign.Right" Width="130" Type="ColumnType.Date"></GridColumn>
        <GridColumn Field=@nameof(Order.Freight) HeaderText="Freight" Format="C2" TextAlign="TextAlign.Right" EditType="EditType.NumericEdit" Width="120"></GridColumn>
        <GridColumn Field=@nameof(Order.ShipCountry) HeaderText="Ship Country"  EditType="EditType.DropDownEdit" Width="150"></GridColumn>
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
            ShipCountry = (new string[] { "USA", "UK", "CHINA", "RUSSIA", "INDIA" })[new Random().Next(5)]
        }).ToList();
    }

    public class Order {
        public int? OrderID { get; set; }
        public string CustomerID { get; set; }
        public DateTime? OrderDate { get; set; }
        public double? Freight { get; set; }
        public string ShipCountry { get; set; }
    }
}

```

The following screenshot represents Editing in Dialog Mode.
![Dialog Editing](./images/dialog-editing.png)

### Batch

In batch edit mode, when you double-click on the datagrid cell, then the target cell changed to edit state.
You can bulk save (added, changed and deleted data in the single request) to data source by click on the toolbar's **Update** button or by externally calling the **BatchSave** method.
To enable Batch edit, set the [`EditSettings.Mode`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridEditSettings~Mode.html) as **Batch**.

```csharp
@using Syncfusion.Blazor.Grids

<SfGrid DataSource="@Orders" AllowPaging="true" Toolbar="@(new List<string>() { "Add", "Delete", "Update", "Cancel" })" Height="315">
    <GridEditSettings AllowAdding="true" AllowEditing="true" AllowDeleting="true" Mode="EditMode.Batch"></GridEditSettings>
    <GridColumns>
        <GridColumn Field=@nameof(Order.OrderID) HeaderText="Order ID" IsPrimaryKey="true" ValidationRules="@(new { required=true})" TextAlign="TextAlign.Right" Width="120"></GridColumn>
        <GridColumn Field=@nameof(Order.CustomerID) HeaderText="Customer Name" ValidationRules="@(new { required=true})" Width="120" ></GridColumn>
        <GridColumn Field=@nameof(Order.OrderDate) HeaderText=" Order Date" EditType="EditType.DatePickerEdit" Format="d" TextAlign="TextAlign.Right" Width="130" Type="ColumnType.Date"></GridColumn>
        <GridColumn Field=@nameof(Order.Freight) HeaderText="Freight" Format="C2" TextAlign="TextAlign.Right" EditType="EditType.NumericEdit" Width="120"></GridColumn>
        <GridColumn Field=@nameof(Order.ShipCountry) HeaderText="Ship Country"  EditType="EditType.DropDownEdit" Width="150"></GridColumn>
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
            ShipCountry = (new string[] { "USA", "UK", "CHINA", "RUSSIA", "INDIA" })[new Random().Next(5)]
        }).ToList();
    }

    public class Order {
        public int? OrderID { get; set; }
        public string CustomerID { get; set; }
        public DateTime? OrderDate { get; set; }
        public double? Freight { get; set; }
        public string ShipCountry { get; set; }
    }
}
```

The following screenshot represents Editing in Batch mode.
![Batch Editing](./images/batch-editing.png)

## Cell edit type and its params

The [`EditType`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridColumn~EditType.html) property of the [`GridColumn`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridColumn.html) component is used for defining the editor component for any particular column. You can set the [`EditType`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridColumn~EditType.html) based on data type of the column. The available edit types are,

* [`NumericTextBox`](https://blazor.syncfusion.com/blazor/documentation/numerictextbox/getting-started) component for integers, double, and decimal data types.

* [`TextBox`](https://blazor.syncfusion.com/blazor/documentation/textbox/getting-started/) component for string data type.

* [`DropDownList`](https://blazor.syncfusion.com/blazor/documentation/dropdownlist/getting-started/) component to show all unique values related to that field.

* [`CheckBox`](https://blazor.syncfusion.com/blazor/documentation/check-box/getting-started/) component for boolean data type.

* [`DatePicker`](https://blazor.syncfusion.com/blazor/documentation/datepicker/getting-started/) component for date data type.

* [`DateTimePicker`](https://blazor.syncfusion.com/blazor/documentation/datetimepicker/getting-started/) component for date time data type.

Also, you can customize the behavior of the editor component through the [`Edit`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridColumn~Edit.html) params of the [`GridColumn`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridColumn.html) component.

The following table describes editor component and their example edit params of the column.

| Component | Example |
|----------------|---------|
| [`NumericTextBox`](https://blazor.syncfusion.com/blazor/documentation/numerictextbox/getting-started) | params: { decimals: 2, value: 5 }|
| [`DropDownList`](https://blazor.syncfusion.com/blazor/documentation/dropdownlist/getting-started/) | params: { value: ‘Germany’ }|
| [`CheckBox`](https://blazor.syncfusion.com/blazor/documentation/check-box/getting-started/) | params: { checked: true} |
| [`DatePicker`](https://blazor.syncfusion.com/blazor/documentation/datepicker/getting-started/) | params: { format:‘dd.MM.yyyy’ } |
| [`DateTimePicker`](https://blazor.syncfusion.com/blazor/documentation/datetimepicker/) | params: { value: new Date() } |

The following sample code demonstrates different edit types and edit params set for the DataGrid columns,

```csharp
@using Syncfusion.Blazor.Buttons
@using Syncfusion.Blazor.DropDowns
@using Syncfusion.Blazor.Grids
@using Syncfusion.Blazor.Inputs

<SfGrid DataSource="@OrderData" Toolbar=@ToolbarItems>
    <GridEditSettings AllowEditing="true" AllowAdding="true" AllowDeleting="true"></GridEditSettings>
    <GridColumns>
        <GridColumn Field=@nameof(Order.OrderID) HeaderText="Order ID" IsPrimaryKey="true" TextAlign="TextAlign.Center" Width="120"></GridColumn>
        <GridColumn Field=@nameof(Order.CustomerID) HeaderText="Customer ID" TextAlign="TextAlign.Center" Width="130"></GridColumn>
        <GridColumn Field=@nameof(Order.Freight) HeaderText="Freight" Format="C2" EditType="EditType.NumericEdit" Edit="@FreightEditParams" TextAlign="TextAlign.Center" Width="130"></GridColumn>
        <GridColumn Field=@nameof(Order.ShipName) HeaderText="Ship Name" TextAlign="TextAlign.Center" EditType="EditType.DropDownEdit" Edit="@ShipNameEditParams" Width="120"></GridColumn>
        <GridColumn Field=@nameof(Order.Verified) HeaderText="Verified" EditType="EditType.BooleanEdit" TextAlign="TextAlign.Center" DisplayAsCheckBox="true" Width="120" Edit="@VerifiedEditParams"></GridColumn>
    </GridColumns>
</SfGrid>

@code{
    public string[] ToolbarItems = new string[] { "Add", "Edit", "Delete", "Update", "Cancel" };

    public object FreightEditParams = new
    {
        @@params = new SfNumericTextBox<int>() { Decimals = 3, Value = 4 }
    };

    public object VerifiedEditParams = new
    {
        @@params = new SfCheckBox() { Checked = true }
    };

    public object ShipNameEditParams = new
    {
        @@params = new SfDropDownList<string, Order>() { Value = "Hanari Carnes" }
    };

    List<Order> OrderData = new List<Order>
    {
        new Order() { OrderID = 10248, CustomerID = "VINET", Freight = 32.38, ShipName = "Vins et alcools Chevalier", Verified = true },
        new Order() { OrderID = 10249, CustomerID = "TOMSP", Freight = 11.61, ShipName = "Toms Spezialitäten", Verified = false },
        new Order() { OrderID = 10250, CustomerID = "HANAR", Freight = 65.83, ShipName = "Hanari Carnes", Verified = true },
        new Order() { OrderID = 10251, CustomerID = "VICTE", Freight = 41.34, ShipName = "Victuailles en stock", Verified = false },
        new Order() { OrderID = 10252, CustomerID = "SUPRD", Freight = 51.3, ShipName = "Suprêmes délices", Verified = false },
        new Order() { OrderID = 10253, CustomerID = "HANAR", Freight = 58.17, ShipName = "Hanari Carnes", Verified = false },
        new Order() { OrderID = 10254, CustomerID = "CHOPS", Freight = 22.98, ShipName = "Chop-suey Chinese", Verified = true },
        new Order() { OrderID = 10255, CustomerID = "RICSU", Freight = 148.33, ShipName = "Richter Supermarket", Verified = true },
        new Order() { OrderID = 10256, CustomerID = "WELLI", Freight = 13.97, ShipName = "Wellington Importadora", Verified = false },
        new Order() { OrderID = 10257, CustomerID = "HILAA", Freight = 81.91, ShipName = "HILARION-Abastos", Verified = true }
    };

    public class Order
    {
        public int OrderID { get; set; }
        public string CustomerID { get; set; }
        public double Freight { get; set; }
        public string ShipName { get; set; }
        public bool Verified { get; set; }
    }
}
```

## Cell Edit Template

> Before adding edit template to the datagrid, we strongly recommend you to go through the [`template`](./templates/#templates) section topic to configure the template.

The cell edit template is used to add a custom component for a particular column. You can use the **EditTemplate** of the [`GridColumn`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridColumn.html) component to add the custom component. You can access the parameters passed to the templates using implicit parameter named **context**.

```csharp
@using Syncfusion.Blazor.DropDowns
@using Syncfusion.Blazor.Grids

<SfGrid  AllowPaging="true" DataSource="@Orders" Toolbar="@(new List<string>() { "Add", "Edit", "Delete", "Cancel", "Update" })">
    <GridEditSettings AllowEditing="true" AllowDeleting="true" AllowAdding="true" Mode="@EditMode.Normal"></GridEditSettings>
    <GridColumns>
        <GridColumn Field=@nameof(Order.OrderID) HeaderText="Order ID" IsPrimaryKey="true" TextAlign="@TextAlign.Center" Width="140"></GridColumn>
        <GridColumn Field=@nameof(Order.CustomerID) HeaderText="Customer Name" Width="150">
            <EditTemplate>
                <SfAutoComplete ID="CustomerID" Value="@((context as Order).CustomerID)" DataSource="@Orders">
                    <AutoCompleteFieldSettings Value="CustomerID"></AutoCompleteFieldSettings>
                </SfAutoComplete>
            </EditTemplate>
        </GridColumn>
        <GridColumn Field=@nameof(Order.Freight) HeaderText="Freight" EditType="EditType.NumericEdit" Format="C2" Width="140" TextAlign="@TextAlign.Right"></GridColumn>
        <GridColumn Field=@nameof(Order.OrderDate) HeaderText="Order Date" EditType="EditType.DatePickerEdit" Format="d" Type="ColumnType.Date" Width="160"></GridColumn>
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

    public class Order
    {
        public int? OrderID { get; set; }
        public string CustomerID { get; set; }
        public DateTime? OrderDate { get; set; }
        public double? Freight { get; set; }
    }
}
```

In the following image, **Autocomplete** component is rendered with **EditTemplate** in Customer ID column
![Celledit Template](./images/celledit-template.png)

## Command column

The command column provides an option to add CRUD action buttons in a column. This can be defined by using the `GridCommandColumns` component which needs to be wrapped inside the [`GridColumn`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridColumn.html) component.

The available built-in command buttons are:

| Command Button | Actions |
|----------------|---------|
| Edit | Edit the current row.|
| Delete | Delete the current row.|
| Save | Update the edited row.|
| Cancel | Cancel the edited state. |

```csharp
@using Syncfusion.Blazor.Grids

<SfGrid DataSource="@Orders" AllowPaging="true" Height="315">
    <GridEditSettings AllowAdding="true" AllowEditing="true" AllowDeleting="true"></GridEditSettings>
    <GridColumns>
        <GridColumn Field=@nameof(Order.OrderID) HeaderText="Order ID" IsPrimaryKey="true" TextAlign="TextAlign.Right" Width="120"></GridColumn>
        <GridColumn Field=@nameof(Order.CustomerID) HeaderText="Customer Name" Width="120"></GridColumn>
        <GridColumn Field=@nameof(Order.OrderDate) HeaderText=" Order Date" EditType="EditType.DatePickerEdit" Format="d" TextAlign="TextAlign.Right" Width="130"></GridColumn>
        <GridColumn Field=@nameof(Order.Freight) HeaderText="Freight" Format="C2" TextAlign="TextAlign.Right" Width="120"></GridColumn>
        <GridColumn HeaderText="Manage Records" Width="150">
            <GridCommandColumns>
                <GridCommandColumn Type="CommandButtonType.Edit" ButtonOption="@(new CommandButtonOptions() { IconCss = "e-icons e-edit", CssClass = "e-flat" })"></GridCommandColumn>
                <GridCommandColumn Type="CommandButtonType.Delete" ButtonOption="@(new CommandButtonOptions() { IconCss = "e-icons e-delete", CssClass = "e-flat" })"></GridCommandColumn>
                <GridCommandColumn Type="CommandButtonType.Save" ButtonOption="@(new CommandButtonOptions() { IconCss = "e-icons e-update", CssClass = "e-flat" })"></GridCommandColumn>
                <GridCommandColumn Type="CommandButtonType.Cancel" ButtonOption="@(new CommandButtonOptions() { IconCss = "e-icons e-cancel-icon", CssClass = "e-flat" })"></GridCommandColumn>
            </GridCommandColumns>
         </GridColumn>
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
            ShipCountry = (new string[] { "USA", "UK", "CHINA", "RUSSIA", "INDIA" })[new Random().Next(5)]
        }).ToList();
    }

    public class Order
    {
        public int? OrderID { get; set; }
        public string CustomerID { get; set; }
        public DateTime? OrderDate { get; set; }
        public double? Freight { get; set; }
        public string ShipCountry { get; set; }
    }
}
```

The following screenshot represents the command column.
![Command Column](./images/command-column.png)

### Custom command

The custom command buttons can be added in a column by using the [`Commands`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridColumn~Commands.html) property of the [`GridColumn`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridColumn.html) component and the action for the custom buttons can be defined in the [`CommandClicked`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridEvents%601~CommandClicked.html) event.

The following sample code demonstrates adding custom command in the **Manage Records** column and the `CommandClicked` event which triggers when the command is clicked,

```csharp
@using Syncfusion.Blazor.Grids

<SfGrid DataSource="@Orders" AllowPaging="true" Height="315">
    <GridEvents CommandClicked="OnCommandClicked" TValue="Order"></GridEvents>
    <GridEditSettings AllowAdding="true" AllowEditing="true" AllowDeleting="true"></GridEditSettings>
    <GridColumns>
        <GridColumn Field=@nameof(Order.OrderID) HeaderText="Order ID" IsPrimaryKey="true" TextAlign="TextAlign.Right" Width="120"></GridColumn>
        <GridColumn Field=@nameof(Order.CustomerID) HeaderText="Customer Name" Width="120"></GridColumn>
        <GridColumn Field=@nameof(Order.OrderDate) HeaderText=" Order Date" EditType="EditType.DatePickerEdit" Format="d" TextAlign="TextAlign.Right" Width="130"></GridColumn>
        <GridColumn Field=@nameof(Order.Freight) HeaderText="Freight" Format="C2" TextAlign="TextAlign.Right" Width="120"></GridColumn>
        <GridColumn HeaderText="Manage Records" Width="150">
            <GridCommandColumns>
                <GridCommandColumn ButtonOption="@(new CommandButtonOptions() { Content = "Details", CssClass = "e-flat" })"></GridCommandColumn>
            </GridCommandColumns>
        </GridColumn>
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
            ShipCountry = (new string[] { "USA", "UK", "CHINA", "RUSSIA", "INDIA" })[new Random().Next(5)]
        }).ToList();
    }

    public class Order
    {
        public int? OrderID { get; set; }
        public string CustomerID { get; set; }
        public DateTime? OrderDate { get; set; }
        public double? Freight { get; set; }
        public string ShipCountry { get; set; }
    }

    public void OnCommandClicked(CommandClickEventArgs<Order> args)
    {
        // Perform required operations here
    }
}
```

The following image represents the custom command added in the **Manage Records** column of the DataGrid component,
![Custom Command](./images/custom-command.png)

## Column validation

Column validation allows you to validate the edited or added row data and it display errors for invalid fields before saving data.
DataGrid uses **Form Validator** library for column validation.
You can set validation rules by defining the [`Columns.ValidationRules`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridColumn~ValidationRules.html).

```csharp
@using Syncfusion.Blazor.Grids

<SfGrid DataSource="@Orders" Height="315" AllowPaging="true" Toolbar="@(new List<string>() { "Add", "Edit", "Delete", "Update", "Cancel" })">
    <GridEditSettings AllowAdding="true" AllowEditing="true" AllowDeleting="true"></GridEditSettings>
    <GridColumns>
        <GridColumn Field=@nameof(Order.OrderID) HeaderText="Order ID" IsPrimaryKey="true" ValidationRules="@(new { required= true })" TextAlign="TextAlign.Right" Width="120"></GridColumn>
        <GridColumn Field=@nameof(Order.CustomerID) HeaderText="Customer Name" Width="120" ValidationRules="@(new { required= true, minLength= 3 })"></GridColumn>
        <GridColumn Field=@nameof(Order.OrderDate) HeaderText=" Order Date" EditType="EditType.DatePickerEdit" Format="d" TextAlign="TextAlign.Right" Width="130" Type="ColumnType.Date"></GridColumn>
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

The following screenshot represents the Column Validation in Normal Editing.
![Validation Rules](./images/validation-rules.png)

## Entity Framework

This section uses and follows the code explained in the [`Entity Framework data binding`](./data-binding/#entity-framework) section hence we recommend you to refer Entity framework data binding section before continue this section.

### Handle CRUD in data access layer class

Now add methods **AddOrder**, **UpdateOrder**, **DeleteOrder** in the **"OrderDataAccessLayer.cs"** to handle the insert, update and remove operations respectively.**CRUD** record details are bound to the **Order** parameter. Please refer the following code.

```csharp
using Microsoft.EntityFrameworkCore;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Threading.Tasks;
using EFGrid.Shared.Models;

namespace EFGrid.Shared.DataAccess
{
    public class OrderDataAccessLayer
    {
        OrderContext db = new OrderContext();
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
        public void AddOrder(Order Order)
        {
            try
            {
                db.Orders.Add(Order);
                db.SaveChanges();
            }
            catch
            {
                throw;
            }
        }
        public void UpdateOrder(Order Order)
        {
            try
            {
                db.Entry(Order).State = EntityState.Modified;
                db.SaveChanges();
            }
            catch
            {
                throw;
            }
        }
        public void DeleteOrder(int id)
        {
            try
            {
                Order ord = db.Orders.Find(id);
                db.Orders.Remove(ord);
                db.SaveChanges();
            }
            catch
            {
                throw;
            }
        }
    }
}
```

### Enable CRUD in Web API

Now you have to create a new **Post**, **Put**, **Delete** method in the Web API controller which will perform the CRUD operations and returns the appropriate resultant data. The **'SfDataManager'** will make requests to this action based on route name.

```csharp
using System;
using System.Collections;
using System.Collections.Generic;
using System.Linq;
using System.Threading.Tasks;
using Microsoft.AspNetCore.Http;
using Microsoft.AspNetCore.Mvc;
using Microsoft.Extensions.Primitives;
using EFGrid.Shared.DataAccess;
using EFGrid.Shared.Models;

namespace WebApplication1.Server.Controllers
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
        [HttpGet("{id}", Name = "Get")]
        public string Get(int id)
        {
            return "value";
        }
        [HttpPost]
        public void Post([FromBody]Order Order)
        {

            Random rand = new Random();
            db.AddOrder(Order);

        }
        [HttpPut]
        public object Put([FromBody]Order Order)
        {
            db.UpdateOrder(Order);
            return Order;
        }
        [HttpDelete("{id}")]
        public void Delete(int id)
        {
            db.DeleteOrder(id);
        }
    }
}
```

### Configure the datagrid to perform CRUD operations

```csharp
@using Syncfusion.Blazor
@using Syncfusion.Blazor.Grids

<SfGrid TValue="Order" AllowPaging="true" Toolbar="@(new List<string>() { "Add", "Edit", "Delete", "Cancel", "Update" })">
    <SfDataManager Url="api/Default" Adaptor="Adaptors.WebApiAdaptor"></SfDataManager>
    <GridEditSettings AllowAdding="true" AllowDeleting="true" AllowEditing="true" Mode="EditMode.Normal"></GridEditSettings>
        <GridColumns>
            <GridColumn Field="OrderID" HeaderText="Order ID" IsPrimaryKey="true" IsIdentity="true" TextAlign="@Syncfusion.Blazor.Grids.TextAlign.Right" Width="90"></GridColumn>
            <GridColumn Field="CustomerID" HeaderText="Customer ID" Width="90"></GridColumn>
            <GridColumn Field="EmployeeID" HeaderText="Employee ID" Width="90"></GridColumn>
        </GridColumns>
</SfGrid>

@code{
    public class Order {
        public int? OrderID { get; set; }
        public string  CustomerID { get; set; }
        public DateTime? OrderDate { get; set; }
        public double? Freight { get; set; }
    }
}
```

>You can find the fully working sample [`here`](https://github.com/ej2gridsamples/Blazor/blob/master/EntityFramework.zip).

## Performing CRUD operations programmatically

You can perform CRUD operations like **Add** , **Update** , **Delete** by using the [`AddRecord`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.SfGrid%601~AddRecord.html) , [`UpdateRow`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.SfGrid%601~UpdateRow.html) , [`DeleteRow`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.SfGrid%601~DeleteRow.html)  methods.
* **AddRecord** - Add a new record into the datagrid
* **UpdateRow** - Update a existing record in a datagrid.
* **DeleteRow** - Delete a selected row in the datagrid

```csharp
@using Syncfusion.Blazor.Grids
@using Syncfusion.Blazor.Buttons

<SfButton @onclick="Add"> Add </SfButton>
<SfButton @onclick="Update"> Update - 1001 </SfButton>
<SfButton @onclick="Delete"> Delete the selected row </SfButton>

<SfGrid DataSource="@Orders" AllowPaging="true" @ref="Grid" Height="315">
    <GridEditSettings AllowAdding="true" AllowEditing="true" AllowDeleting="true"></GridEditSettings>
    <GridColumns>
        <GridColumn Field=@nameof(Order.OrderID) HeaderText="Order ID" IsPrimaryKey="true" ValidationRules="@(new { required = true })" TextAlign="TextAlign.Right" Width="120"></GridColumn>
        <GridColumn Field=@nameof(Order.CustomerID) HeaderText="Customer Name" ValidationRules="@(new { required = true })" Width="120"></GridColumn>
        <GridColumn Field=@nameof(Order.Freight) HeaderText="Freight" Format="C2" TextAlign="TextAlign.Right" EditType="EditType.NumericEdit" Width="120"></GridColumn>
        <GridColumn Field=@nameof(Order.ShipCountry) HeaderText="Ship Country" EditType="EditType.DropDownEdit" Width="150"></GridColumn>
    </GridColumns>
</SfGrid>

@code{
    public List<Order> Orders { get; set; }
    SfGrid<Order> Grid;

    public void Add()
    {
        Order adddata = new Order() { OrderID = 1000, CustomerID = "MJDGX", ShipCountry = "LONDON",
        Freight = 3.01 };
        this.Grid.AddRecord(adddata);
    }

    public void Update()
    {
        Order data = new Order () { OrderID = 1001, CustomerID = "ABCDE", ShipCountry = "LONDON", Freight = 2.91 };
        this.Grid.UpdateRow(1, data);
    }

    public void Delete()
    {
        this.Grid.DeleteRecord();
    }

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

    public class Order
    {
        public int? OrderID { get; set; }
        public string CustomerID { get; set; }
        public DateTime? OrderDate { get; set; }
        public double? Freight { get; set; }
        public string ShipCountry { get; set; }
    }
}
```

The following GIF represents the datagrid with Add, Update, Delete items,
![CRUD operations](./images/Editing.gif)

## Custom external form editing

You can perform the edit operation of datagrid in a Custom external form. The edit operation can be done by [`RowSelected`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridEvents%601~RowSelected.html) property.

```csharp

@using Syncfusion.Blazor.Grids
@using Syncfusion.Blazor.Buttons
@using Syncfusion.Blazor.DropDowns
@using Syncfusion.Blazor.Inputs

<div class="row">
     <div class="col-md-6">
         <div>
             <div class="form-row">
                 <div class="form-group col-md-12">
                     <label for="orderedit">OrderID</label>
                     <input class="form-control" @bind="@(SelectedProduct.OrderID)" type="number" disabled />
                 </div>
             </div>
             <div class="form-row">
                 <div class="form-group col-md-12">
                     <label for="customeredit">CustomerID</label>
                     <SfTextBox ID="CustomerID" @bind-Value="@(SelectedProduct.CustomerID)"></SfTextBox>
                 </div>
             </div>
             <div class="form-row">
                 <div class="form-group col-md-12">
                     <label for="freightedit">Frieght</label>
                     <SfNumericTextBox ID="Freight" TValue="double?" @bind-Value="@SelectedProduct.Freight"></SfNumericTextBox>
                 </div>
             </div>
             <div class="form-row">
                 <div class="form-group col-md-12">
                     <label for="countryedit">ShipCountry</label>
                     <SfDropDownList ID="ShipCountry" @bind-Value="@SelectedProduct.ShipCountry" TItem="Country" TValue="string" DataSource="@Dropdown">
                         <DropDownListFieldSettings Value="ShipCountry" Text="ShipCountry"></DropDownListFieldSettings>
                     </SfDropDownList>
                 </div>
             </div>
         </div>
     <SfButton @onclick="Save">Save</SfButton>
     </div>
     <div class="col-md-6">
         <SfGrid DataSource="@Orders" AllowPaging="true" @ref="Grid" Height=315>
             <GridEditSettings AllowEditing="true"></GridEditSettings>
             <GridEvents RowSelected="RowSelectHandler" TValue="Order"></GridEvents>
             <GridColumns>
                 <GridColumn Field=@nameof(Order.OrderID) HeaderText="OrderID" IsPrimaryKey="true" TextAlign="TextAlign.Right" Width="120"></GridColumn>
                 <GridColumn Field=@nameof(Order.CustomerID) HeaderText="CustomerID" TextAlign="TextAlign.Right" Width="120"></GridColumn>
                 <GridColumn Field=@nameof(Order.Freight) HeaderText="Freight" TextAlign="TextAlign.Right" Format="C2" Width="120"></GridColumn>
                 <GridColumn Field=@nameof(Order.ShipCountry) HeaderText="ShipCountry" TextAlign="TextAlign.Right" Width="120"></GridColumn>
             </GridColumns>
         </SfGrid>
     </div>
 </div>

@code{
    public List<Order> Orders { get; set; }
    SfGrid<Order> Grid;
    public Order SelectedProduct = new Order();
    public class Country
    {
        public string ShipCountry { get; set; }
    }
    List<Country> Dropdown = new List<Country>
    {
          new Country() { ShipCountry= "USA" },
          new Country() { ShipCountry= "UK" },
          new Country() { ShipCountry= "RUSSIA" },
          new Country() { ShipCountry= "INDIA" },
          new Country() { ShipCountry= "CHINA" },
    };

    void Save()
    {
        this.Grid.UpdateRow(1, SelectedProduct);
    }

    protected override void OnInitialized()
    {
        Orders = Enumerable.Range(1, 75).Select(x => new Order()
        {
            OrderID = 1000 + x,
            CustomerID = (new string[] { "ALFKI", "ANANTR", "ANTON", "BLONP", "BOLID" })[new Random().Next(5)],
            Freight = 2.1 * x,
            ShipCountry = (new string[] { "USA", "UK", "CHINA", "RUSSIA", "INDIA" })[new Random().Next(5)]
        }).ToList();
    }
    public class Order
    {
        public int? OrderID { get; set; }
        public string CustomerID { get; set; }
        public double? Freight { get; set; }
        public string ShipCountry { get; set; }
    }

    public void RowSelectHandler(RowSelectEventArgs<Order> args)
    {
        SelectedProduct = args.Data ;
    }

}

```

The following GIF represent the datagrid with Custom External form editing,
![Custom external form](./images/Customform.gif)

## Dialog template

> Before adding dialog template to the datagrid, we strongly recommend you to go through the [`Template`](./templates/#templates) section topic to configure the template.

The dialog template editing provides an option to customize the default behavior of dialog editing. Using the dialog template, you can render your own editors by defining the [`GridEditSettings`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridEditSettings.html) component's [`Mode`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridEditSettings~Mode.html) property as **Dialog** and wrapping the HTML elements inside the [`Template`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridEditSettings~Template.html) property of [`GridEditSettings`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridEditSettings.html).

In some cases, you would need to add new field editors in the dialog which are not present in the column model. In that case, the dialog template will help you to customize the default edit dialog.

The following sample code demonstrates DataGrid enabled with dialog template editing,

```csharp
@using Syncfusion.Blazor.Grids
@using Syncfusion.Blazor.Calendars
@using Syncfusion.Blazor.DropDowns
@using Syncfusion.Blazor.Inputs

<SfGrid  DataSource="@GridData" Toolbar="@(new string[] {"Add", "Edit" ,"Delete","Update","Cancel" })">
    <GridEditSettings AllowAdding="true" AllowEditing="true" AllowDeleting="true" Mode="@EditMode.Dialog">
        <Template>
            @{
                var Order = (context as OrdersDetails);
                <div>
                    <div class="form-row">
                        <div class="form-group col-md-6">
                            <label class="e-float-text e-label-top">Order ID</label>
                            <SfTextBox ID="OrderID" Value="@(Order.OrderID.ToString())" Enabled="false"></SfTextBox>
                        </div>
                        <div class="form-group col-md-6">
                            <label class="e-float-text e-label-top">Customer Name</label>
                            <SfAutoComplete ID="customerID" FloatLabelType="FloatLabelType.Auto" Value="@(Order.CustomerID)" TValue="string" DataSource="@GridData">
                                <AutoCompleteFieldSettings Value="CustomerID"></AutoCompleteFieldSettings>
                            </SfAutoComplete>
                        </div>
                    </div>
                    <div class="form-row">
                        <div class="form-group col-md-6">
                            <label class="e-float-text e-label-top">Freight</label>
                            <SfNumericTextBox ID="Freight" Value="@(Order.Freight)" TValue="double?"></SfNumericTextBox>
                        </div>
                        <div class="form-group col-md-6">
                            <label class="e-float-text e-label-top">Order Date</label>
                            <SfDatePicker ID="OrderDate" Value="@(Order.OrderDate)"></SfDatePicker>
                        </div>
                    </div>
                    <div class="form-row">
                        <div class="form-group col-md-6">
                            <label class="e-float-text e-label-top">Ship Country</label>
                            <SfDropDownList ID="ShipCountry" Value="@(Order.ShipCountry)" TItem="OrdersDetails" TValue="string" DataSource="@GridData">
                                <DropDownListFieldSettings Value="ShipCountry" Text="ShipCountry"></DropDownListFieldSettings>
                            </SfDropDownList>
                        </div>
                        <div class="form-group col-md-6">
                            <label class="e-float-text e-label-top">Ship City</label>
                            <SfDropDownList ID="ShipCity" Value="@(Order.ShipCity)" TItem="OrdersDetails" TValue="string" DataSource="@GridData">
                                <DropDownListFieldSettings Value="ShipCity" Text="ShipCity"></DropDownListFieldSettings>
                            </SfDropDownList>
                        </div>
                    </div>
                    <div class="form-row">
                        <div class="form-group col-md-12">
                            <label class="e-float-text e-label-top">Ship Address</label>
                            <SfTextBox ID="ShipAddress" Value="@(Order.ShipAddress)"></SfTextBox>
                        </div>
                    </div>
                </div>
            }
        </Template>
    </GridEditSettings>
    <GridColumns>
        <GridColumn Field=@nameof(OrdersDetails.OrderID) HeaderText="Order ID" IsPrimaryKey="true" TextAlign="@TextAlign.Center" HeaderTextAlign="@TextAlign.Center" Width="140"></GridColumn>
        <GridColumn Field=@nameof(OrdersDetails.CustomerID) HeaderText="Customer Name" Width="150"></GridColumn>
        <GridColumn Field=@nameof(OrdersDetails.Freight) HeaderText="Freight" Format="C2" Width="140" TextAlign="@TextAlign.Right" HeaderTextAlign="@TextAlign.Right"></GridColumn>
        <GridColumn Field=@nameof(OrdersDetails.OrderDate) HeaderText="Order Date" Format="d" Type="ColumnType.Date" Width="160"></GridColumn>
        <GridColumn Field=@nameof(OrdersDetails.ShipCountry) HeaderText="Ship Country" Width="150"></GridColumn>
    </GridColumns>
</SfGrid>

@code{
    public List<OrdersDetails> GridData = new List<OrdersDetails>
    {
        new OrdersDetails() { OrderID = 10248, CustomerID = "VINET", Freight = 32.38, ShipCity = "Berlin", OrderDate = DateTime.Now.AddDays(-2), ShipName = "Vins et alcools Chevalier", ShipCountry = "Denmark", ShipAddress = "Kirchgasse 6" },
        new OrdersDetails() { OrderID = 10249, CustomerID = "TOMSP", Freight = 11.61, ShipCity = "Madrid", OrderDate = DateTime.Now.AddDays(-5), ShipName = "Toms Spezialitäten", ShipCountry = "Brazil", ShipAddress = "Avda. Azteca 123" },
        new OrdersDetails() { OrderID = 10250, CustomerID = "HANAR", Freight = 65.83, ShipCity = "Cholchester", OrderDate = DateTime.Now.AddDays(-12), ShipName = "Hanari Carnes", ShipCountry = "Germany", ShipAddress = "Carrera 52 con Ave. Bolívar #65-98 Llano Largo" },
        new OrdersDetails() { OrderID = 10251, CustomerID = "VICTE", Freight = 41.34, ShipCity = "Marseille", OrderDate = DateTime.Now.AddDays(-18), ShipName = "Victuailles en stock", ShipCountry = "Austria", ShipAddress = "Magazinweg 7" },
        new OrdersDetails() { OrderID = 10252, CustomerID = "SUPRD", Freight = 51.3, ShipCity = "Tsawassen", OrderDate = DateTime.Now.AddDays(-22), ShipName = "Suprêmes délices", ShipCountry = "Switzerland", ShipAddress = "1029 - 12th Ave. S." },
        new OrdersDetails() { OrderID = 10253, CustomerID = "HANAR", Freight = 58.17, ShipCity = "Tsawassen", OrderDate = DateTime.Now.AddDays(-26), ShipName = "Hanari Carnes", ShipCountry = "Switzerland", ShipAddress = "1029 - 12th Ave. S." },
        new OrdersDetails() { OrderID = 10254, CustomerID = "CHOPS", Freight = 22.98, ShipCity = "Berlin", OrderDate = DateTime.Now.AddDays(-34), ShipName = "Chop-suey Chinese", ShipCountry = "Denmark", ShipAddress = "Kirchgasse 6" },
        new OrdersDetails() { OrderID = 10255, CustomerID = "RICSU", Freight = 148.33, ShipCity = "Madrid", OrderDate = DateTime.Now.AddDays(-39), ShipName = "Richter Supermarket", ShipCountry = "Brazil", ShipAddress = "Avda. Azteca 123" },
        new OrdersDetails() { OrderID = 10256, CustomerID = "WELLI", Freight = 13.97, ShipCity = "Madrid", OrderDate = DateTime.Now.AddDays(-43), ShipName = "Wellington Importadora", ShipCountry = "Brazil", ShipAddress = "Avda. Azteca 123" },
        new OrdersDetails() { OrderID = 10257, CustomerID = "HILAA", Freight = 81.91, ShipCity = "Cholchester", OrderDate = DateTime.Now.AddDays(-48), ShipName = "HILARION-Abastos", ShipCountry = "Germany", ShipAddress = "Carrera 52 con Ave. Bolívar #65-98 Llano Largo" }
    };

    public class OrdersDetails {
        public int? OrderID { get; set; }
        public string CustomerID { get; set; }
        public double? Freight { get; set; }
        public string ShipCity { get; set; }
        public DateTime OrderDate { get; set; }
        public string ShipName { get; set; }
        public string ShipCountry { get; set; }
        public string ShipAddress { get; set; }
    }
}

<style>
    .form-group.col-md-6 {
        width: 200px;
    }

    label.e-float-text {
        position: relative;
        padding-left: 0;
        top: 10%;
    }
</style>
```

> In the above sample code, the textbox rendered for **OrderID** column inside the dialog template is disabled using its `Enabled` property to prevent editing of the primary key column.

The following image represents the dialog template that is displayed on double-clicking a DataGrid cell,
![Dialog Template](./images/dialog-edit-template.png)

### Disable components in dialog template

It is possible to disable particular components rendered inside the dialog template using the data source value. This can be achieved by utilizing the `Enabled` property of the components which specifies whether the component is enabled or disabled.

This is demonstrated in the below sample code where if the `RequestType` argument value of the [`OnActionBegin`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridEvents%601~OnActionBegin.html) event is **BeginEdit** then the `Enabled` property of the **OrderID** Textbox is set to false.

```csharp
@using Syncfusion.Blazor.Grids
@using Syncfusion.Blazor.Calendars
@using Syncfusion.Blazor.DropDowns
@using Syncfusion.Blazor.Inputs

<SfGrid  DataSource="@GridData" Toolbar="@(new string[] {"Add", "Edit" ,"Delete","Update","Cancel" })">
    <GridEvents OnActionBegin="ActionBeginHandler" TValue="OrdersDetails"></GridEvents>
    <GridEditSettings AllowAdding="true" AllowEditing="true" AllowDeleting="true" Mode="@EditMode.Dialog">
        <Template>
            @{
                var Order = (context as OrdersDetails);
                <div>
                    <div class="form-row">
                        <div class="form-group col-md-6">
                            <label class="e-float-text e-label-top">Order ID</label>
                            <SfTextBox ID="OrderID" Value="@(Order.OrderID.ToString())" Enabled="@Enabled"></SfTextBox>
                        </div>
                        <div class="form-group col-md-6">
                            <label class="e-float-text e-label-top">Customer Name</label>
                            <SfAutoComplete ID="customerID" FloatLabelType="FloatLabelType.Auto" Value="@(Order.CustomerID)" TValue="string" DataSource="@GridData">
                                <AutoCompleteFieldSettings Value="CustomerID"></AutoCompleteFieldSettings>
                            </SfAutoComplete>
                        </div>
                    </div>
                    <div class="form-row">
                        <div class="form-group col-md-6">
                            <label class="e-float-text e-label-top">Freight</label>
                            <SfNumericTextBox ID="Freight" Value="@(Order.Freight)" TValue="double?"></SfNumericTextBox>
                        </div>
                        <div class="form-group col-md-6">
                            <label class="e-float-text e-label-top">Order Date</label>
                            <SfDatePicker ID="OrderDate" Value="@(Order.OrderDate)"></SfDatePicker>
                        </div>
                    </div>
                    <div class="form-row">
                        <div class="form-group col-md-6">
                            <label class="e-float-text e-label-top">Ship Country</label>
                            <SfDropDownList ID="ShipCountry" Value="@(Order.ShipCountry)" TItem="OrdersDetails" TValue="string" DataSource="@GridData">
                                <DropDownListFieldSettings Value="ShipCountry" Text="ShipCountry"></DropDownListFieldSettings>
                            </SfDropDownList>
                        </div>
                        <div class="form-group col-md-6">
                            <label class="e-float-text e-label-top">Ship City</label>
                            <SfDropDownList ID="ShipCity" Value="@(Order.ShipCity)" TItem="OrdersDetails" TValue="string" DataSource="@GridData">
                                <DropDownListFieldSettings Value="ShipCity" Text="ShipCity"></DropDownListFieldSettings>
                            </SfDropDownList>
                        </div>
                    </div>
                    <div class="form-row">
                        <div class="form-group col-md-12">
                            <label class="e-float-text e-label-top">Ship Address</label>
                            <SfTextBox ID="ShipAddress" Value="@(Order.ShipAddress)"></SfTextBox>
                        </div>
                    </div>
                </div>
            }
        </Template>
    </GridEditSettings>
    <GridColumns>
        <GridColumn Field=@nameof(OrdersDetails.OrderID) HeaderText="Order ID" IsPrimaryKey="true" TextAlign="@TextAlign.Center" HeaderTextAlign="@TextAlign.Center" Width="140"></GridColumn>
        <GridColumn Field=@nameof(OrdersDetails.CustomerID) HeaderText="Customer Name" Width="150"></GridColumn>
        <GridColumn Field=@nameof(OrdersDetails.Freight) HeaderText="Freight" Format="C2" Width="140" TextAlign="@TextAlign.Right" HeaderTextAlign="@TextAlign.Right"></GridColumn>
        <GridColumn Field=@nameof(OrdersDetails.OrderDate) HeaderText="Order Date" Format="d" Type="ColumnType.Date" Width="160"></GridColumn>
        <GridColumn Field=@nameof(OrdersDetails.ShipCountry) HeaderText="Ship Country" Width="150"></GridColumn>
    </GridColumns>
</SfGrid>

@code{
    public bool Enabled = true;

    public List<OrdersDetails> GridData = new List<OrdersDetails>
{
        new OrdersDetails() { OrderID = 10248, CustomerID = "VINET", Freight = 32.38, ShipCity = "Berlin", OrderDate = DateTime.Now.AddDays(-2), ShipName = "Vins et alcools Chevalier", ShipCountry = "Denmark", ShipAddress = "Kirchgasse 6" },
        new OrdersDetails() { OrderID = 10249, CustomerID = "TOMSP", Freight = 11.61, ShipCity = "Madrid", OrderDate = DateTime.Now.AddDays(-5), ShipName = "Toms Spezialitäten", ShipCountry = "Brazil", ShipAddress = "Avda. Azteca 123" },
        new OrdersDetails() { OrderID = 10250, CustomerID = "HANAR", Freight = 65.83, ShipCity = "Cholchester", OrderDate = DateTime.Now.AddDays(-12), ShipName = "Hanari Carnes", ShipCountry = "Germany", ShipAddress = "Carrera 52 con Ave. Bolívar #65-98 Llano Largo" },
        new OrdersDetails() { OrderID = 10251, CustomerID = "VICTE", Freight = 41.34, ShipCity = "Marseille", OrderDate = DateTime.Now.AddDays(-18), ShipName = "Victuailles en stock", ShipCountry = "Austria", ShipAddress = "Magazinweg 7" },
        new OrdersDetails() { OrderID = 10252, CustomerID = "SUPRD", Freight = 51.3, ShipCity = "Tsawassen", OrderDate = DateTime.Now.AddDays(-22), ShipName = "Suprêmes délices", ShipCountry = "Switzerland", ShipAddress = "1029 - 12th Ave. S." },
        new OrdersDetails() { OrderID = 10253, CustomerID = "HANAR", Freight = 58.17, ShipCity = "Tsawassen", OrderDate = DateTime.Now.AddDays(-26), ShipName = "Hanari Carnes", ShipCountry = "Switzerland", ShipAddress = "1029 - 12th Ave. S." },
        new OrdersDetails() { OrderID = 10254, CustomerID = "CHOPS", Freight = 22.98, ShipCity = "Berlin", OrderDate = DateTime.Now.AddDays(-34), ShipName = "Chop-suey Chinese", ShipCountry = "Denmark", ShipAddress = "Kirchgasse 6" },
        new OrdersDetails() { OrderID = 10255, CustomerID = "RICSU", Freight = 148.33, ShipCity = "Madrid", OrderDate = DateTime.Now.AddDays(-39), ShipName = "Richter Supermarket", ShipCountry = "Brazil", ShipAddress = "Avda. Azteca 123" },
        new OrdersDetails() { OrderID = 10256, CustomerID = "WELLI", Freight = 13.97, ShipCity = "Madrid", OrderDate = DateTime.Now.AddDays(-43), ShipName = "Wellington Importadora", ShipCountry = "Brazil", ShipAddress = "Avda. Azteca 123" },
        new OrdersDetails() { OrderID = 10257, CustomerID = "HILAA", Freight = 81.91, ShipCity = "Cholchester", OrderDate = DateTime.Now.AddDays(-48), ShipName = "HILARION-Abastos", ShipCountry = "Germany", ShipAddress = "Carrera 52 con Ave. Bolívar #65-98 Llano Largo" }
    };

    public class OrdersDetails
    {
        public int OrderID { get; set; }
        public string CustomerID { get; set; }
        public double Freight { get; set; }
        public string ShipCity { get; set; }
        public DateTime OrderDate { get; set; }
        public string ShipName { get; set; }
        public string ShipCountry { get; set; }
        public string ShipAddress { get; set; }
    }

    public void ActionBeginHandler(ActionEventArgs<OrdersDetails> args)
    {
        if (args.RequestType == Syncfusion.Blazor.Grids.Action.BeginEdit)
        {
            // The Textbox component is disabled using its Enabled property
            this.Enabled = false;
        }
        else
        {
            this.Enabled = true;
        }
    }
}

<style>
    .form-group.col-md-6 {
        width: 200px;
    }

    label.e-float-text {
        position: relative;
        padding-left: 0;
        top: 10%;
    }
</style>
```

The following image represents the dialog template of the DataGrid component with disabled components,
![Disable components](./images/disable-component.png)

### Set focus to editor

By default, the first input element in the dialog will be focused while opening it. If the first input element is in disabled or hidden state, you can set focus to the required input element in the corresponding components **Created** or **DataBound** event.

This is demonstrated in the below sample code where the first input element is in disabled state. So the  **CustomerID** Autocomplete component is focused by invoking its [`FocusIn`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.DropDowns.SfAutoComplete%601~FocusIn.html) method in the AutoComplete's [`DataBound`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.DropDowns.AutoCompleteEvents%601~DataBound.html) event.

```csharp
@using Syncfusion.Blazor.Grids
@using Syncfusion.Blazor.Calendars
@using Syncfusion.Blazor.DropDowns
@using Syncfusion.Blazor.Inputs

<SfGrid  DataSource="@GridData" Toolbar="@(new string[] {"Add", "Edit" ,"Delete","Update","Cancel" })">
    <GridEditSettings AllowAdding="true" AllowEditing="true" AllowDeleting="true" Mode="@EditMode.Dialog">
        <Template>
            @{
                var Order = (context as OrdersDetails);
                <div>
                    <div class="form-row">
                        <div class="form-group col-md-6">
                            <label class="e-float-text e-label-top">Order ID</label>
                            <SfTextBox ID="OrderID" Value="@(Order.OrderID.ToString())" Enabled="false"></SfTextBox>
                        </div>
                        <div class="form-group col-md-6">
                            <label class="e-float-text e-label-top">Customer Name</label>
                            <SfAutoComplete ID="customerID" @ref="AutoComplete" FloatLabelType="FloatLabelType.Auto" Value="@(Order.CustomerID)" TValue="string" DataSource="@GridData">
                                <AutoCompleteEvents DataBound="OnDataBound" TValue="OrdersDetails"></AutoCompleteEvents>
                                <AutoCompleteFieldSettings Value="CustomerID"></AutoCompleteFieldSettings>
                            </SfAutoComplete>
                        </div>
                    </div>
                    <div class="form-row">
                        <div class="form-group col-md-6">
                            <label class="e-float-text e-label-top">Freight</label>
                            <SfNumericTextBox ID="Freight" Value="@(Order.Freight)" TValue="double?"></SfNumericTextBox>
                        </div>
                        <div class="form-group col-md-6">
                            <label class="e-float-text e-label-top">Order Date</label>
                            <SfDatePicker ID="OrderDate" Value="@(Order.OrderDate)"></SfDatePicker>
                        </div>
                    </div>
                    <div class="form-row">
                        <div class="form-group col-md-6">
                            <label class="e-float-text e-label-top">Ship Country</label>
                            <SfDropDownList ID="ShipCountry" Value="@(Order.ShipCountry)" TItem="OrdersDetails" TValue="string" DataSource="@GridData">
                                <DropDownListFieldSettings Value="ShipCountry" Text="ShipCountry"></DropDownListFieldSettings>
                            </SfDropDownList>
                        </div>
                        <div class="form-group col-md-6">
                            <label class="e-float-text e-label-top">Ship City</label>
                            <SfDropDownList ID="ShipCity" Value="@(Order.ShipCity)" TItem="OrdersDetails" TValue="string" DataSource="@GridData">
                                <DropDownListFieldSettings Value="ShipCity" Text="ShipCity"></DropDownListFieldSettings>
                            </SfDropDownList>
                        </div>
                    </div>
                    <div class="form-row">
                        <div class="form-group col-md-12">
                            <label class="e-float-text e-label-top">Ship Address</label>
                            <SfTextBox ID="ShipAddress" Value="@(Order.ShipAddress)"></SfTextBox>
                        </div>
                    </div>
                </div>
            }
        </Template>
    </GridEditSettings>
    <GridColumns>
        <GridColumn Field=@nameof(OrdersDetails.OrderID) HeaderText="Order ID" IsPrimaryKey="true" TextAlign="@TextAlign.Center" HeaderTextAlign="@TextAlign.Center" Width="140"></GridColumn>
        <GridColumn Field=@nameof(OrdersDetails.CustomerID) HeaderText="Customer Name" Width="150"></GridColumn>
        <GridColumn Field=@nameof(OrdersDetails.Freight) HeaderText="Freight" Format="C2" Width="140" TextAlign="@TextAlign.Right" HeaderTextAlign="@TextAlign.Right"></GridColumn>
        <GridColumn Field=@nameof(OrdersDetails.OrderDate) HeaderText="Order Date" Format="d" Type="ColumnType.Date" Width="160"></GridColumn>
        <GridColumn Field=@nameof(OrdersDetails.ShipCountry) HeaderText="Ship Country" Width="150"></GridColumn>
    </GridColumns>
</SfGrid>

@code{
    private SfAutoComplete<string> AutoComplete;
    public List<OrdersDetails> GridData = new List<OrdersDetails>
    {
        new OrdersDetails() { OrderID = 10248, CustomerID = "VINET", Freight = 32.38, ShipCity = "Berlin", OrderDate = DateTime.Now.AddDays(-2), ShipName = "Vins et alcools Chevalier", ShipCountry = "Denmark", ShipAddress = "Kirchgasse 6" },
        new OrdersDetails() { OrderID = 10249, CustomerID = "TOMSP", Freight = 11.61, ShipCity = "Madrid", OrderDate = DateTime.Now.AddDays(-5), ShipName = "Toms Spezialitäten", ShipCountry = "Brazil", ShipAddress = "Avda. Azteca 123" },
        new OrdersDetails() { OrderID = 10250, CustomerID = "HANAR", Freight = 65.83, ShipCity = "Cholchester", OrderDate = DateTime.Now.AddDays(-12), ShipName = "Hanari Carnes", ShipCountry = "Germany", ShipAddress = "Carrera 52 con Ave. Bolívar #65-98 Llano Largo" },
        new OrdersDetails() { OrderID = 10251, CustomerID = "VICTE", Freight = 41.34, ShipCity = "Marseille", OrderDate = DateTime.Now.AddDays(-18), ShipName = "Victuailles en stock", ShipCountry = "Austria", ShipAddress = "Magazinweg 7" },
        new OrdersDetails() { OrderID = 10252, CustomerID = "SUPRD", Freight = 51.3, ShipCity = "Tsawassen", OrderDate = DateTime.Now.AddDays(-22), ShipName = "Suprêmes délices", ShipCountry = "Switzerland", ShipAddress = "1029 - 12th Ave. S." },
        new OrdersDetails() { OrderID = 10253, CustomerID = "HANAR", Freight = 58.17, ShipCity = "Tsawassen", OrderDate = DateTime.Now.AddDays(-26), ShipName = "Hanari Carnes", ShipCountry = "Switzerland", ShipAddress = "1029 - 12th Ave. S." },
        new OrdersDetails() { OrderID = 10254, CustomerID = "CHOPS", Freight = 22.98, ShipCity = "Berlin", OrderDate = DateTime.Now.AddDays(-34), ShipName = "Chop-suey Chinese", ShipCountry = "Denmark", ShipAddress = "Kirchgasse 6" },
        new OrdersDetails() { OrderID = 10255, CustomerID = "RICSU", Freight = 148.33, ShipCity = "Madrid", OrderDate = DateTime.Now.AddDays(-39), ShipName = "Richter Supermarket", ShipCountry = "Brazil", ShipAddress = "Avda. Azteca 123" },
        new OrdersDetails() { OrderID = 10256, CustomerID = "WELLI", Freight = 13.97, ShipCity = "Madrid", OrderDate = DateTime.Now.AddDays(-43), ShipName = "Wellington Importadora", ShipCountry = "Brazil", ShipAddress = "Avda. Azteca 123" },
        new OrdersDetails() { OrderID = 10257, CustomerID = "HILAA", Freight = 81.91, ShipCity = "Cholchester", OrderDate = DateTime.Now.AddDays(-48), ShipName = "HILARION-Abastos", ShipCountry = "Germany", ShipAddress = "Carrera 52 con Ave. Bolívar #65-98 Llano Largo" }
    };

    public class OrdersDetails {
        public int? OrderID { get; set; }
        public string CustomerID { get; set; }
        public double? Freight { get; set; }
        public string ShipCity { get; set; }
        public DateTime OrderDate { get; set; }
        public string ShipName { get; set; }
        public string ShipCountry { get; set; }
        public string ShipAddress { get; set; }
    }

    public void OnDataBound()
    {
        this.AutoComplete.FocusIn();
    }
}

<style>
    .form-group.col-md-6 {
        width: 200px;
    }

    label.e-float-text {
        position: relative;
        padding-left: 0;
        top: 10%;
    }
</style>
```

The following image represents the AutoComplete component in focused state inside the dialog template of the DataGrid component,
![Dynamic focus of components](./images/dynamic-focus.png)

## Inline Template

> Before adding Inline template to the datagrid, we strongly recommend you to go through the [`Template`](./templates/#templates) section topic to configure the template.

The Inline template editing provides an option to customize the default behavior of Inline editing. Using the Inline template, you can render your own editors by defining the [`GridEditSettings`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridEditSettings.html) component's [`Mode`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridEditSettings~Mode.html) property as **Normal** and wrapping the HTML elements inside the [`Template`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridEditSettings~Template.html) property of [`GridEditSettings`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridEditSettings.html).

In some cases, you would need to add new field editors in the Inline editing which are not present in the column model. In that case, the Inline template editing will help you to customize the default editing.

The following sample code demonstrates DataGrid enabled with Inline template editing,

```csharp
@using Syncfusion.Blazor.Grids
@using Syncfusion.Blazor.Calendars
@using Syncfusion.Blazor.DropDowns
@using Syncfusion.Blazor.Inputs

<SfGrid DataSource="@GridData" Toolbar="@(new string[] {"Add", "Edit" ,"Delete","Update","Cancel" })">
    <GridEditSettings AllowAdding="true" AllowEditing="true" AllowDeleting="true" Mode="@EditMode.Normal">
        <Template>
            @{
                var Order = (context as OrdersDetails);
                <div>
                    <div class="form-row">
                        <div class="form-group col-md-6">
                            <label class="e-float-text e-label-top">Order ID</label>
                            <SfTextBox ID="OrderID" Value="@(Order.OrderID.ToString())" Enabled="false"></SfTextBox>
                        </div>
                        <div class="form-group col-md-6">
                            <label class="e-float-text e-label-top">Customer Name</label>
                            <SfAutoComplete ID="customerID" FloatLabelType="FloatLabelType.Auto" Value="@(Order.CustomerID)" TValue="string" DataSource="@GridData">
                                <AutoCompleteFieldSettings Value="CustomerID"></AutoCompleteFieldSettings>
                            </SfAutoComplete>
                        </div>
                    </div>
                    <div class="form-row">
                        <div class="form-group col-md-6">
                            <label class="e-float-text e-label-top">Freight</label>
                            <SfNumericTextBox ID="Freight" Value="@(Order.Freight)" TValue="double?"></SfNumericTextBox>
                        </div>
                        <div class="form-group col-md-6">
                            <label class="e-float-text e-label-top">Order Date</label>
                            <SfDatePicker ID="OrderDate" Value="@(Order.OrderDate)"></SfDatePicker>
                        </div>
                    </div>
                    <div class="form-row">
                        <div class="form-group col-md-6">
                            <label class="e-float-text e-label-top">Ship Country</label>
                            <SfDropDownList ID="ShipCountry" TItem="OrdersDetails" Value="@(Order.ShipCountry)" TValue="string" DataSource="@GridData">
                                <DropDownListFieldSettings Value="ShipCountry" Text="ShipCountry"></DropDownListFieldSettings>
                            </SfDropDownList>
                        </div>
                        <div class="form-group col-md-6">
                            <label class="e-float-text e-label-top">Ship City</label>
                            <SfDropDownList ID="ShipCity" TItem="OrdersDetails" Value="@(Order.ShipCity)" TValue="string" DataSource="@GridData">
                                <DropDownListFieldSettings Value="ShipCity" Text="ShipCity"></DropDownListFieldSettings>
                            </SfDropDownList>
                        </div>
                    </div>
                    <div class="form-row">
                        <div class="form-group col-md-12">
                            <label class="e-float-text e-label-top">Ship Address</label>
                            <SfTextBox ID="ShipAddress" Value="@(Order.ShipAddress)"></SfTextBox>
                        </div>
                    </div>
                </div>
            }
        </Template>
    </GridEditSettings>
    <GridColumns>
        <GridColumn Field=@nameof(OrdersDetails.OrderID) HeaderText="Order ID" IsPrimaryKey="true" TextAlign="@TextAlign.Center" HeaderTextAlign="@TextAlign.Center" Width="140"></GridColumn>
        <GridColumn Field=@nameof(OrdersDetails.CustomerID) HeaderText="Customer Name" Width="150"></GridColumn>
        <GridColumn Field=@nameof(OrdersDetails.Freight) HeaderText="Freight" Format="C2" Width="140" TextAlign="@TextAlign.Right" HeaderTextAlign="@TextAlign.Right"></GridColumn>
        <GridColumn Field=@nameof(OrdersDetails.OrderDate) HeaderText="Order Date" Format="d" Type="ColumnType.Date" Width="160"></GridColumn>
        <GridColumn Field=@nameof(OrdersDetails.ShipCountry) HeaderText="Ship Country" Width="150"></GridColumn>
    </GridColumns>
</SfGrid>

@code{
    public List<OrdersDetails> GridData = new List<OrdersDetails>
    {
        new OrdersDetails() { OrderID = 10248, CustomerID = "VINET", Freight = 32.38, ShipCity = "Berlin", OrderDate = DateTime.Now.AddDays(-2), ShipName = "Vins et alcools Chevalier", ShipCountry = "Denmark", ShipAddress = "Kirchgasse 6" },
        new OrdersDetails() { OrderID = 10249, CustomerID = "TOMSP", Freight = 11.61, ShipCity = "Madrid", OrderDate = DateTime.Now.AddDays(-5), ShipName = "Toms Spezialitäten", ShipCountry = "Brazil", ShipAddress = "Avda. Azteca 123" },
        new OrdersDetails() { OrderID = 10250, CustomerID = "HANAR", Freight = 65.83, ShipCity = "Cholchester", OrderDate = DateTime.Now.AddDays(-12), ShipName = "Hanari Carnes", ShipCountry = "Germany", ShipAddress = "Carrera 52 con Ave. Bolívar #65-98 Llano Largo" },
        new OrdersDetails() { OrderID = 10251, CustomerID = "VICTE", Freight = 41.34, ShipCity = "Marseille", OrderDate = DateTime.Now.AddDays(-18), ShipName = "Victuailles en stock", ShipCountry = "Austria", ShipAddress = "Magazinweg 7" },
        new OrdersDetails() { OrderID = 10252, CustomerID = "SUPRD", Freight = 51.3, ShipCity = "Tsawassen", OrderDate = DateTime.Now.AddDays(-22), ShipName = "Suprêmes délices", ShipCountry = "Switzerland", ShipAddress = "1029 - 12th Ave. S." },
        new OrdersDetails() { OrderID = 10253, CustomerID = "HANAR", Freight = 58.17, ShipCity = "Tsawassen", OrderDate = DateTime.Now.AddDays(-26), ShipName = "Hanari Carnes", ShipCountry = "Switzerland", ShipAddress = "1029 - 12th Ave. S." },
        new OrdersDetails() { OrderID = 10254, CustomerID = "CHOPS", Freight = 22.98, ShipCity = "Berlin", OrderDate = DateTime.Now.AddDays(-34), ShipName = "Chop-suey Chinese", ShipCountry = "Denmark", ShipAddress = "Kirchgasse 6" },
        new OrdersDetails() { OrderID = 10255, CustomerID = "RICSU", Freight = 148.33, ShipCity = "Madrid", OrderDate = DateTime.Now.AddDays(-39), ShipName = "Richter Supermarket", ShipCountry = "Brazil", ShipAddress = "Avda. Azteca 123" },
        new OrdersDetails() { OrderID = 10256, CustomerID = "WELLI", Freight = 13.97, ShipCity = "Madrid", OrderDate = DateTime.Now.AddDays(-43), ShipName = "Wellington Importadora", ShipCountry = "Brazil", ShipAddress = "Avda. Azteca 123" },
        new OrdersDetails() { OrderID = 10257, CustomerID = "HILAA", Freight = 81.91, ShipCity = "Cholchester", OrderDate = DateTime.Now.AddDays(-48), ShipName = "HILARION-Abastos", ShipCountry = "Germany", ShipAddress = "Carrera 52 con Ave. Bolívar #65-98 Llano Largo" }
    };

    public class OrdersDetails
    {
        public int? OrderID { get; set; }
        public string CustomerID { get; set; }
        public double? Freight { get; set; }
        public string ShipCity { get; set; }
        public DateTime OrderDate { get; set; }
        public string ShipName { get; set; }
        public string ShipCountry { get; set; }
        public string ShipAddress { get; set; }
    }
}

<style>
    .form-group.col-md-6 {
        width: 200px;
    }

    label.e-float-text {
        position: relative;
        padding-left: 0;
        top: 10%;
    }
</style>
```

> In the above sample code, the textbox rendered for **OrderID** column inside the Inline editing template is disabled using its `Enabled` property to prevent editing of the primary key column.

## Adding a new row at the bottom of the datagrid

By default, a new row will be added at the top of the datagrid. You can change it by setting [`NewRowPosition`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridEditSettings~NewRowPosition.html) property of the [`GridEditSettings`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridEditSettings.html) component as **Bottom**.

The following sample code demonstrates changing the position of the new row that gets added in the DataGrid component,

```csharp
@using Syncfusion.Blazor.Grids

<SfGrid DataSource="@Orders" Height="315" AllowPaging="true" Toolbar="@(new List<string>() { "Add", "Edit", "Delete", "Update", "Cancel" })">
    <GridEditSettings AllowAdding="true" AllowEditing="true" AllowDeleting="true" NewRowPosition="NewRowPosition.Bottom"></GridEditSettings>
    <GridColumns>
        <GridColumn Field=@nameof(Order.OrderID) HeaderText="Order ID" IsPrimaryKey="true" TextAlign="TextAlign.Right" Width="120"></GridColumn>
        <GridColumn Field=@nameof(Order.CustomerID) HeaderText="Customer Name" Width="120"></GridColumn>
        <GridColumn Field=@nameof(Order.OrderDate) HeaderText=" Order Date" EditType="EditType.DatePickerEdit" Format="d" TextAlign="TextAlign.Right" Width="130" Type="ColumnType.Date"></GridColumn>
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

The following image represents the new row added at the bottom of the DataGrid,
![New Row Position](./images/new-row-position.png)

## Confirmation messages

It is possible to display confirmation dialog's on performing deletion or batch operations on the DataGrid records.

### Delete confirmation

The delete confirm dialog can be shown on deleting a record by setting the [`ShowDeleteConfirmDialog`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridEditSettings~ShowDeleteConfirmDialog.html) property of the [`GridEditSettings`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridEditSettings.html) component as **true**.

The following sample code demonstrates enabling delete confirmation dialog in the DataGrid component,

```csharp
@using Syncfusion.Blazor.Grids

<SfGrid DataSource="@Orders" Height="315" AllowPaging="true" Toolbar="@(new List<string>() { "Add", "Edit", "Delete", "Update", "Cancel" })">
    <GridEditSettings AllowAdding="true" AllowEditing="true" AllowDeleting="true" ShowDeleteConfirmDialog="true"></GridEditSettings>
    <GridColumns>
        <GridColumn Field=@nameof(Order.OrderID) HeaderText="Order ID" IsPrimaryKey="true" TextAlign="TextAlign.Right" Width="120"></GridColumn>
        <GridColumn Field=@nameof(Order.CustomerID) HeaderText="Customer Name" Width="120"></GridColumn>
        <GridColumn Field=@nameof(Order.OrderDate) HeaderText=" Order Date" EditType="EditType.DatePickerEdit" Format="d" TextAlign="TextAlign.Right" Width="130" Type="ColumnType.Date"></GridColumn>
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

    public class Order
    {
        public int? OrderID { get; set; }
        public string CustomerID { get; set; }
        public DateTime? OrderDate { get; set; }
        public double? Freight { get; set; }
    }
}
```

The following GIF represents the delete confirmation dialog displayed while deleting a record in DataGrid,
![Delete confirmation dialog](./images/delete-confirm-dialog.gif)

> The [`ShowDeleteConfirmDialog`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridEditSettings~ShowDeleteConfirmDialog.html) supports all type of edit modes.

### Batch confirmation

The confirmation dialog can be enabled for all the batch operations by setting the [`ShowConfirmDialog`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridEditSettings~ShowConfirmDialog.html) property of the [`GridEditSettings`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridEditSettings.html) component as **true**.

The following sample code demonstrates enabling confirmation dialog for batch operations in the DataGrid component,

```csharp
@using Syncfusion.Blazor.Grids

<SfGrid DataSource="@Orders" Height="315" AllowPaging="true" AllowSorting="true" Toolbar="@(new List<string>() { "Add", "Edit", "Delete", "Update", "Cancel" })">
    <GridEditSettings AllowAdding="true" AllowEditing="true" AllowDeleting="true" ShowConfirmDialog="true" ShowDeleteConfirmDialog="true" Mode="EditMode.Batch"></GridEditSettings>
    <GridColumns>
        <GridColumn Field=@nameof(Order.OrderID) HeaderText="Order ID" IsPrimaryKey="true" TextAlign="TextAlign.Right" Width="120"></GridColumn>
        <GridColumn Field=@nameof(Order.CustomerID) HeaderText="Customer Name" Width="120"></GridColumn>
        <GridColumn Field=@nameof(Order.OrderDate) HeaderText=" Order Date" EditType="EditType.DatePickerEdit" Format="d" TextAlign="TextAlign.Right" Width="130" Type="ColumnType.Date"></GridColumn>
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

    public class Order
    {
        public int? OrderID { get; set; }
        public string CustomerID { get; set; }
        public DateTime? OrderDate { get; set; }
        public double? Freight { get; set; }
    }
}
```

The following GIF represents the confirmation dialog displayed while performing batch operations in DataGrid,
![Confirmation dialog](./images/confirmation-dialog.gif)

> Enabling [`ShowConfirmDialog`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridEditSettings~ShowConfirmDialog.html) requires the [`Mode`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridEditSettings~Mode.html) property value of the [`GridEditSettings`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridEditSettings.html) component to be **Batch**.
> If [`ShowConfirmDialog`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridEditSettings~ShowConfirmDialog.html) is set to false, then confirmation dialog will not be displayed on batch editing.

## Default column values on adding new record

The datagrid provides an option to set the default value for the columns when adding a new record in it. To set a default value for a particular column you need to define it in the [`DefaultValue`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridColumn~DefaultValue.html) property of the [`GridColumn`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridColumn.html) component.

The following sample code demonstrates setting default value as **ANTON** to the **CustomerID** column,

```csharp
@using Syncfusion.Blazor.Grids

<SfGrid DataSource="@Orders" Height="315" AllowPaging="true" Toolbar="@(new List<string>() { "Add", "Edit", "Delete", "Update", "Cancel" })">
    <GridEditSettings AllowAdding="true" AllowEditing="true" AllowDeleting="true"></GridEditSettings>
    <GridColumns>
        <GridColumn Field=@nameof(Order.OrderID) HeaderText="Order ID" IsPrimaryKey="true" TextAlign="TextAlign.Right" Width="120"></GridColumn>
        <GridColumn Field=@nameof(Order.CustomerID) HeaderText="Customer Name" Width="120" DefaultValue="@("ANTON")"></GridColumn>
        <GridColumn Field=@nameof(Order.OrderDate) HeaderText=" Order Date" EditType="EditType.DatePickerEdit" Format="d" TextAlign="TextAlign.Right" Width="130" Type="ColumnType.Date"></GridColumn>
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

    public class Order
    {
        public int? OrderID { get; set; }
        public string CustomerID { get; set; }
        public DateTime? OrderDate { get; set; }
        public double? Freight { get; set; }
    }
}
```

The following image represents the default value displayed in the **CustomerID** column while adding a new record in DataGrid,
![Default Column Value](./images/default-column-value.png)

## Disable editing for particular column

You can disable editing for particular columns by setting value as **false** to the [`AllowEditing`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridColumn~AllowEditing.html) property of the [`GridColumn`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridColumn.html) component.

The following sample code demonstrates editing disabled for the **CustomerID** column,

```csharp
@using Syncfusion.Blazor.Grids

<SfGrid DataSource="@Orders" Height="315" AllowPaging="true" Toolbar="@(new List<string>() { "Add", "Edit", "Delete", "Update", "Cancel" })">
    <GridEditSettings AllowAdding="true" AllowEditing="true" AllowDeleting="true"></GridEditSettings>
    <GridColumns>
        <GridColumn Field=@nameof(Order.OrderID) HeaderText="Order ID" IsPrimaryKey="true" TextAlign="TextAlign.Right" Width="120"></GridColumn>
        <GridColumn Field=@nameof(Order.CustomerID) HeaderText="Customer Name" Width="120" AllowEditing="false"></GridColumn>
        <GridColumn Field=@nameof(Order.OrderDate) HeaderText=" Order Date" EditType="EditType.DatePickerEdit" Format="d" TextAlign="TextAlign.Right" Width="130" Type="ColumnType.Date"></GridColumn>
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

    public class Order
    {
        public int? OrderID { get; set; }
        public string CustomerID { get; set; }
        public DateTime? OrderDate { get; set; }
        public double? Freight { get; set; }
    }
}
```

The following screenshot represents the editing disabled for the **CustomerID** column in DataGrid,
![Editing Disabled](./images/editing-disabled.png)

## Troubleshoot: Editing works only for first row

The Editing functionalities can be performed based upon the primary key value of the selected row. If **PrimaryKey** is not defined in the datagrid, then edit or delete action take places in the first row.

## Event trace while editing

While editing operation is getting executed the following events will be notified,

* OnActionBegin
* OnActionComplete

In both these events the type of editing operation is returned in the **RequestType** parameter of the event arguments. In addition to this, the event arguments also return the edited row data.

The **RequestType** values for the editing operations are listed in the below table,

| RequestType | OnActionBegin | OnActionComplete |
|----------|---------------|---------------|
| BeginEdit | Before editing operation begins | After editing operation is completed |
| Add | Before add operation begins | After add operation is completed |
| Delete | Before delete operation begins | After delete operation is completed |
| Save | Before save operation begins | After save operation is completed |
| Cancel | Before cancel operation begins | After cancel operation is completed |

The following sample code demonstrates the different **RequestType** parameters returned while performing editing operations in the OnActionBegin and OnActionComplete event,

```csharp
@using Syncfusion.Blazor.Grids

<SfGrid DataSource="@Orders" AllowPaging="true" Toolbar="@(new List<string>() { "Add", "Edit", "Delete", "Cancel", "Update" })" Height="315">
    <GridEditSettings AllowAdding="true" AllowEditing="true" AllowDeleting="true"></GridEditSettings>
    <GridEvents OnActionBegin="ActionBegin" OnActionComplete="ActionComplete" TValue="Order"></GridEvents>
    <GridColumns>
        <GridColumn Field=@nameof(Order.OrderID) HeaderText="Order ID" IsPrimaryKey="true" TextAlign="TextAlign.Right" Width="120"></GridColumn>
        <GridColumn Field=@nameof(Order.CustomerID) HeaderText="Customer Name" Width="120"></GridColumn>
        <GridColumn Field=@nameof(Order.OrderDate) HeaderText=" Order Date" EditType="EditType.DatePickerEdit" Format="d" TextAlign="TextAlign.Right" Width="130" Type="ColumnType.Date"></GridColumn>
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

    public class Order
    {
        public int? OrderID { get; set; }
        public string CustomerID { get; set; }
        public DateTime? OrderDate { get; set; }
        public double? Freight { get; set; }
    }

    public void ActionBegin(ActionEventArgs<Order> args)
    {
        if (args.RequestType == Syncfusion.Blazor.Grids.Action.BeginEdit)
        {
            // Triggers before editing operation starts
        }
        else if (args.RequestType == Syncfusion.Blazor.Grids.Action.Add)
        {
            // Triggers before add operation starts
        }
        else if (args.RequestType == Syncfusion.Blazor.Grids.Action.Cancel)
        {
            // Triggers before cancel operation starts
        }
        else if (args.RequestType == Syncfusion.Blazor.Grids.Action.Save)
        {
            // Triggers before save operation starts
        }
        else if (args.RequestType == Syncfusion.Blazor.Grids.Action.Delete)
        {
            // Triggers before delete operation starts
        }
    }

    public void ActionComplete(ActionEventArgs<Order> args)
    {
        if (args.RequestType == Syncfusion.Blazor.Grids.Action.BeginEdit)
        {
            // Triggers once editing operation completes
        }
        else if (args.RequestType == Syncfusion.Blazor.Grids.Action.Add)
        {
            // Triggers once add operation completes
        }
        else if (args.RequestType == Syncfusion.Blazor.Grids.Action.Cancel)
        {
            // Triggers once cancel operation completes
        }
        else if (args.RequestType == Syncfusion.Blazor.Grids.Action.Save)
        {
            // Triggers once save operation completes
        }
        else if (args.RequestType == Syncfusion.Blazor.Grids.Action.Delete)
        {
            // Triggers once delete operation completes
        }
    }
}
```

## Customize the edit dialog

You can use [`HeaderTemplate`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridEditSettings~HeaderTemplate.html) and [`FooterTemplate`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridEditSettings~FooterTemplate.html) of the [`GridEditSettings`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Grids.GridEditSettings.html) component to customize the appearance of edit dialog.

In the below example we have changed the dialog's header text and footer button content for editing and adding records.

```csharp
@using Syncfusion.Blazor.Buttons
@using Syncfusion.Blazor.Grids

<SfGrid @ref="Grid" DataSource="@Orders" AllowPaging="true" Toolbar="@(new List<string>() { "Add", "Edit", "Delete", "Update", "Cancel" })" Height="315">
    <GridEditSettings AllowAdding="true" AllowEditing="true" AllowDeleting="true" Mode="EditMode.Dialog">
        <HeaderTemplate>
            @{
                var text = GetHeader((context as Order));
                <span>@text</span>
            }
        </HeaderTemplate>
        <FooterTemplate>
            <SfButton OnClick="@Save" IsPrimary="true">@ButtonText</SfButton>
            <SfButton OnClick="@Cancel">Cancel</SfButton>
        </FooterTemplate>
    </GridEditSettings>
    <GridColumns>
        <GridColumn Field=@nameof(Order.OrderID) HeaderText="Order ID" IsPrimaryKey="true" ValidationRules="@(new { required=true})" TextAlign="TextAlign.Right" Width="120"></GridColumn>
        <GridColumn Field=@nameof(Order.CustomerID) HeaderText="Customer Name" ValidationRules="@(new { required=true})" Width="120"></GridColumn>
        <GridColumn Field=@nameof(Order.OrderDate) HeaderText=" Order Date" EditType="EditType.DatePickerEdit" Format="d" TextAlign="TextAlign.Right" Width="130" Type="ColumnType.Date"></GridColumn>
        <GridColumn Field=@nameof(Order.Freight) HeaderText="Freight" Format="C2" TextAlign="TextAlign.Right" EditType="EditType.NumericEdit" Width="120"></GridColumn>
        <GridColumn Field=@nameof(Order.ShipCountry) HeaderText="Ship Country" EditType="EditType.DropDownEdit" Width="150"></GridColumn>
    </GridColumns>
</SfGrid>

@code{
    SfGrid<Order> Grid { get; set; }
    public List<Order> Orders { get; set; }
    public string Header { get; set; }
    public string ButtonText { get; set; }
    public string GetHeader(Order Value)
    {
        if (Value.OrderID == null)
        {
            ButtonText = "Insert";
            return "Insert New Order";
        }
        else
        {
            ButtonText = "Save Changes";
            return "Edit Record Details of " + Value.OrderID.ToString();
        }
    }
    public async Task Cancel()
    {
        await Grid.CloseEdit();     //Cancel editing action
    }
    public async Task Save()
    {
        await Grid.EndEdit();       //Save the edited/added data to Grid
    }
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

    public class Order
    {
        public int? OrderID { get; set; }
        public string CustomerID { get; set; }
        public DateTime? OrderDate { get; set; }
        public double? Freight { get; set; }
        public string ShipCountry { get; set; }
    }
}
```
