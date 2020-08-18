---
title: "Localization"
component: "Query Builder"
description: "Learn how to give localization support to rules and conditions"
---

# Localization

The `Localization` library allows you to localize default text content of the Query Builder. The Query Builder has static text that can be changed to other cultures (Arabic, Deutsch, French, etc.). In the following sample the text is changed to `German` culture.

The following list of properties and its values are used in the Query Builder.

| Locale key | en-US (default) |
| ------------ | ----------------------- |
| AddGroup  | Add Group |
| AddCondition  | Add Condition |
| DeleteRule | Remove this condition |
| DeleteGroup | Delete group |
| Edit | EDIT |
| SelectField | Select a field |
| SelectOperator | Select operator |
| StartsWith | Starts With|
| EndsWith | Ends With |
| Contains | Contains |
| Equal | Equal |
| NotEqual | Not Equal |
| LessThan | Less Than |
| LessThanOrEqual | Less Than Or Equal |
| GreaterThan | Greater Than |
| GreaterThanOrEqual | Greater Than Or Equal |
| Between | Between |
| NotBetween | Not Between|
| In | In |
| NotIn | Not In |
| Remove | REMOVE |
| ValidationMessage | This field is required |
| SummaryViewTitle | Summary View |
| OtherFields | Other Fields |
| AND | AND |
| OR | OR |
| SelectValue | Enter Value |
| IsEmpty | Is Empty |
| IsNotEmpty | Is Not Empty |
| IsNull | Is Null |
| IsNotNull | Is Not Null |

> To load translation object in an application, define the culture and the component locale text corresponding to the language in a separate `locale.json` file under `wwwroot` folder.

`locale.json`

```json
{
"de-DE": {
        "querybuilder": {
            "AddGroup": "Gruppe hinzufügen",
            "AddCondition": "Bedingung hinzufügen",
            "DeleteRule": "Entfernen Sie diesen Zustand",
            "DeleteGroup": "Gruppe löschen",
            "Edit": "BEARBEITEN",
            "SelectField": "Wählen Sie ein Feld aus",
            "DeleteRule": "Entfernen Sie diesen Zustand",
            "DeleteGroup": "Gruppe löschen",
            "SelectOperator": "Operator auswählen",
            "StartsWith": "Beginnt mit",
            "EndsWith": "Endet mit",
            "Contains": "Enthält",
            "Equal": "Gleich",
            "NotEqual": "Nicht gleich",
            "LessThan": "Weniger als",
            "LessThanOrEqual": "Weniger als oder gleich",
            "GreaterThan": "Größer als",
            "GreaterThanOrEqual": "Größer als oder gleich",
            "Between": "Zwischen",
            "NotBetween": "Nicht zwischen",
            "In": "Im",
            "NotIn": "Nicht in",
            "Remove": "LÖSCHEN",
            "ValidationMessage": "Dieses Feld wird benötigt",
            "AND": "Und",
            "OR": "Oder"
        }
    }
}

```

```csharp

@using Syncfusion.Blazor.QueryBuilder

<SfQueryBuilder>
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
    [Inject]
    protected IJSRuntime JsRuntime { get; set; }

    protected override void OnAfterRender()
    {
        this.JsRuntime.Sf().LoadLocaleData("wwwroot/locale.json").SetCulture("de-DE");
    }

}

```

Output will be shown as

![Query Builder Sample](./images/qb-locale.png)