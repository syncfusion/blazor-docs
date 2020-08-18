---
title: "Events"
component: "Pivot Table"
description: "Describes about available events in the Pivot Table."
---

# Events

## AggregateMenuOpen

To know more about this event, refer [here](./grouping-bar/#aggregatemenuopen).

## BeforeExport

To know more about this event, refer [here](./tool-bar/#beforereport).

## BeginDrillThrough

The event [`BeginDrillThrough`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.PivotViewEvents%601~BeginDrillThrough.html) is triggered when value cell is clicked in the Pivot Table while editing. To use this event, user need to enable editing option with the help of [`PivotViewCellEditSettings`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.PivotViewCellEditSettings_members.html) class. It has following parameters - [`CellInfo`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.BeginDrillThroughEventArgs~CellInfo.html) and [`Type`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.BeginDrillThroughEventArgs~Type.html). This event allows user to view the [`CellInfo`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.BeginDrillThroughEventArgs~CellInfo.html) which contains [`ColumnHeaders`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.DrillThroughEventArgs~ColumnHeaders.html), [`CurrentCell`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.DrillThroughEventArgs~CurrentCell.html), [`CurrentTarget`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.DrillThroughEventArgs~CurrentTarget.html), [`RawData`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.DrillThroughEventArgs~RawData.html), [`RowHeaders`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.DrillThroughEventArgs~RowHeaders.html) and [`Value`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.DrillThroughEventArgs~Value.html).

> In this event, the parameter [`GridObj`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.BeginDrillThroughEventArgs~GridObj.html) is returned as **null** due to its size.

```csharp

    @using Syncfusion.Blazor.PivotView

    <SfPivotView TValue="ProductDetails">
        <PivotViewDataSourceSettings DataSource="@data">
            <PivotViewColumns>
                <PivotViewColumn Name="Year"></PivotViewColumn>
                <PivotViewColumn Name="Quarter"></PivotViewColumn>
            </PivotViewColumns>
            <PivotViewRows>
                <PivotViewRow Name="Country"></PivotViewRow>
                <PivotViewRow Name="Products"></PivotViewRow>
            </PivotViewRows>
            <PivotViewValues>
                <PivotViewValue Name="Sold" Caption="Unit Sold"></PivotViewValue>
                <PivotViewValue Name="Amount" Caption="Amount"></PivotViewValue>
            </PivotViewValues>
        </PivotViewDataSourceSettings>
        <PivotViewEvents TValue="ProductDetails" BeginDrillThrough="beginDrill"></PivotViewEvents>
        <PivotViewCellEditSettings AllowEditing=true AllowAdding=true AllowDeleting=true Mode=EditMode.Normal></PivotViewCellEditSettings>
    </SfPivotView>

    @code{
        public List<ProductDetails> data { get; set; }
        protected override void OnInitialized()
        {
            this.data = ProductDetails.GetProductData().ToList();
           //Bind the data source collection here. Refer "Assigning sample data to the pivot table" section in getting started for more details.
        }
       private void beginDrill(BeginDrillThroughEventArgs args)
        {
            //args.CellInfo -> consists of cell info for drillthrough
        }

    }

```

## CalculatedFieldCreate

To know more about this event, refer [here](./calculated-field/#calculatedfieldcreate).

## CellClick

The event [`CellClick`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.PivotViewEvents%601~CellClick.html) is triggered whenever a cell is clicked in the Pivot Table component. It has following parameters - [`CurrentCell`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.CellClickEventArgs~CurrentCell.html) and [`Data`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.CellClickEventArgs~Data.html). For instance, using this event end user can either add or remove CSS class name from the respective cell and also perform many other DOM manipulations.

```csharp

    @using Syncfusion.Blazor.PivotView

    <SfPivotView TValue="ProductDetails">
        <PivotViewDataSourceSettings DataSource="@data">
            <PivotViewColumns>
                <PivotViewColumn Name="Year"></PivotViewColumn>
                <PivotViewColumn Name="Quarter"></PivotViewColumn>
            </PivotViewColumns>
            <PivotViewRows>
                <PivotViewRow Name="Country"></PivotViewRow>
                <PivotViewRow Name="Products"></PivotViewRow>
            </PivotViewRows>
            <PivotViewValues>
                <PivotViewValue Name="Sold" Caption="Unit Sold"></PivotViewValue>
                <PivotViewValue Name="Amount" Caption="Amount"></PivotViewValue>
            </PivotViewValues>
        </PivotViewDataSourceSettings>
        <PivotViewEvents TValue="ProductDetails" CellClick="cellClick"></PivotViewEvents>
    </SfPivotView>

    @code{
        public List<ProductDetails> data { get; set; }
        protected override void OnInitialized()
        {
            this.data = ProductDetails.GetProductData().ToList();
           //Bind the data source collection here. Refer "Assigning sample data to the pivot table" section in getting started for more details.
        }
        private void cellClick(CellClickEventArgs args)
        {
            args.CurrentCell.AddClass(new string[] { "e-test" });
        }
    }

```

## CellSelected

To know more about this event, refer [here](./row-and-column/#event).

## CellSelecting

The event [`CellSelecting`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.PivotViewEvents%601~CellSelecting.html) is triggered when cell selection is about to initiate in the Pivot Table. To use this event, [`AllowSelection`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.PivotViewGridSettings~AllowSelection.html) property in [`PivotViewGridSettings`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.PivotViewGridSettings.html) must be set to **true**. It has following parameters -  [`Cancel`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.PivotCellSelectedEventArgs~CurrentCell.html), [`CurrentCell`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.PivotCellSelectedEventArgs~CurrentCell.html), [`IsCellClick`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.PivotCellSelectedEventArgs~IsCellClick.html) and [`Data`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.PivotCellSelectedEventArgs~Data.html). For instance, using this event user can pass those selected cell information to any external component for data binding.

```csharp

    @using Syncfusion.Blazor.PivotView

    <SfPivotView TValue="ProductDetails">
        <PivotViewDataSourceSettings DataSource="@data">
            <PivotViewColumns>
                <PivotViewColumn Name="Year"></PivotViewColumn>
                <PivotViewColumn Name="Quarter"></PivotViewColumn>
            </PivotViewColumns>
            <PivotViewRows>
                <PivotViewRow Name="Country"></PivotViewRow>
                <PivotViewRow Name="Products"></PivotViewRow>
            </PivotViewRows>
            <PivotViewValues>
                <PivotViewValue Name="Sold" Caption="Unit Sold"></PivotViewValue>
                <PivotViewValue Name="Amount" Caption="Amount"></PivotViewValue>
            </PivotViewValues>
        </PivotViewDataSourceSettings>
        <PivotViewEvents TValue="ProductDetails" CellSelecting="cellSelecting"></PivotViewEvents>
    </SfPivotView>

    @code{
        public List<ProductDetails> data { get; set; }
        protected override void OnInitialized()
        {
            this.data = ProductDetails.GetProductData().ToList();
           //Bind the data source collection here. Refer "Assigning sample data to the pivot table" section in getting started for more details.
        }
        private void cellSelecting(PivotCellSelectedEventArgs args)
        {
            args.CurrentCell.AddClass(new string[] { "e-test" });
        }
    }

```

## ChartSeriesCreated

The event [`ChartSeriesCreated`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.PivotViewEvents%601~ChartSeriesCreated.html) is triggered once chart series are completely rendered. This event is triggered only when [`View`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.PivotViewDisplayOption~View.html) property in [`PivotViewDisplayOption`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.PivotViewDisplayOption.html) class is set to **Chart**.  It has following parameter - [`Cancel`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.ChartSeriesCreatedEventArgs~Cancel.html), and [`Series`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.ChartSeriesCreatedEventArgs~Series.html). When the parameter [`Cancel`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.ChartSeriesCreatedEventArgs~Cancel.html) is set to **true**, chart series rendered will be revoked.

```csharp

    @using Syncfusion.Blazor.PivotView

    <SfPivotView TValue="ProductDetails">
        <PivotViewDataSourceSettings DataSource="@data">
            <PivotViewColumns>
                <PivotViewColumn Name="Year"></PivotViewColumn>
                <PivotViewColumn Name="Quarter"></PivotViewColumn>
            </PivotViewColumns>
            <PivotViewRows>
                <PivotViewRow Name="Country"></PivotViewRow>
                <PivotViewRow Name="Products"></PivotViewRow>
            </PivotViewRows>
            <PivotViewValues>
                <PivotViewValue Name="Sold" Caption="Unit Sold"></PivotViewValue>
                <PivotViewValue Name="Amount" Caption="Amount"></PivotViewValue>
            </PivotViewValues>
        </PivotViewDataSourceSettings>
        <PivotViewDisplayOption View=View.Chart></PivotViewDisplayOption>
        <PivotViewEvents TValue="ProductDetails" ChartSeriesCreated="chartSeries"></PivotViewEvents>
    </SfPivotView>

    @code{
        public List<ProductDetails> data { get; set; }
        protected override void OnInitialized()
        {
            this.data = ProductDetails.GetProductData().ToList();
           //Bind the data source collection here. Refer "Assigning sample data to the pivot table" section in getting started for more details.
        }
        private void chartSeries(ChartSeriesCreatedEventArgs args)
        {
            args.Cancel = true;//chart series will not be rendered
        }
    }

```

## ConditionalFormatting

The event [`ConditionalFormatting`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.PivotViewEvents%601~ConditionalFormatting.html) is triggered initially while clicking the "ADD CONDITION" button inside the conditional formatting dialog in-order to fill user specific condition instead of default condition at runtime. To use this event, [`AllowConditionalFormatting`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.SfPivotView%601~AllowConditionalFormatting.html) property in [`SfPivotView`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.SfPivotView%601.html) class must be set to **true**. It has following parameters - [`ApplyGrandTotals`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.IConditionalFormatSettings~ApplyGrandTotals.html), [`Conditions`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.IConditionalFormatSettings~Conditions.html), [`Label`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.IConditionalFormatSettings~Label.html), [`Measure`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.IConditionalFormatSettings~Measure.html), [`Style`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.IConditionalFormatSettings~Style.html), [`Value1`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.IConditionalFormatSettings~Value1.html) and [`Value2`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.IConditionalFormatSettings~Value2.html).

```csharp

    @using Syncfusion.Blazor.PivotView

    <SfPivotView TValue="ProductDetails" AllowConditionalFormatting="true">
        <PivotViewDataSourceSettings DataSource="@data">
            <PivotViewColumns>
                <PivotViewColumn Name="Year"></PivotViewColumn>
                <PivotViewColumn Name="Quarter"></PivotViewColumn>
            </PivotViewColumns>
            <PivotViewRows>
                <PivotViewRow Name="Country"></PivotViewRow>
                <PivotViewRow Name="Products"></PivotViewRow>
            </PivotViewRows>
            <PivotViewValues>
                <PivotViewValue Name="Sold" Caption="Unit Sold"></PivotViewValue>
                <PivotViewValue Name="Amount" Caption="Amount"></PivotViewValue>
            </PivotViewValues>
        </PivotViewDataSourceSettings>
        <PivotViewEvents TValue="ProductDetails" ConditionalFormatting="conditionalFormat"></PivotViewEvents>
    </SfPivotView>

    @code{
        public List<ProductDetails> data { get; set; }
        protected override void OnInitialized()
        {
            this.data = ProductDetails.GetProductData().ToList();
           //Bind the data source collection here. Refer "Assigning sample data to the pivot table" section in getting started for more details.
        }
        private void conditionalFormat(CellClickEventArgs args)
        {
            //to change the conditional formatting settings in conditional format dialog
            args.Style.BackgroundColor = "Blue";
            args.Value1 = 23459;
        }
    }

```

## Drill

The event [`Drill`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.PivotViewEvents%601~Drill.html) is triggered whenever a member is expanded or collapsed in the Pivot Table. It has following parameters - [`DrillInfo`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.DrillArgs%601~DrillInfo.html) and [`PivotView`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.DrillArgs%601~Pivotview.html). For instance using this event user can alter delimiter and drill action for the respective item.

> In this event the parameter [`PivotView`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.DrillArgs%601~Pivotview.html) is returned as **null** due to its size.

```csharp

    @using Syncfusion.Blazor.PivotView

    <SfPivotView TValue="ProductDetails" AllowConditionalFormatting="true">
        <PivotViewDataSourceSettings DataSource="@data">
            <PivotViewColumns>
                <PivotViewColumn Name="Year"></PivotViewColumn>
                <PivotViewColumn Name="Quarter"></PivotViewColumn>
            </PivotViewColumns>
            <PivotViewRows>
                <PivotViewRow Name="Country"></PivotViewRow>
                <PivotViewRow Name="Products"></PivotViewRow>
            </PivotViewRows>
            <PivotViewValues>
                <PivotViewValue Name="Sold" Caption="Unit Sold"></PivotViewValue>
                <PivotViewValue Name="Amount" Caption="Amount"></PivotViewValue>
            </PivotViewValues>
        </PivotViewDataSourceSettings>
        <PivotViewEvents TValue="ProductDetails" Drill="drill"></PivotViewEvents>
    </SfPivotView>

    @code{
        public List<ProductDetails> data { get; set; }
        protected override void OnInitialized()
        {
            this.data = ProductDetails.GetProductData().ToList();
           //Bind the data source collection here. Refer "Assigning sample data to the pivot table" section in getting started for more details.
        }
        private void drill(DrillArgs<ProductDetails> args)
        {
            //args.DrillInfo --> in this user can get which field is drilled
            args.DrillInfo.Delimiter = "##";
            args.DrillInfo.Action = "up";
        }
    }

```

## DrillThrough

The event [`DrillThrough`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.PivotViewEvents%601~DrillThrough.html) is triggered when a value cell is clicked in the Pivot Table during drill through operation. It has following parameter - [`ColumnHeaders`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.DrillThroughEventArgs~ColumnHeaders.html), [`CurrentCell`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.DrillThroughEventArgs~CurrentCell.html), [`CurrentTarget`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.DrillThroughEventArgs~CurrentTarget.html), [`RawData`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.DrillThroughEventArgs~RawData.html), [`RowHeaders`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.DrillThroughEventArgs~RowHeaders.html) and [`Value`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.DrillThroughEventArgs~Value.html). This event allows user to view cell information like [`ColumnHeaders`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.DrillThroughEventArgs~ColumnHeaders.html), [`CurrentCell`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.DrillThroughEventArgs~CurrentCell.html), [`CurrentTarget`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.DrillThroughEventArgs~CurrentTarget.html), [`RawData`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.DrillThroughEventArgs~RawData.html), [`RowHeaders`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.DrillThroughEventArgs~RowHeaders.html) and [`Value`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.DrillThroughEventArgs~Value.html) for the appropriate cell in which drill through is performed. Exclusively the event helps to view and process the raw data information behind a aggregated value inside value cell.

```csharp

    @using Syncfusion.Blazor.PivotView

    <SfPivotView TValue="ProductDetails" AllowConditionalFormatting="true">
        <PivotViewDataSourceSettings DataSource="@data">
            <PivotViewColumns>
                <PivotViewColumn Name="Year"></PivotViewColumn>
                <PivotViewColumn Name="Quarter"></PivotViewColumn>
            </PivotViewColumns>
            <PivotViewRows>
                <PivotViewRow Name="Country"></PivotViewRow>
                <PivotViewRow Name="Products"></PivotViewRow>
            </PivotViewRows>
            <PivotViewValues>
                <PivotViewValue Name="Sold" Caption="Unit Sold"></PivotViewValue>
                <PivotViewValue Name="Amount" Caption="Amount"></PivotViewValue>
            </PivotViewValues>
        </PivotViewDataSourceSettings>
        <PivotViewEvents TValue="ProductDetails" DrillThrough="drillThrough"></PivotViewEvents>
    </SfPivotView>

    @code{
        public List<ProductDetails> data { get; set; }
        protected override void OnInitialized()
        {
            this.data = ProductDetails.GetProductData().ToList();
           //Bind the data source collection here. Refer "Assigning sample data to the pivot table" section in getting started for more details.
        }
        private void drillThrough(DrillThroughEventArgs args)
        {
            //args.CurrentCell --> in this user can get on which cell drillthrough is performed
        }
    }

```

## EnginePopulating

The [`EnginePopulating`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.PivotViewEvents%601~EnginePopulating.html) event is available in both Pivot Table and Field List.

* The event [`EnginePopulating`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.PivotFieldListEvents%601~EnginePopulating.html) is triggered from Field List object whenever the report gets modified in its UI.

* Likewise, [`EnginePopulating`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.PivotViewEvents%601~EnginePopulating.html) event is triggered from Pivot Table object whenever the report gets modified via grouping bar, toolbar, etc.

This event will be triggered before engine framing works gets initiated and allows user to customize the pivot datasource settings. It has following parameter - [`DataSourceSettings`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.EnginePopulatingEventArgs~DataSourceSettings.html).

```csharp

    @using Syncfusion.Blazor.PivotView

    <SfPivotView TValue="ProductDetails" AllowConditionalFormatting="true">
        <PivotViewDataSourceSettings DataSource="@data">
            <PivotViewColumns>
                <PivotViewColumn Name="Year"></PivotViewColumn>
                <PivotViewColumn Name="Quarter"></PivotViewColumn>
            </PivotViewColumns>
            <PivotViewRows>
                <PivotViewRow Name="Country"></PivotViewRow>
                <PivotViewRow Name="Products"></PivotViewRow>
            </PivotViewRows>
            <PivotViewValues>
                <PivotViewValue Name="Sold" Caption="Unit Sold"></PivotViewValue>
                <PivotViewValue Name="Amount" Caption="Amount"></PivotViewValue>
            </PivotViewValues>
        </PivotViewDataSourceSettings>
        <PivotViewEvents TValue="ProductDetails" EnginePopulating="enginePopulating"></PivotViewEvents>
    </SfPivotView>

    @code{
        public List<ProductDetails> data { get; set; }
        protected override void OnInitialized()
        {
            this.data = ProductDetails.GetProductData().ToList();
           //Bind the data source collection here. Refer "Assigning sample data to the pivot table" section in getting started for more details.
        }
        private void enginePopulating(EnginePopulatingEventArgs args)
        {
            //args.DataSourceSettings --> user can modify datasource settings before engine populates
        }
    }

```

## EnginePopulated

The [`EnginePopulated`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.PivotFieldListEvents%601~EnginePopulated.html) event is available in both Pivot Table and Field List. To know more about this event, refer [here](./field-list/#enginepopulated).

## FetchReport

To know more about this event, refer [here](./tool-bar/#fetchreport).

## FieldListRefreshed

To know more about this event, refer [here](./field-list/#field).

## FieldDragStart

To know more about this event, refer [here](./grouping-bar/#fielddragstart).

## FieldDrop

To know more about this event, refer [here](./grouping-bar/#fielddrop).

## FieldDropped

The [`FieldDropped`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.PivotFieldListEvents%601~FieldDropped.html) event is available in both Grouping Bar and Field List.

To know more about this event with respect to field list operation, refer [here](./field-list/#fielddropped).

To know more about this event with respect to grouping bar operation, refer [here](./grouping-bar/#fielddropped).

## FieldRemove

To know more about this event, refer [here](./grouping-bar/#fieldremove).

## HyperlinkCellClicked

To know more about this event, refer [here](./hyper-link/#event).

## LoadReport

To know more about this event, refer [here](./tool-bar/#loadreport).

## MemberEditorOpen

To know more about this event, refer [here](./filtering/#membereditoropen).

## NewReport

To know more about this event, refer [here](./tool-bar/#newreport).

## OnLoad

The [`OnLoad`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.PivotViewEvents%601~OnLoad.html) event is available in both Pivot Table and Field List.

To know more about this event, refer [here](./data-binding/#event).

## RenameReport

To know more about this event, refer [here](./tool-bar/#renamereport).

## RemoveReport

To know more about this event, refer [here](./tool-bar/#removereport).

## SaveReport

To know more about this event, refer [here](./tool-bar/#savereport).

## ToolbarRender

The event [`ToolbarRender`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.PivotViewEvents%601~ToolbarRendered.html) is triggered before rendering of toolbar. This event is available only when toolbar is enabled in the Pivot Table. It has following parameter - [`CustomToolbar`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.ToolbarArgs~CustomToolbar.html). Using this event user can add custom toolbar items as well as remove existing items from the toolbar.

```csharp
    @using Syncfusion.Blazor.PivotView

    <SfPivotView TValue="ProductDetails" ShowFieldList="true" ShowToolbar="true" Toolbar="@toolbar" AllowConditionalFormatting="true" AllowPdfExport="true" AllowExcelExport="true">
        <PivotViewDisplayOption Primary=Primary.Table View=View.Both></PivotViewDisplayOption>
            <PivotViewDataSourceSettings DataSource="@data" ShowGrandTotals="true" ShowSubTotals="true">
                <PivotViewColumns>
                    <PivotViewColumn Name="Year"></PivotViewColumn>
                    <PivotViewColumn Name="Quarter"></PivotViewColumn>
                </PivotViewColumns>
                <PivotViewRows>
                    <PivotViewRow Name="Country"></PivotViewRow>
                    <PivotViewRow Name="Products"></PivotViewRow>
                </PivotViewRows>
                <PivotViewValues>
                    <PivotViewValue Name="Sold" Caption="Units Sold"></PivotViewValue>
                    <PivotViewValue Name="Amount" Caption="Sold Amount"></PivotViewValue>
                </PivotViewValues>
                <PivotViewFormatSettings>
                    <PivotViewFormatSetting Name="Amount" Format="C"></PivotViewFormatSetting>
                </PivotViewFormatSettings>
            </PivotViewDataSourceSettings>
            <PivotViewEvents TValue="ProductDetails" ToolbarRendered="toolbarRender" RenameReport="renameReport" RemoveReport="removeReport" SaveReport="saveReport" LoadReport="loadReport" FetchReport="fetchReport" ></PivotViewEvents>
            <PivotViewGridSettings ColumnWidth="140"></PivotViewGridSettings>
    </SfPivotView>

    @code{
        public List<ToolbarItems> toolbar = new List<ToolbarItems> {
            ToolbarItems.New,
            ToolbarItems.Load,
            ToolbarItems.Remove,
            ToolbarItems.Rename,
            ToolbarItems.SaveAs,
            ToolbarItems.Save,
            ToolbarItems.Grid,
            ToolbarItems.Chart,
            ToolbarItems.Export,
            ToolbarItems.SubTotal,
            ToolbarItems.GrandTotal,
            ToolbarItems.ConditionalFormatting,
            ToolbarItems.FieldList
        };
        public List<ProductDetails> data { get; set; }
        protected override void OnInitialized()
        {
            this.data = ProductDetails.GetProductData().ToList();
           //Bind the data source collection here. Refer "Assigning sample data to the pivot table" section in getting started for more details.
        }
         public void toolbarRender(ToolbarArgs args)
        {
            //args.CustomToolbar -> user can add or remove toolbar items
        }
        public List<string> report = new List<string>();
        public List<string> reportName = new List<string>();
        //to save report
        public void saveReport(SaveReportArgs args)
        {
            var i = 0;
            bool isSaved = false;
            for (i = 0; i < this.reportName.Count; i++)
            {
                if (this.reportName[i] == args.ReportName)
                {
                    this.report[i] = args.Report;
                    isSaved = true;
                }
            }
            if (args.Report != null && !(isSaved))
            {
                this.report.Add(args.Report);
                this.reportName.Add(args.ReportName);
            }

        }
        //fetch reports
        public void fetchReport(FetchReportArgs args)
        {
            args.ReportName = this.reportName.ToArray();

        }
        //to load the selected report
        public void loadReport(LoadReportArgs args)
        {
            var i = 0;
            var j = 0;
            for (i = 0; i < this.reportName.Count; i++)
            {
                if (this.reportName[i] == args.ReportName)
                {
                    j = i;
                }
            }
            this.pivot.LoadPersistData(this.report[j]);
        }
        //to delete a report
        public void removereport(RemoveReportArgs args)
        {
            var i = 0;
            for( i=0;i<this.reportName.Count; i++)
            {
                if(this.reportName[i] == args.ReportName)
                {
                    this.reportName.RemoveAt(i);
                    this.report.RemoveAt(i);
                }
            }
        }
        // to rename a report
        public void renamereport(RenameReportArgs args)
        {
            var i = 0;
            for( i=0;i<=(this.reportName.Count - 1); i++)
            {
                if(this.reportName[i] == args.ReportName)
                {
                    this.reportName.RemoveAt(i);
                    this.reportName.Add(args.Rename);
                }
            }
        }
    }

```