# Templates

This section explains the list of templates available in the Query Builder.

## Value Template

Template allows you to define your own widgets for value. Use the [`ValueTemplate`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.QueryBuilder.QueryBuilderTemplates.html#Syncfusion_Blazor_QueryBuilder_QueryBuilderTemplates_ValueTemplate), property to define templates.

```csharp
@using Syncfusion.Blazor.QueryBuilder
@using Syncfusion.Blazor.DropDowns

<div class="col-lg-12 control-section">
    <SfQueryBuilder TValue="ExpenseData" Width="100%" DataSource="@DataSource">
        <QueryBuilderRule Condition="and" Rules="@Rules"></QueryBuilderRule>
        <QueryBuilderColumns>
            <QueryBuilderColumn Field="PaymentMode" Label="PaymentMode" Type=Syncfusion.Blazor.QueryBuilder.ColumnType.String>
                <QueryBuilderTemplates>
                    <ValueTemplate>
                        <SfDropDownList TValue="string" TItem="ItemFields" DataSource="@Items" @bind-Value="@DefaultValue">
                            <DropDownListFieldSettings Text="Id"></DropDownListFieldSettings>
                            <DropDownListEvents TItem="ItemFields" TValue="string" ValueChange="e => OnChange(e, context)"></DropDownListEvents>
                        </SfDropDownList>
                    </ValueTemplate>
                </QueryBuilderTemplates>
            </QueryBuilderColumn>
            <QueryBuilderColumn Field="Category" Label="Category" Type=Syncfusion.Blazor.QueryBuilder.ColumnType.String></QueryBuilderColumn>
            <QueryBuilderColumn Field="Description" Label="Description" Type=ColumnType.String></QueryBuilderColumn>
            <QueryBuilderColumn Field="Amount" Label="Amount" Type=Syncfusion.Blazor.QueryBuilder.ColumnType.Number></QueryBuilderColumn>
        </QueryBuilderColumns>
    </SfQueryBuilder>
</div>
@code{
    public string DefaultValue = "Cash";
    public List<ExpenseData> DataSource;
    public class ExpenseData
    {
        public string Category { get; set; }
        public string PaymentMode { get; set; }
        public string Description { get; set; }
        public int Amount { get; set; }
    }
    protected override void OnInitialized()
    {
        DataSource = new List<ExpenseData>()
        {
            new ExpenseData() {Category= "Food", PaymentMode="Credit Card", Description="Boiled peanuts", Amount=100 },
            new ExpenseData() {Category= "Food", PaymentMode="Debit Card", Description="Boiled peanuts", Amount=200 },
            new ExpenseData() {Category= "Food", PaymentMode="Cash", Description="Confederate cush", Amount=300 },
            new ExpenseData() {Category= "Transportation", PaymentMode="Cash", Description="Public and other transportation", Amount=150 },
            new ExpenseData() {Category= "Transportation", PaymentMode="Debit Card", Description="Public and other transportation", Amount=250 }
        };
    }
    public class ItemFields
    {
        public string Id { get; set; }
    }
    public List<ItemFields> Items = new List<ItemFields>() {
        new ItemFields(){ Id= "Cash" },
        new ItemFields(){ Id= "Debit Card" },
        new ItemFields(){ Id= "Credit Card" },
        new ItemFields(){ Id= "Net Banking" }
    };
    public void OnChange(Syncfusion.Blazor.DropDowns.ChangeEventArgs<string, ItemFields> args, RuleModel Rule)
    {
        Rule.Value = args.Value;
    }
    List<RuleModel> Rules = new List<RuleModel>()
    {
        new RuleModel { Label="PaymentMode", Field="PaymentMode", Type="String", Operator="equal", Value="Debit Card" },
        new RuleModel { Label="Category", Field="Category", Type="String", Operator="equal", Value="Food" }
    };
}

```

Output will be shown as

![Query Builder Sample](./images/qb-value-template.png)

## Column Template

Column Template allows you to define your own widgets for entire column. Use the [`ColumnTemplate`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.QueryBuilder.QueryBuilderTemplates.html#Syncfusion_Blazor_QueryBuilder_QueryBuilderTemplates_ColumnTemplate) property to define templates.

In the following sample, the DropDownList component is used as the custom components for field and value in the `PaymentMode` column.

```csharp

@using Syncfusion.Blazor.QueryBuilder
@using Syncfusion.Blazor.DropDowns
@using Newtonsoft.Json

<div class="col-lg-12 control-section">
    <SfQueryBuilder TValue="ExpenseData" @ref="qb" DataSource="@DataSource" Width="75%">
        <QueryBuilderEvents TValue="ExpenseData" Created="UpdateContent" RuleChanged="UpdateContent"></QueryBuilderEvents>
        <QueryBuilderRule Condition="and" Rules="@Rules"></QueryBuilderRule>
        <QueryBuilderColumns>
            <QueryBuilderColumn Field="PaymentMode" Label="PaymentMode" Type=Syncfusion.Blazor.QueryBuilder.ColumnType.String>
                <QueryBuilderTemplates>
                    <ColumnTemplate>
                        <div class="e-field">
                            <SfDropDownList TItem="string" TValue="string" DataSource="qb.Columns.Select(e => e.Field)" @bind-Value="context.Label">
                                <DropDownListFieldSettings Text="PaymentMode"></DropDownListFieldSettings>
                                <DropDownListEvents TItem="string" TValue="string" Created="e => ValueCreated(context)" ValueChange="e => ChangeField(e, context)"></DropDownListEvents>
                            </SfDropDownList>
                        </div>
                        <div class="e-value-field">
                            <SfDropDownList TValue="string" TItem="ItemFields" DataSource="@Items" @bind-Value="@DefaultValue">
                                <DropDownListFieldSettings Text="Id"></DropDownListFieldSettings>
                                <DropDownListEvents TItem="ItemFields" TValue="string" ValueChange="e => ChangeValue(e, context)"></DropDownListEvents>
                            </SfDropDownList>
                        </div>
                    </ColumnTemplate>
                </QueryBuilderTemplates>
            </QueryBuilderColumn>
            <QueryBuilderColumn Field="Category" Label="Category" Type=Syncfusion.Blazor.QueryBuilder.ColumnType.String></QueryBuilderColumn>
            <QueryBuilderColumn Field="Description" Label="Description" Type=ColumnType.String></QueryBuilderColumn>
            <QueryBuilderColumn Field="Amount" Label="Amount" Type=Syncfusion.Blazor.QueryBuilder.ColumnType.Number></QueryBuilderColumn>
        </QueryBuilderColumns>
    </SfQueryBuilder>
</div>

<table class="col-lg-3">
    <tbody>
        <tr>
            <td colspan="2">
                <textarea id="table" readonly>@content</textarea>
            </td>
        </tr>
    </tbody>
</table>


@code {
    SfQueryBuilder<ExpenseData> qb;
    private string content;
    public List<ExpenseData> DataSource;
    public string DefaultValue = "Cash";

    public class ItemFields
    {
        public string Id { get; set; }
    }

    public List<ItemFields> Items = new List<ItemFields>() {
        new ItemFields(){ Id= "Cash" },
        new ItemFields(){ Id= "Debit Card" },
        new ItemFields(){ Id= "Credit Card" },
        new ItemFields(){ Id= "Net Banking" }
    };

    public void UpdateContent()
    {
        content = JsonConvert.SerializeObject(qb.GetValidRules(), Formatting.Indented, new JsonSerializerSettings
        {
            NullValueHandling = NullValueHandling.Ignore
        });
    }

    public void ValueCreated(RuleModel Rule)
    {
        Rule.Value = "Cash";
        UpdateContent();
    }

    public void ChangeValue(Syncfusion.Blazor.DropDowns.ChangeEventArgs<string, ItemFields> args, RuleModel Rule)
    {
        Rule.Value = args.Value;
        UpdateContent();
    }

    private void ChangeField(Syncfusion.Blazor.DropDowns.ChangeEventArgs<string, string> args, RuleModel Rule)
    {
        Rule.Field = args.Value;
        Rule.Label = args.Value;
        Rule.Operator = "equal";
        UpdateContent();
    }

    public class ExpenseData
    {
        public string Category { get; set; }
        public string PaymentMode { get; set; }
        public string Description { get; set; }
        public int Amount { get; set; }
    }
    protected override void OnInitialized()
    {
        DataSource = new List<ExpenseData>()
        {
            new ExpenseData() {Category= "Food", PaymentMode="Credit Card", Description="Boiled peanuts", Amount=100 },
            new ExpenseData() {Category= "Food", PaymentMode="Debit Card", Description="Boiled peanuts", Amount=200 },
            new ExpenseData() {Category= "Food", PaymentMode="Cash", Description="Confederate cush", Amount=300 },
            new ExpenseData() {Category= "Transportation", PaymentMode="Cash", Description="Public and other transportation", Amount=150 },
            new ExpenseData() {Category= "Transportation", PaymentMode="Debit Card", Description="Public and other transportation", Amount=250 }
        };
    }

    List<RuleModel> Rules = new List<RuleModel>()
    {
        new RuleModel { Label="PaymentMode", Field="PaymentMode", Type="String", Operator="equal", Value="Cash" }
    };
}

<style>
    .e-query-builder {
        margin: 0 auto;
        float: left;
    }
    .e-rule-field .e-field,
    .e-rule-field .e-value-field {
        display: inline-block;
    }
    .e-rule-field .e-value-field {
        padding-left: 20px;
    }

    #table {
        width: 110%;
        height: 500px;
        border: 1px solid grey;
        overflow: auto;
        font-family: monospace;
    }
</style>

```

Output will be shown as

![Query Builder Sample](./images/qb-column-template.png)