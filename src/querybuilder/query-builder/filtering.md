---
title: "Filtering"
component: "Query Builder"
description: "Learn how to delete/create conditions and group"
---

# Filtering

Query Builder allows you to create or delete conditions and groups. You can use [`ShowButtons`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.QueryBuilder.SfQueryBuilder.html#Syncfusion_Blazor_QueryBuilder_SfQueryBuilder_ShowButtons) to enable/disable these buttons.

You can `create` or `delete` conditions by interacting through the user interface and methods.

Use the [`AddRules`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.QueryBuilder.SfQueryBuilder.html#Syncfusion_Blazor_QueryBuilder_SfQueryBuilder_AddRules_System_Object_System_String_), and [`DeleteRules`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.QueryBuilder.SfQueryBuilder.html#Syncfusion_Blazor_QueryBuilder_SfQueryBuilder_DeleteRules_System_Object_) methods to create/delete conditions.
Use [`AddGroups`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.QueryBuilder.SfQueryBuilder.html#Syncfusion_Blazor_QueryBuilder_SfQueryBuilder_AddGroups_System_Object_System_String_), and [`DeleteGroups`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.QueryBuilder.SfQueryBuilder.html#Syncfusion_Blazor_QueryBuilder_SfQueryBuilder_DeleteGroups_System_Object_) methods to create/delete groups.

```csharp

@using Syncfusion.Blazor.QueryBuilder
@using Syncfusion.Blazor.Buttons

<SfQueryBuilder Rule="@ImportRules" @ref="QuerybuilderObj">
                <QueryBuilderColumns>
                    <QueryBuilderColumn Field="EmployeeID" Label="Employee ID" Type="number"></QueryBuilderColumn>
                    <QueryBuilderColumn Field="FirstName" Label="First Name" Type="string"></QueryBuilderColumn>
                    <QueryBuilderColumn Field="TitleOfCourtesy" Label="Title Of Courtesy" Type="boolean"></QueryBuilderColumn>
                    <QueryBuilderColumn Field="HireDate" Label="Hire Date" Type="date" Format = "MM/dd/yyyy"></QueryBuilderColumn>
                    <QueryBuilderColumn Field="Country" Label="Country" Type="string"></QueryBuilderColumn>
                </QueryBuilderColumns>
</SfQueryBuilder>
<SfButton @onclick="addRule" IsPrimary="true" Content="Add Rules"></SfButton>
<SfButton @onclick="addGroup" IsPrimary="true" Content="Add Group"></SfButton>
<SfButton @onclick="deleteGroups" IsPrimary="true" Content="Delete Groups"></SfButton>

@code {
    SfQueryBuilder QuerybuilderObj;
    public QueryBuilderRule ImportRules = new QueryBuilderRule
    {
        Condition = "or",
        Rules = new List<RuleModel> { new RuleModel { Field = "EmployeeID", Value = "1001", Operator = "notequal" },
        new RuleModel { Field = "Country", Value = "England", Operator = "equal" } }
    };

    public List<RuleModel> Rules = new List<RuleModel> {
        new RuleModel{ Label = "Employee ID", Field = "EmployeeID", Type = "number", Operator = "equal", Value = "1091" }
    };

    public List<RuleModel> Groups = new List<RuleModel> {
        new RuleModel{ Condition = "or", Rules = new List<RuleModel>{
            new RuleModel { Label = "Employee ID", Field = "EmployeeID", Type = "number", Operator = "equal", Value = "1091" } } }

    };

    public string[] GroupID = new string[] {"group1"};

    private void addRule()
    {
        this.QuerybuilderObj.AddRules(Rules, "group0");
    }

    private void addGroup()
    {
        this.QuerybuilderObj.AddGroups(Groups, "group0");
    }

    private void deleteGroups()
    {
        this.QuerybuilderObj.DeleteGroups(GroupID);
    }
}

```

Output will be shown as

![Query Builder Sample](./images/qb-filtering.png)
