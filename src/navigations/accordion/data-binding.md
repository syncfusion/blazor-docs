---
component: "Accordion"
---

# DataBinding

Accordion component provides an option to get accordion items from the local data. It can be done through iteration of Accordion Items using conditional **foreach** loop. Accordion only supports the local data for data binding.

You can use `HeaderTemplate` and `ContentTemplate` properties to render accordion header and content respectively.

The below sample explains how to initialize accordion items through `templates`.

```csharp
@using Syncfusion.Blazor.Navigations

<SfAccordion>
    <AccordionItems>
        @foreach (AccordionData Item in AccordionItems)
        {
            <AccordionItem>
                <HeaderTemplate>
                    <div>@(Item.EmployeeName)</div>
                </HeaderTemplate>
                <ContentTemplate>
                    <div>
                        <div><b>Employee ID: </b>@Item.EmployeeId</div>
                        <div><b>Designation: </b>@Item.Designation</div>
                    </div>
                </ContentTemplate>
            </AccordionItem>
        }
    </AccordionItems>
</SfAccordion>

@code {
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

![Load Accordion items using datasource](./images/acrdnDatabinding.png)