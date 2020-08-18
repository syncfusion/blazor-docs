---
title: "Defer Layout Update"
component: "Pivot Table"
description: "Defer update allows users to update the pivot table only on demand."
---
<!-- markdownlint-disable MD012 -->

# Defer Layout Update

Defer layout update support allows to update the pivot table component only on demand. On enabling this feature, end user can drag-and-drop fields between row, column, value and filter axes, apply sorting and filtering inside the Field List, resulting in change of pivot report alone but not the pivot table values. Once all operations are performed and on clicking the "Apply" button in the Field List, pivot table will start to update with the last modified report. This also helps in bringing better performance in pivot table component rendering.

The field list can be displayed in two different formats to interact with pivot table. They are:

* **In-built Field List (Popup)**: To display the field list icon in pivot table UI to invoke the built-in dialog.
* **Stand-alone Field List (Fixed)**: To display the field list in a static position within a web page.

## In-built Field List (Popup)

To enable deferred updates in the pivot table, set the property [`AllowDeferLayoutUpdate`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.SfPivotView%601~AllowDeferLayoutUpdate.html) in [`SfPivotView`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.SfPivotView%601.html) as **true**. To make a note, the defer update option can be controlled only via Field List during runtime.

```csharp
    @using Syncfusion.Blazor.PivotView

    <SfPivotView TValue="ProductDetails" ShowFieldList="true" AllowDeferLayoutUpdate="true">
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
                <PivotViewValue Name="Amount" Caption="Sold Amount"></PivotViewValue>
            </PivotViewValues>
            <PivotViewFormatSettings>
                <PivotViewFormatSetting Name="Amount" Format="C"></PivotViewFormatSetting>
            </PivotViewFormatSettings>
        </PivotViewDataSourceSettings>
    </SfPivotvotView>

    @code{
        public List<ProductDetails> data { get; set; }
        protected override void OnInitialized()
        {
            this.data = ProductDetails.GetProductData().ToList();
           //Bind the data source collection here. Refer "Assigning sample data to the pivot table" section in getting started for more details.
        }
    }

```

![output](images/fieldlist_deferupdate.png)

## Stand-alone Field List (Fixed)

The field list can be rendered in a static position, anywhere in web page layout, like a separate component. To do so, you need to set [`RenderMode`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.SfPivotFieldList~RenderMode.html) property to [**Mode.Fixed**](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.Mode.html) in [`SfPivotFieldList`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.SfPivotFieldList%601_members.html).

To enable deferred updates in the static fieldlist, set the property [`AllowDeferLayoutUpdate`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.SfPivotFieldList~AllowDeferLayoutUpdate.html) in [`SfPivotFieldlist`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.SfPivotFieldList%601_members.html) as **true**. To make a note, the defer update option can be controlled only via Field List during runtime.

> To make field list interact with pivot table, you need to use the **UpdateView** and **Update** methods for data source update in both field list and pivot table simultaneously.


```csharp
        <SfPivotView TValue="ProductDetails" ID="pivotview"  @ref="pivotView" AllowDeferLayoutUpdate="true" Height="530">
            <PivotViewEvents TValue="ProductDetails" EnginePopulated="pivotenginepopulated"></PivotViewEvents>
        </SfPivotView>
        <SfPivotFieldList TValue="ProductDetails" ID="fieldlist" @ref="fieldList" RenderMode="Mode.Fixed" AllowDeferLayoutUpdate="true">
            <PivotFieldListDataSourceSettings DataSource="@data" EnableSorting=true>
                <PivotFieldListColumns>
                    <PivotFieldListColumn Name="Year"></PivotFieldListColumn>
                    <PivotFieldListColumn Name="Quarter"></PivotFieldListColumn>
                </PivotFieldListColumns>
                <PivotFieldListRows>
                    <PivotFieldListRow Name="Country"></PivotFieldListRow>
                    <PivotFieldListRow Name="Products"></PivotFieldListRow>
                </PivotFieldListRows>
                <PivotFieldListValues>
                    <PivotFieldListValue Name="Sold" Caption="Unit Sold"></PivotFieldListValue>
                    <PivotFieldListValue Name="Amount" Caption="Sold Amount"></PivotFieldListValue>
                </PivotFieldListValues>
            </PivotFieldListDataSourceSettings>
            <PivotFieldListEvents TValue="ProductDetails" EnginePopulated="enginepopulated"></PivotFieldListEvents>
        </SfPivotFieldList>
        <style>
            #fieldlist {
                width: 42%;
                height: 100%;
                float: right;
            }

            #pivotview {
                width: 57%;
                height: 530px;
                float: left;
            }
        </style>
        @code{
            SfPivotFieldList<ProductDetails> fieldList;
            SfPivotView<ProductDetails> pivotView;
            public List<ProductDetails> data { get; set; }
            protected override void OnInitialized()
            {
                this.data = ProductDetails.GetProductData();
            }

            public void pivotenginepopulated(EnginePopulatedEventArgs args)
            {
                this.fieldList.Update(this.pivotView);
            }
            public void enginepopulated(EnginePopulatedEventArgs args)
            {
                this.fieldList.UpdateView(this.pivotView);
            }
        }

```

![output](images/defer-update-static.png)