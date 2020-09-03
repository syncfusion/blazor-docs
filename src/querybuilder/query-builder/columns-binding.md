---
title: "Columns Binding"
component: "Query Builder"
description: "This section helps to learn how to bind the columns in the Query Builder in Blazor application in step-by-step procedure."
---

# Column Binding

The column definitions are used as the [`DataSource`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.QueryBuilder.SfQueryBuilder.html#Syncfusion_Blazor_QueryBuilder_SfQueryBuilder_DataSource) schema in the Query Builder. This plays a vital role in rendering column values. The Query Builder operations such as create or delete conditions and create or delete groups are performed based on the column definitions. The [`Field`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.QueryBuilder.QueryBuilderColumn.html#Syncfusion_Blazor_QueryBuilder_QueryBuilderColumn_Field) property of the [`Columns`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.QueryBuilder.SfQueryBuilder.html#Syncfusion_Blazor_QueryBuilder_SfQueryBuilder_Columns) is necessary to map the data source values in the query builder columns.

> If the column field is not specified in the data source, the column values will be empty.

## Auto generation

The [`Columns`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.QueryBuilder.SfQueryBuilder.html#Syncfusion_Blazor_QueryBuilder_SfQueryBuilder_Columns) are automatically generated when the [`Columns`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.QueryBuilder.SfQueryBuilder.html#Syncfusion_Blazor_QueryBuilder_SfQueryBuilder_Columns) declaration is empty or undefined while initializing the query builder. All the columns in the `DataSource` are bound as the query builder columns.

```csharp
@using Syncfusion.Blazor.QueryBuilder

<SfQueryBuilder DataSource="@EmployeeDetails"></SfQueryBuilder>

@code {
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
}

```

> When columns are auto-generated, the column type will be determined from the first record of the data source.

## Labels

By default, the column label is displayed from the column [`Field`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.QueryBuilder.QueryBuilderColumn.html#Syncfusion_Blazor_QueryBuilder_QueryBuilderColumn_Field) value. To override the default label, you have to define the [`Label`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.QueryBuilder.QueryBuilderColumn.html#Syncfusion_Blazor_QueryBuilder_QueryBuilderColumn_Label) value.

> If both the field and headerText are not defined in the column, the column renders with `empty` header text.

## Operators

The operator for a column can be defined in the [`Columns`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.QueryBuilder.SfQueryBuilder.html#Syncfusion_Blazor_QueryBuilder_SfQueryBuilder_Columns) property.
The available operators and its supported data types are:

| Operators | Description | Supported Types |
| ------------ | ----------------------- | ------------------ |
| startswith  | Checks whether the value begins with the specified value. | String |
| endswith  | Checks whether the value ends with the specified value. | String |
| contains | Checks whether the value contains the specified value. | String |
| equal | Checks whether the value is equal to the specified value. | String|Number/Date/Boolean |
| notequal | Checks for values not equal to the specified value. | String/Number| Date| Boolean |
| greaterthan | Checks whether the value is greater than the specified value. | Date/Number |
| greaterthanorequal | Checks whether a value is greater than or equal to the specified value. | Date/Number |
| lessthan | Checks whether the value is less than the specified value.| Date/Number |
| lessthanorequal | Checks whether the value is less than or equal to the specified value. | Date/Number |
| between | Checks whether the value is between the two-specific value. | Date/Number |
| notbetween | Checks whether the value is not between the two-specific value. | Date/Number |
| in | Checks whether the value is one of the specific values. | String/Number |
| notin | Checks whether the value is not in the specific values. | String/Number |
| isempty | Checks whether the value is empty in the specific values. | String/Number |
| isnotempty | Checks whether the value is not empty in the specific values. | String/Number |

## Step

The Query Builder allows you to set the step values to the number fields. So that, you can easily access the numeric textbox. Use the [`Step`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.QueryBuilder.QueryBuilderColumn.html#Syncfusion_Blazor_QueryBuilder_QueryBuilderColumn_Step) property, to set the step value for number values.

## Format

The Query Builder formats date and number values. Use the [`Format`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.QueryBuilder.QueryBuilderColumn.html#Syncfusion_Blazor_QueryBuilder_QueryBuilderColumn_Format)   property, to format date and number values.

```csharp
@using Syncfusion.Blazor.QueryBuilder

<SfQueryBuilder DataSource="@EmployeeDetails" @ref="QueryBuilderObj">
    <QueryBuilderColumns>
        <QueryBuilderColumn Field="EmployeeID" Label="Employee ID" Type="number">
        </QueryBuilderColumn>
        <QueryBuilderColumn Field="FirstName" Label="First Name" Type="string"></QueryBuilderColumn>
        <QueryBuilderColumn Field="TitleOfCourtesy" Label="Title Of Courtesy" Type="boolean">
        </QueryBuilderColumn>
        <QueryBuilderColumn Field="HireDate" Label="Hire Date" Type="date" Format = "MM/dd/yyyy">
        </QueryBuilderColumn>
        <QueryBuilderColumn Field="Country" Label="Country" Type="string"></QueryBuilderColumn>
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
}
```

Output will be shown as

![Query Builder Sample](./images/qb-format.png)

## Validations

Validation allows you to validate the conditions and it display errors for invalid fields while using the [`ValidateFields`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.QueryBuilder.SfQueryBuilder.html#Syncfusion_Blazor_QueryBuilder_SfQueryBuilder_ValidateFields) method. To enable validation in the Query Builder, set [`AllowValidation`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.QueryBuilder.SfQueryBuilder.html#Syncfusion_Blazor_QueryBuilder_SfQueryBuilder_AllowValidation) to true. Column fields are validated after setting [`AllowValidation`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.QueryBuilder.SfQueryBuilder.html#Syncfusion_Blazor_QueryBuilder_SfQueryBuilder_AllowValidation) to true. So, you should manually configure the validation for Operator and Value fields through `Validation`.

> Set `IsRequired` validation for Operator and Value fields.
> Set `Min`, `Max` values for number values.

```csharp
@using Syncfusion.Blazor.QueryBuilder
@using Syncfusion.Blazor.Buttons

<SfQueryBuilder DataSource="@EmployeeDetails" AllowValidation="true" @ref="QueryBuilderObj">
                <QueryBuilderColumns>
                    <QueryBuilderColumn Field="EmployeeID" Label="Employee ID" Type="number"></QueryBuilderColumn>
                    <QueryBuilderColumn Field="FirstName" Label="First Name" Type="string"></QueryBuilderColumn>
                    <QueryBuilderColumn Field="TitleOfCourtesy" Label="Title Of Courtesy" Type="boolean"></QueryBuilderColumn>
                    <QueryBuilderColumn Field="HireDate" Label="Hire Date" Type="date" Format = "MM/dd/yyyy"></QueryBuilderColumn>
                    <QueryBuilderColumn Field="Country" Label="Country" Type="string"></QueryBuilderColumn>
                </QueryBuilderColumns>
</SfQueryBuilder>
<SfButton CssClass="e-primary" @onclick="validate" >Validation</SfButton>

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

    private void validate()
    {
        QueryBuilderObj.ValidateFields();
    }
}

```

Output will be shown as

![Query Builder Sample](./images/qb-validate.png)