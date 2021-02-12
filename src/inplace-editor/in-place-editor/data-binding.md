---
component: "In-place Editor"
---

# Data Binding

The Razor components load the data either from local data sources or remote data services using the `DataSource` property and it supports the data type of an array or `DataManager`. Also supports different kind of data services such as OData, OData V4, Web API, and data formats such as XML, JSON, JSONP with the help of `DataManager` adaptors.

## Local

To bind local data to the Razor components, you can assign an array of object or string to the `DataSource` property. The local data source can also be provided as an instance of the `DataManager`.

```csharp

@using Syncfusion.Blazor.DropDowns
@using Syncfusion.Blazor.InPlaceEditor

<div id="container">
    <span class="content-title"> Select customer name: </span>
    <SfInPlaceEditor @bind-Value="@DropDownValue" Type="Syncfusion.Blazor.InPlaceEditor.InputType.DropDownList" TValue="string">
        <EditorComponent>
            <SfDropDownList TItem="string" TValue="string" Placeholder="Select a customer" @bind-Value="@DropDownValue" DataSource="@DataManager">
            </SfDropDownList>
        </EditorComponent>
    </SfInPlaceEditor>
</div>

<style>
    #container {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 80px;
    }

    #element {
        width: 150px;
    }

    .content-title {
        font-weight: 500;
        margin-right: 20px;
        display: flex;
        align-items: center;
    }
</style>

@code {
    public string DropDownValue = "Maria Anders";
    public static string[] DataManager = new string[] { "Maria Anders", "Ana Trujillo", "Antonio Moreno", "Thomas Hardy", "Chiristina Berglund", "Hanna Moos" };

}

```

The output will be as follows.

![data](./images/data.png)
