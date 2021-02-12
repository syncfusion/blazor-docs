---
component: "TreeView"
---

# Template

The TreeView component allows you to customize the look of TreeView nodes using the `NodeTemplate` property.

The NodeTemplate tag is nested inside the TreeViewTemplates tag, where you can define the custom structure for TreeView. Inside the NodeTemplate tag, a generic type context property is used to access the tree node details.

In the following sample, employee information such as employee photo, name, and designation have been included using the `NodeTemplate` property.

```csharp
@using Syncfusion.Blazor.Navigations
@inject Microsoft.AspNetCore.Components.NavigationManager UriHelper

<SfTreeView TValue="EmployeeDetails" CssClass="custom">
    <TreeViewFieldsSettings TValue="EmployeeDetails" Id="EmployeeId" Text="EmployeeName" DataSource="@Employee" Expanded="Expanded" HasChildren="HasChild" Selected="Selected" ParentID="ParentId"></TreeViewFieldsSettings>
    <TreeViewTemplates TValue="EmployeeDetails">
        <NodeTemplate>
            @{
                var employee = ((context as EmployeeDetails));
                <img class="eimage" src="@UriHelper.ToAbsoluteUri($"/css/images/Employees/{@employee.Image}.png")" alt="@employee.Image" />
                <div class="ename">@((@context as EmployeeDetails).EmployeeName)</div>
                <div class="ejob">@((@context as EmployeeDetails).Designation)</div>
            }
        </NodeTemplate>
    </TreeViewTemplates>
</SfTreeView>

@code
{
    public class EmployeeDetails
    {
        public string EmployeeName { get; set; }
        public int EmployeeId { get; set; }
        public int? ParentId { get; set; }
        public bool HasChild { get; set; }
        public bool Expanded { get; set; }
        public bool Selected { get; set; }
        public string Image { get; set; }
        public string Designation { get; set; }
    }

    List<EmployeeDetails> Employee = new List<EmployeeDetails>();

    protected override void OnInitialized()
    {
        base.OnInitialized();

        Employee.Add(new EmployeeDetails
        {
            EmployeeId = 1,
            EmployeeName = "Steven Buchanan",
            HasChild = true,
            Expanded = true,
            Image = "10",
            Designation = "CEO"
        });
        Employee.Add(new EmployeeDetails
        {
            EmployeeId = 2,
            ParentId = 1,
            EmployeeName = "Laura Callahan",
            Image = "2",
            Designation = "Product Manager",
            HasChild = true
        });
        Employee.Add(new EmployeeDetails
        {
            EmployeeId = 3,
            ParentId = 2,
            EmployeeName = "Andrew Fuller",
            Image = "7",
            Designation = "Team Lead",
            HasChild = true
        });
        Employee.Add(new EmployeeDetails
        {
            EmployeeId = 4,
            ParentId = 3,
            EmployeeName = "Anne Dodsworth",
            Image = "1",
            Designation = "Developer"
        });
        Employee.Add(new EmployeeDetails
        {
            EmployeeId = 5,
            ParentId = 1,
            EmployeeName = "Nancy Davolio",
            HasChild = true,
            Image = "4",
            Designation = "Product Manager"
        });
        Employee.Add(new EmployeeDetails
        {
            EmployeeId = 6,
            ParentId = 5,
            EmployeeName = "Michael Suyama",
            Image = "9",
            Designation = "Team Lead",
            HasChild = true
        });
        Employee.Add(new EmployeeDetails
        {
            EmployeeId = 7,
            ParentId = 6,
            EmployeeName = "Robert King",
            Image = "8",
            Designation = "Developer"
        });
        Employee.Add(new EmployeeDetails
        {
            EmployeeId = 8,
            ParentId = 7,
            EmployeeName = "Margaret Peacock",
            Image = "6",
            Designation = "Developer"
        });
        Employee.Add(new EmployeeDetails
        {
            EmployeeId = 9,
            ParentId = 1,
            EmployeeName = "Janet Leverling",
            Image = "3",
            Designation = "HR"
        });
    }
}
<style>
    .custom.e-treeview .e-fullrow {
        height: 72px;
    }

    .custom.e-treeview .e-list-text {
        line-height: normal;
    }

    .eimage {
        float: left;
        padding: 11px 16px 11px 0;
        height: 48px;
        width: 48px;
        box-sizing: content-box;
    }

    .ename {
        font-size: 16px;
        padding: 14px 0 0;
    }

    .ejob {
        font-size: 14px;
        opacity: .87;
    }
</style>
```

Output be like the below.

![TreeView Sample](./images/template.png)
