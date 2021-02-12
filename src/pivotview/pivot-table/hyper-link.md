---
component: "Pivot Table"
---

# Hyperlink

The pivot table supports to show hyperlink option to link data for individual cells that are displayed in the component. Also, the hyperlink can be enabled separately for row headers, column headers, value cells, and summary cells using the [`PivotViewHyperlinkSettings`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.PivotView.PivotViewHyperlinkSettings.html) class. It can be configured through code behind, during initial rendering and the settings available to show hyperlink are:

* [`ShowHyperlink`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.PivotView.PivotViewHyperlinkSettings.html#Syncfusion_Blazor_PivotView_PivotViewHyperlinkSettings_ShowHyperlink): It allows to set the visibility of hyperlink in all cells.
* [`ShowRowHeaderHyperlink`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.PivotView.PivotViewHyperlinkSettings.html#Syncfusion_Blazor_PivotView_PivotViewHyperlinkSettings_ShowRowHeaderHyperlink): It allows to set the visibility of hyperlink in row headers.
* [`ShowColumnHeaderHyperlink`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.PivotView.PivotViewHyperlinkSettings.html#Syncfusion_Blazor_PivotView_PivotViewHyperlinkSettings_ShowColumnHeaderHyperlink): It allows to set the visibility of hyperlink in column headers.
* [`ShowValueCellHyperlink`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.PivotView.PivotViewHyperlinkSettings.html#Syncfusion_Blazor_PivotView_PivotViewHyperlinkSettings_ShowValueCellHyperlink): It allows to set the visibility of hyperlink in value cells.
* [`ShowSummaryCellHyperlink`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.PivotView.PivotViewHyperlinkSettings.html#Syncfusion_Blazor_PivotView_PivotViewHyperlinkSettings_ShowSummaryCellHyperlink): It allows to set the visibility of hyperlink in summary cells.
* [`HeaderText`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.PivotView.PivotViewHyperlinkSettings.html#Syncfusion_Blazor_PivotView_PivotViewHyperlinkSettings_HeaderText): It allows to set the visibility of hyperlink based on header text.
* [`ConditionalSettings`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.PivotView.PivotViewConditionalSetting.html): It allows to set the visibility of hyperlink based on specific condition.

<!-- markdownlint-disable MD028 -->
> By default, the hyperlink options are disabled for all cells in the pivot table.

> User defined style can be applied to hyperlink using [`CssClass`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.PivotView.PivotViewHyperlinkSettings.html#Syncfusion_Blazor_PivotView_PivotViewHyperlinkSettings_CssClass) property in [`PivotViewHyperlinkSettings`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.PivotView.PivotViewHyperlinkSettings.html) class.

## Hyperlink for all cells

The pivot table has an option to show hyperlink option for all cells that are currently in display. To do so, user need to set [`ShowHyperlink`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.PivotView.PivotViewHyperlinkSettings.html#Syncfusion_Blazor_PivotView_PivotViewHyperlinkSettings_ShowHyperlink) to **true**.

```csharp
    @using Syncfusion.Blazor.PivotView

    <SfPivotView TValue="ProductDetails" ShowFieldList="true">
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
                <PivotViewValue Name="Amount" Caption="Sold Amount"></PivotViewValue>
            </PivotViewValues>
             <PivotViewFormatSettings>
                <PivotViewFormatSetting Name="Amount" Format="C"></PivotViewFormatSetting>
            </PivotViewFormatSettings>
        </PivotViewDataSourceSettings>
        <PivotViewHyperlinkSettings ShowHyperlink="true" CssClass="e-custom-class">
        </PivotViewHyperlinkSettings>
    </SfPivotView>

<style>
    .e-custom-class,.e-custom-class:hover {
        text-decoration: underline !important;
        color: blue !important;
    }
    .e-custom-class:hover {
        color: red !important;
    }
</style>
    @code{
        public List<ProductDetails> data { get; set; }
        protected override void OnInitialized()
        {
            this.data = ProductDetails.GetProductData().ToList();
           //Bind the data source collection here. Refer "Assigning sample data to the pivot table" section in getting started for more details.
        }
    }
```

![output](images/hyperlink.png)

## Hyperlink for row headers

The pivot table has an option to show hyperlink option for row header cells alone that are currently in display. To do so, user need to set [`ShowRowHeaderHyperlink`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.PivotView.PivotViewHyperlinkSettings.html#Syncfusion_Blazor_PivotView_PivotViewHyperlinkSettings_ShowRowHeaderHyperlink) to **true**.

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
                <PivotViewValue Name="Amount" Caption="Sold Amount"></PivotViewValue>
            </PivotViewValues>
             <PivotViewFormatSettings>
                <PivotViewFormatSetting Name="Amount" Format="C"></PivotViewFormatSetting>
            </PivotViewFormatSettings>
        </PivotViewDataSourceSettings>
        <PivotViewHyperlinkSettings ShowRowHeaderHyperlink="true" CssClass="e-custom-class">
        </PivotViewHyperlinkSettings>
    </SfPivotView>

<style>
    .e-custom-class,.e-custom-class:hover {
        text-decoration: underline !important;
        color: blue !important;
    }
    .e-custom-class:hover {
        color: red !important;
    }
</style>
    @code{
        public List<ProductDetails> data { get; set; }
        protected override void OnInitialized()
        {
            this.data = ProductDetails.GetProductData().ToList();
           //Bind the data source collection here. Refer "Assigning sample data to the pivot table" section in getting started for more details.
        }
    }
```

![output](images/hyperlink-rowheader.png)

## Hyperlink for column headers

The pivot table has an option to show hyperlink option for column header cells alone that are currently in display. To do so, user need to set [`ShowColumnHeaderHyperlink`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.PivotView.PivotViewHyperlinkSettings.html#Syncfusion_Blazor_PivotView_PivotViewHyperlinkSettings_ShowColumnHeaderHyperlink) to **true**.

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
                <PivotViewValue Name="Amount" Caption="Sold Amount"></PivotViewValue>
            </PivotViewValues>
            <PivotViewFormatSettings>
                <PivotViewFormatSetting Name="Amount" Format="C"></PivotViewFormatSetting>
            </PivotViewFormatSettings>
        </PivotViewDataSourceSettings>
            <PivotViewHyperlinkSettings ShowColumnHeaderHyperlink="true" CssClass="e-custom-class">
            </PivotViewHyperlinkSettings>
    </SfPivotView>

<style>
    .e-custom-class,.e-custom-class:hover {
        text-decoration: underline !important;
        color: blue !important;
    }
    .e-custom-class:hover {
        color: red !important;
    }
</style>
    @code{
        public List<ProductDetails> data { get; set; }
        protected override void OnInitialized()
        {
            this.data = ProductDetails.GetProductData().ToList();
           //Bind the data source collection here. Refer "Assigning sample data to the pivot table" section in getting started for more details.
        }
    }
```

![output](images/hyperlink-columnheader.png)

## Hyperlink for value cells

The pivot table has an option to show hyperlink option for value cells alone that are currently in display. To do so, user need to set [`ShowValueCellHyperlink`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.PivotView.PivotViewHyperlinkSettings.html#Syncfusion_Blazor_PivotView_PivotViewHyperlinkSettings_ShowValueCellHyperlink) to **true**.

```csharp
    @using Syncfusion.Blazor.PivotView

    <SfPivotView TValue="ProductDetails">
        <PivotViewDataSourceSettings DataSource="@data" ExpandAll="true">
            <PivotViewColumns>
                <PivotViewColumn Name="Year"></PivotViewColumn>
                <PivotViewColumn Name="Quarter"></PivotViewColumn>
            </PivotViewColumns>
            <PivotViewRows>
                <PivotViewRow Name="Country"></PivotViewRow>
                <PivotViewRow Name="Products"></PivotViewRow>
            </PivotViewRows>
            <PivotViewValues>
                <PivotViewValue Name="Amount" Caption="Sold Amount"></PivotViewValue>
            </PivotViewValues>
             <PivotViewFormatSettings>
                <PivotViewFormatSetting Name="Amount" Format="C"></PivotViewFormatSetting>
            </PivotViewFormatSettings>
        </PivotViewDataSourceSettings>
            <PivotViewHyperlinkSettings ShowValueCellHyperlink="true" CssClass="e-custom-class">
            </PivotViewHyperlinkSettings>
    </SfPivotView>

<style>
    .e-custom-class,.e-custom-class:hover {
        text-decoration: underline !important;
        color: blue !important;
    }
    .e-custom-class:hover {
        color: red !important;
    }
</style>
    @code{
        public List<PivotViewData.DefaultData> data { get; set; }
        protected override void OnInitialized()
        {
            this.data = PivotViewData.GetDefaultData().ToList();
           //Bind the data source collection here. Refer "Assigning sample data to the pivot table" section in getting started for more details.
        }
    }
```

![output](images/hyperlink-value.png)

## Hyperlink for summary cells

The pivot table has an option to show hyperlink option for summary cells alone that are currently in display. To do so, user need to set [`ShowSummaryCellHyperlink`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.PivotView.PivotViewHyperlinkSettings.html#Syncfusion_Blazor_PivotView_PivotViewHyperlinkSettings_ShowSummaryCellHyperlink) to **true**.

```csharp
    @using Syncfusion.Blazor.PivotView

    <SfPivotView TValue="ProductDetails">
        <PivotViewDataSourceSettings DataSource="@data" ExpandAll="true">
            <PivotViewColumns>
                <PivotViewColumn Name="Year"></PivotViewColumn>
                <PivotViewColumn Name="Quarter"></PivotViewColumn>
            </PivotViewColumns>
            <PivotViewRows>
                <PivotViewRow Name="Country"></PivotViewRow>
                <PivotViewRow Name="Products"></PivotViewRow>
            </PivotViewRows>
            <PivotViewValues>
                <PivotViewValue Name="Amount" Caption="Sold Amount"></PivotViewValue>
            </PivotViewValues>
             <PivotViewFormatSettings>
                <PivotViewFormatSetting Name="Amount" Format="C"></PivotViewFormatSetting>
            </PivotViewFormatSettings>
        </PivotViewDataSourceSettings>
            <PivotViewHyperlinkSettings ShowSummaryCellHyperlink="true" CssClass="e-custom-class">
            </PivotViewHyperlinkSettings>
    </SfPivotView>

<style>
    .e-custom-class,.e-custom-class:hover {
        text-decoration: underline !important;
        color: blue !important;
    }
    .e-custom-class:hover {
        color: red !important;
    }
</style>
    @code{
        public List<PivotViewData.DefaultData> data { get; set; }
        protected override void OnInitialized()
        {
            this.data = PivotViewData.GetDefaultData().ToList();
           //Bind the data source collection here. Refer "Assigning sample data to the pivot table" section in getting started for more details.
        }
    }
```

![output](images/hyperlink-summary.png)

## Condition based hyperlink

The pivot table has an option to show hyperlink in the cells based on specific conditions. It can be configured using the [`PivotViewConditionalSettings`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.PivotView.PivotViewConditionalSetting.html) class through code behind, during initial rendering. The settings required are:

* [`Measure`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.PivotView.PivotViewConditionalSetting.html#Syncfusion_Blazor_PivotView_PivotViewConditionalSetting_Measure): Specifies the value field name, in-order to set the visibility of hyperlink for the same when condition is met.
* [`Conditions`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.PivotView.PivotViewConditionalSetting.html#Syncfusion_Blazor_PivotView_PivotViewConditionalSetting_Conditions): Specifies the operator type such as [**Condition.Equals**](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.PivotView.Condition.html), [**Condition.GreaterThan**](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.PivotView.Condition.html), [**Condition.LessThan**](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.PivotView.Condition.html), etc.
* [`Value1`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.PivotView.PivotViewConditionalSetting.html#Syncfusion_Blazor_PivotView_PivotViewConditionalSetting_Value1): Specifies the start value.
* [`Value2`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.PivotView.PivotViewConditionalSetting.html#Syncfusion_Blazor_PivotView_PivotViewConditionalSetting_Value2): Specifies the end value.

```csharp
    @using Syncfusion.Blazor.PivotView

    <SfPivotView TValue="ProductDetails">
        <PivotViewDataSourceSettings DataSource="@data" ExpandAll="true">
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
        <PivotViewHyperlinkSettings CssClass="e-custom-class">
            <PivotViewConditionalSettings>
                <PivotViewConditionalSetting Measure="Sold" Conditions=Condition.Between Value1="100" Value2="200"></PivotViewConditionalSetting>
            </PivotViewConditionalSettings>
        </PivotViewHyperlinkSettings>
    </SfPivotView>

<style>
    .e-custom-class,.e-custom-class:hover {
        text-decoration: underline !important;
        color: blue !important;
    }
    .e-custom-class:hover {
        color: red !important;
    }
</style>
    @code{
        public List<PivotViewData.DefaultData> data { get; set; }
        protected override void OnInitialized()
        {
            this.data = PivotViewData.GetDefaultData().ToList();
           //Bind the data source collection here. Refer "Assigning sample data to the pivot table" section in getting started for more details.
        }
    }
```

![output](images/hyperlink-condition.png)

## Header based hyperlink

The pivot table has an option to show hyperlink in the cells based on specific row or column header. It can be configured using the [`HeaderText`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.PivotView.PivotViewHyperlinkSettings.html#Syncfusion_Blazor_PivotView_PivotViewHyperlinkSettings_HeaderText) option through code behind, during initial rendering.

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
                <PivotViewValue Name="Amount" Caption="Sold Amount"></PivotViewValue>
            </PivotViewValues>
             <PivotViewFormatSettings>
                <PivotViewFormatSetting Name="Amount" Format="C"></PivotViewFormatSetting>
            </PivotViewFormatSettings>
        </PivotViewDataSourceSettings>
        <PivotViewHyperlinkSettings HeaderText="FY 2015" CssClass="e-custom-class"></PivotViewHyperlinkSettings>
    </SfPivotView>

<style>
   .e-custom-class,.e-custom-class:hover {
        text-decoration: underline !important;
        color: blue !important;
    }
    .e-custom-class:hover {
        color: red !important;
    }
</style>

    @code{
        public List<PivotViewData.DefaultData> data { get; set; }
        protected override void OnInitialized()
        {
            this.data = PivotViewData.GetDefaultData().ToList();
           //Bind the data source collection here. Refer "Assigning sample data to the pivot table" section in getting started for more details.
        }
    }
```

![output](images/hyperlink-header.png)

## Event

The event [`HyperlinkCellClicked`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.PivotView.PivotViewEvents-1.html#Syncfusion_Blazor_PivotView_PivotViewEvents_1_HyperlinkCellClicked) fires on every hyperlink cell click.

It has following parameters - [`Cancel`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.PivotView.HyperCellClickEventArgs.html#Syncfusion_Blazor_PivotView_HyperCellClickEventArgs_Cancel) and [`CurrentCell`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.PivotView.HyperCellClickEventArgs.html#Syncfusion_Blazor_PivotView_HyperCellClickEventArgs_CurrentCell). The parameter [`CurrentCell`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.PivotView.HyperCellClickEventArgs.html#Syncfusion_Blazor_PivotView_HyperCellClickEventArgs_CurrentCell) is used to customize the host cell element by any means. Meanwhile, when the parameter [`Cancel`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.PivotView.HyperCellClickEventArgs.html#Syncfusion_Blazor_PivotView_HyperCellClickEventArgs_Cancel) is set to **true**, applied customization will not be updated to the host cell element.

```csharp
    @using Syncfusion.Blazor.PivotView

    <SfPivotView TValue="ProductDetails" ShowFieldList="true">
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
                <PivotViewValue Name="Amount" Caption="Sold Amount"></PivotViewValue>
            </PivotViewValues>
        </PivotViewDataSourceSettings>
        <PivotViewHyperlinkSettings ShowHyperlink="true" CssClass="e-custom-class">
        </PivotViewHyperlinkSettings>
        <PivotViewEvents TValue="ProductDetails"  HyperlinkCellClicked="hyperlink"></PivotViewEvents>
    </SfPivotView>

<style>
    .e-custom-class,.e-custom-class:hover {
        text-decoration: underline !important;
        color: blue !important;
    }
    .e-custom-class:hover {
        color: red !important;
    }
</style>
    @code{
        public List<ProductDetails> data { get; set; }
        protected override void OnInitialized()
        {
            this.data = ProductDetails.GetProductData().ToList();
           //Bind the data source collection here. Refer "Assigning sample data to the pivot table" section in getting started for more details.
        }
        public void hyperlink(HyperCellClickEventArgs args)
        {
            args.CurrentCell.SetAttribute("data-url", "https://syncfusion.com/");//here we have redirected to Syncfusion on hyperlinkcell click
        }
    }
```