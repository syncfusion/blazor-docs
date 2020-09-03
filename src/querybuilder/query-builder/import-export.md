---
title: "Import and Export"
component: "Query Builder"
description: "Learn how to import end export the rules in the Blazor Query Builder control."
---

# Importing

Importing allows you to view or edit the predefined conditions which is available in JSON or SQL. You can import the conditions either initial rendering or post rendering.

## Initial rendering

To apply conditions initially, you can define the [`Rule`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.QueryBuilder.SfQueryBuilder.html#Syncfusion_Blazor_QueryBuilder_SfQueryBuilder_Rule). Here, you can import structured JSON object by defining the [`Rule`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.QueryBuilder.SfQueryBuilder.html#Syncfusion_Blazor_QueryBuilder_SfQueryBuilder_Rule) property.

```csharp

@using Syncfusion.Blazor.QueryBuilder

<SfQueryBuilder DataSource="@EmployeeDetails" Rule="@ImportRules" @ref="QueryBuilderObj">
                <QueryBuilderColumns>
                    <QueryBuilderColumn Field="EmployeeID" Label="Employee ID" Type="number"></QueryBuilderColumn>
                    <QueryBuilderColumn Field="FirstName" Label="First Name" Type="string"></QueryBuilderColumn>
                    <QueryBuilderColumn Field="TitleOfCourtesy" Label="Title Of Courtesy" Type="boolean"></QueryBuilderColumn>
                    <QueryBuilderColumn Field="HireDate" Label="Hire Date" Type="date"></QueryBuilderColumn>
                    <QueryBuilderColumn Field="Country" Label="Country" Type="string"></QueryBuilderColumn>
                    <QueryBuilderColumn Field="City" Label="City" Type="string"></QueryBuilderColumn>
                </QueryBuilderColumns>
            </SfQueryBuilder>

@code {
    SfQueryBuilder QueryBuilderObj;
    public List<Employee> EmployeeDetails = new List<Employee>
        {
        new Employee{ FirstName = "Martin", EmployeeID = "1001", Country = "England", City = "Manchester", HireDate = "23/04/2014" },
        new Employee{ FirstName = "Benjamin", EmployeeID = "1002", Country = "England", City = "Birmingham", HireDate = "19/06/2014" },
        new Employee{ FirstName = "Stuart", EmployeeID = "1003", Country = "England", City = "London", HireDate = "04/07/2014"},
        new Employee{ FirstName = "Ben", EmployeeID = "1004", Country = "USA", City = "California", HireDate = "15/08/2014" },
        new Employee{ FirstName = "Joseph", EmployeeID = "1005", Country = "Spain", City = "Madrid", HireDate = "29/08/2014" }
    };

    public class Employee {
        public string FirstName { get; set; }
        public string EmployeeID { get; set; }
        public string Country { get; set; }
        public string City { get; set; }
        public string HireDate { get; set; }
    }

    public QueryBuilderRule ImportRules = new QueryBuilderRule
    {
        Condition = "or",
        Rules = new List<RuleModel> {
            new RuleModel { Field = "EmployeeID", Value = "1001", Operator = "notequal" },
            new RuleModel { Field = "Country", Value = "England", Operator = "equal" }
        }
    };
}
```

Output will be shown as

![Query Builder Sample](./images/qb-databinding.png)

## Post rendering

### Importing from JSON

You can set the conditions from structured JSON object through the [`SetRules`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.QueryBuilder.SfQueryBuilder.html#Syncfusion_Blazor_QueryBuilder_SfQueryBuilder_SetRules_Syncfusion_Blazor_QueryBuilder_RuleModel_) method.

```csharp
@using Syncfusion.Blazor.QueryBuilder
@using Syncfusion.Blazor.Buttons

<SfQueryBuilder DataSource="@EmployeeDetails"  @ref="QueryBuilderObj">
                <QueryBuilderColumns>
                    <QueryBuilderColumn Field="EmployeeID" Label="Employee ID" Type="number"></QueryBuilderColumn>
                    <QueryBuilderColumn Field="FirstName" Label="First Name" Type="string"></QueryBuilderColumn>
                    <QueryBuilderColumn Field="TitleOfCourtesy" Label="Title Of Courtesy" Type="boolean"></QueryBuilderColumn>
                    <QueryBuilderColumn Field="HireDate" Label="Hire Date" Type="date"></QueryBuilderColumn>
                    <QueryBuilderColumn Field="Country" Label="Country" Type="string"></QueryBuilderColumn>
                    <QueryBuilderColumn Field="City" Label="City" Type="string"></QueryBuilderColumn>
                </QueryBuilderColumns>
            </SfQueryBuilder>
<SfButton CssClass="e-primary" @onclick="setRules">Set Rules</SfButton>

@code {
SfQueryBuilder QueryBuilderObj;
    public List<Employee> EmployeeDetails = new List<Employee>
        {
        new Employee{ FirstName = "Martin", EmployeeID = "1001", Country = "England", City = "Manchester", HireDate = "23/04/2014" },
        new Employee{ FirstName = "Benjamin", EmployeeID = "1002", Country = "England", City = "Birmingham", HireDate = "19/06/2014" },
        new Employee{ FirstName = "Stuart", EmployeeID = "1003", Country = "England", City = "London", HireDate = "04/07/2014"},
        new Employee{ FirstName = "Ben", EmployeeID = "1004", Country = "USA", City = "California", HireDate = "15/08/2014" },
        new Employee{ FirstName = "Joseph", EmployeeID = "1005", Country = "Spain", City = "Madrid", HireDate = "29/08/2014" }
    };

    public class Employee {
        public string FirstName { get; set; }
        public string EmployeeID { get; set; }
        public string Country { get; set; }
        public string City { get; set; }
        public string HireDate { get; set; }
    }

public RuleModel ImportRules = new RuleModel
{
    Condition = "or",
    Rules = new List<RuleModel>{
        new RuleModel { Field = "EmployeeID", Value = "1001", Operator = "notequal" },
        new RuleModel { Field = "Country", Value = "England", Operator = "equal" }
    }
};

private void setRules()
    {
        QueryBuilderObj.SetRules(ImportRules);
    }
}

```

Output will be shown as

![Query Builder Sample](./images/qb-setrules.png)

### Importing from SQL

You can set the conditions from SQL query through the [`SetRulesFromSql`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.QueryBuilder.SfQueryBuilder.html#Syncfusion_Blazor_QueryBuilder_SfQueryBuilder_SetRulesFromSql_System_String_) method.

```csharp
@using Syncfusion.Blazor.QueryBuilder
@using Syncfusion.Blazor.Buttons

<SfQueryBuilder DataSource="@EmployeeDetails" @ref="QueryBuilderObj">
                <QueryBuilderColumns>
                    <QueryBuilderColumn Field="EmployeeID" Label="Employee ID" Type="number"></QueryBuilderColumn>
                    <QueryBuilderColumn Field="FirstName" Label="First Name" Type="string"></QueryBuilderColumn>
                    <QueryBuilderColumn Field="TitleOfCourtesy" Label="Title Of Courtesy" Type="boolean"></QueryBuilderColumn>
                    <QueryBuilderColumn Field="HireDate" Label="Hire Date" Type="date"></QueryBuilderColumn>
                    <QueryBuilderColumn Field="Country" Label="Country" Type="string"></QueryBuilderColumn>
                    <QueryBuilderColumn Field="City" Label="City" Type="string"></QueryBuilderColumn>
                </QueryBuilderColumns>
</SfQueryBuilder>
<SfButton CssClass="e-primary" @onclick="setRules">Set Rules</SfButton>

@code {
SfQueryBuilder QueryBuilderObj;
public List<Employee> EmployeeDetails = new List<Employee>
        {
        new Employee{ FirstName = "Martin", EmployeeID = "1001", Country = "England", City = "Manchester", HireDate = "23/04/2014" },
        new Employee{ FirstName = "Benjamin", EmployeeID = "1002", Country = "England", City = "Birmingham", HireDate = "19/06/2014" },
        new Employee{ FirstName = "Stuart", EmployeeID = "1003", Country = "England", City = "London", HireDate = "04/07/2014"},
        new Employee{ FirstName = "Ben", EmployeeID = "1004", Country = "USA", City = "California", HireDate = "15/08/2014" },
        new Employee{ FirstName = "Joseph", EmployeeID = "1005", Country = "Spain", City = "Madrid", HireDate = "29/08/2014" }
    };

    public class Employee {
        public string FirstName { get; set; }
        public string EmployeeID { get; set; }
        public string Country { get; set; }
        public string City { get; set; }
        public string HireDate { get; set; }
    }

private void setRules()
    {
        QueryBuilderObj.SetRulesFromSql("EmployeeID = 1001 and City LIKE ('%Manchester')");
    }
}
```

Output will be shown as

![Query Builder Sample](./images/qb-sql.png)

# Exporting

Exporting allows you to save or maintain the created conditions through the Query Builder. You can export the defined conditions by the following ways.

## Exporting to JSON

You can export the defined conditions to structured JSON object through the [`GetValidRules`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.QueryBuilder.SfQueryBuilder.html#Syncfusion_Blazor_QueryBuilder_SfQueryBuilder_GetValidRules_Syncfusion_Blazor_QueryBuilder_RuleModel_) method.

## Exporting to SQL

You can export the defined conditions to SQL query through the [`GetRulesFromSql`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.QueryBuilder.SfQueryBuilder.html#Syncfusion_Blazor_QueryBuilder_SfQueryBuilder_GetRulesFromSql_System_String_) method.

```csharp
@using Syncfusion.Blazor.QueryBuilder
@using Syncfusion.Blazor.Buttons

<SfQueryBuilder DataSource="@EmployeeDetails" Rule="@ImportRules" @ref="QueryBuilderObj">
                <QueryBuilderColumns>
                    <QueryBuilderColumn Field="EmployeeID" Label="Employee ID" Type="number"></QueryBuilderColumn>
                    <QueryBuilderColumn Field="FirstName" Label="First Name" Type="string"></QueryBuilderColumn>
                    <QueryBuilderColumn Field="TitleOfCourtesy" Label="Title Of Courtesy" Type="boolean"></QueryBuilderColumn>
                    <QueryBuilderColumn Field="HireDate" Label="Hire Date" Type="date"></QueryBuilderColumn>
                    <QueryBuilderColumn Field="Country" Label="Country" Type="string"></QueryBuilderColumn>
                    <QueryBuilderColumn Field="City" Label="City" Type="string"></QueryBuilderColumn>
                </QueryBuilderColumns>
</SfQueryBuilder>
<SfButton CssClass="e-primary" @onclick="setRules">Get Rules</SfButton>
<SfButton CssClass="e-primary" @onclick="getSql">Get SQL</SfButton>

@code {
    SfQueryBuilder QueryBuilderObj;
    public List<Employee> EmployeeDetails = new List<Employee>
        {
        new Employee{ FirstName = "Martin", EmployeeID = "1001", Country = "England", City = "Manchester", HireDate = "23/04/2014" },
        new Employee{ FirstName = "Benjamin", EmployeeID = "1002", Country = "England", City = "Birmingham", HireDate = "19/06/2014" },
        new Employee{ FirstName = "Stuart", EmployeeID = "1003", Country = "England", City = "London", HireDate = "04/07/2014"},
        new Employee{ FirstName = "Ben", EmployeeID = "1004", Country = "USA", City = "California", HireDate = "15/08/2014" },
        new Employee{ FirstName = "Joseph", EmployeeID = "1005", Country = "Spain", City = "Madrid", HireDate = "29/08/2014" }
    };

    public class Employee {
        public string FirstName { get; set; }
        public string EmployeeID { get; set; }
        public string Country { get; set; }
        public string City { get; set; }
        public string HireDate { get; set; }
    }

    public QueryBuilderRule ImportRules = new QueryBuilderRule
    {
        Condition = "or",
        Rules = new List<RuleModel>{
            new RuleModel { Field = "EmployeeID", Value = "1001", Operator = "notequal" },
            new RuleModel { Field = "Country", Value = "England", Operator = "equal" }
        }
    };

    private async void getSql()
    {
        string sql = await QueryBuilderObj.GetSqlFromRules();
    }

    protected void setRules()
    {
        QueryBuilderObj.SetRulesFromSql("FirstName LIKE ('%Ch%')");
    }
 }

```