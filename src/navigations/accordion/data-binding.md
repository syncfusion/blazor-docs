---
title: "data bindig"
component: "Accordion"
description: "This example demonstrates how to bind any data object to accordion items in the Blazor Accordion component."
---

# DataBinding

Accordion component provides an option to get accordion items from the local data. It can be done through `DataSource` property. The `DataSource` property supports list of objects.

You can use `HeaderTemplate` and `ItemTemplate` properties to render accordion header and content respectively.

> If you use `DataSource` property, It is mandatory to define `HeaderTemplate` and `ContentTemplate` to render accordion header and content. Accordion only supports the local data for data binding.

The below sample explains how to initialize accordion items through `DataSource` and `templates`.

```csharp
@using Syncfusion.Blazor.Navigations

<SfAccordion DataSource="@AccordionItems">
    <AccordionTemplates>
        <HeaderTemplate>
            <div>@((context as AccordionData).EmployeeName)</div>
        </HeaderTemplate>
        <ItemTemplate>
            @{
                AccordionData ContextData = context as AccordionData;
                <div>
                    <div><b>Employee ID: </b>@ContextData.EmployeeId</div>
                    <div><b>Designation: </b>@ContextData.Designation</div>
                </div>
            }
        </ItemTemplate>
    </AccordionTemplates>
</SfAccordion>

@code{
    List<AccordionData> AccordionItems = new List<AccordionData>()
    {
        new AccordionData
        {
        EmployeeId = 1,
        EmployeeName = "Laura Callahan",
        Designation = "Product Manager",
        },
        new AccordionData
        {
        EmployeeId = 3,
        EmployeeName = "Andrew Fuller",
        Designation = "Team Lead",
        },
        new AccordionData
        {
        EmployeeId = 4,
        EmployeeName = "Anne Dodsworth",
        Designation = "Developer"
        },
        new AccordionData
        {
        EmployeeId = 5,
        EmployeeName = "Nancy Davolio",
        Designation = "Product Manager"
        }
    };

    public class AccordionData
    {
        public string EmployeeName { get; set; }
        public int EmployeeId { get; set; }
        public string Designation { get; set; }
    }
}
```

Output be like the below.

![Load Accordion items using datasource](./images/acrdnDatasource.png)