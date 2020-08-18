---
title: "Blazor In-place Editor | Get started from server-side"
component: "In-place Editor"
description: "Get started with Blazor In-place Editor using Blazor server-side application by rendering datepicker and dropdown component, and submit data to the server."
---
<!-- markdownlint-disable MD024 -->

# Getting Started

This section briefly explains how to include a In-Place Editor component in your Blazor Server-side application. You can refer [Getting Started with Syncfusion Blazor for Server-Side in Visual Studio 2019 page](../getting-started/server-side-blazor/) for the introduction and configuring the common specifications.

## Importing Syncfusion Blazor component in the application

* Install `Syncfusion.Blazor` NuGet package to the application by using the `NuGet Package Manager`.

> Please ensure to check the `Include prerelease` option for our Beta release.

* You can add the client-side resources through CDN or from NuGet package in the `<head>` element of the **~/Pages/_Host.cshtml** page.

```html

<head>
    <link href="_content/Syncfusion.Blazor/styles/bootstrap4.css" rel="stylesheet" />
    @*<link href="https://cdn.syncfusion.com/blazor/{:version:}/styles/bootstrap4.css" rel="stylesheet" />*@
</head>

```

> For Internet Explorer 11 kindly refer the polyfills. Refer the [documentation](../../common/how-to/render-blazor-server-app-in-ie/) for more information.

```html

<head>
    <link href="_content/Syncfusion.Blazor/styles/bootstrap4.css" rel="stylesheet" />
    <script src="https://github.com/Daddoon/Blazor.Polyfill/releases/download/3.0.1/blazor.polyfill.min.js"></script>
</head>

```

## Adding component package to the application

Open **~/_Imports.razor** file and import the `Syncfusion.Blazor.InPlaceEditor` package.

```csharp

@using Syncfusion.Blazor.InPlaceEditor

```

## Add SyncfusionBlazor service in Startup.cs

Open the **Startup.cs** file and add services required by Syncfusion components using `services.AddSyncfusionBlazor()` method. Add this method in the ConfigureServices function as follows.

```csharp

using Syncfusion.Blazor;
namespace BlazorApplication
{
    public class Startup
    {
        ....
        ....
        public void ConfigureServices(IServiceCollection services)
        {
            ....
            ....
            services.AddSyncfusionBlazor();
        }
    }
}

```

## Add In-Place Editor component

To initialize the In-Place Editor component, add the below code to your **Index.razor** view page which is present under **~/Pages** folder.

The following code explains how to initialize a simple In-place Editor in the Razor page.

```csharp

@using Syncfusion.Blazor.InPlaceEditor

<table>
    <tr>
        <td>
            <label class="control-label" style="text-align: left;font-size: 14px;font-weight: 400">
                TextBox
            </label>
        </td>
        <td>
            <SfInPlaceEditor Mode="RenderMode.Inline" Type="InputType.Text" Value="@TextValue" SubmitOnEnter="true" Model="@TModel">
            </SfInPlaceEditor>
        </td>
    </tr>
</table>

@code {
    public string TextValue = "Andrew";

    public TextBoxModel TModel = new TextBoxModel()
    {
        Placeholder = "Enter employee name"
    };
}

```

## Render In-place Editor with popup

The following code explains how to initialize a simple In-place Editor with popup in the Blazor page.

```csharp

@using Syncfusion.Blazor.InPlaceEditor

<table>
    <tr>
        <td>
            <label class="control-label">
                Choose a Country:
            </label>
        </td>
        <td>
            <SfInPlaceEditor Mode="RenderMode.Popup" Type="InputType.AutoComplete" Value="@AutoValue" Model="@AutocompleteData">
            </SfInPlaceEditor>
        </td>
    </tr>
</table>

@code {
    public string AutoValue = "Australia";

    public AutoCompleteModel<string> AutocompleteData = new AutoCompleteModel<string>()
    {
        Placeholder = "Type to search countries",
        DataSource = new string[] { "Australia", "Bermuda", "Canada", "Cameroon", "Denmark", "Finland", "Greenland", "Poland" }
    };
}

```

## Run the application

After successful compilation of your application, run the application.

Output be like the below.

![Inplace-editor inline mode](./images/inline.png)

![Inplace-editor popup mode](./images/popup-mode.png)

## Configuring DropDownList

You can render the Blazor DropDownList by changing the `Type` property as `DropDownList` and configure its properties and methods using the `Model` property.

In the following example, `Type` and model values are configured to render the `DropDownList` component.

```csharp

@using Syncfusion.Blazor.InPlaceEditor

<SfInPlaceEditor Mode="RenderMode.Inline" Type="InputType.DropDownList" Value="@DropdownValue" Model="@DropdownData" />

@code {
    public string DropdownValue = "Australia";

    public DropDownListModel<string> DropdownData = new DropDownListModel<string>()
    {
        Placeholder = "Select Country",
        DataSource = new string[] { "Australia", "Bermuda", "Canada", "Cameroon", "Denmark", "Finland", "Greenland", "Poland" }
    };
}

```

## Integrate DatePicker

You can render the Blazor `DatePicker` by changing the `Type` property as `Date` and also configure its properties and methods using the `Model` property.

In the following sample, `Type` and `Model` values are configured to render the `DatePicker` component.

```csharp

@using Syncfusion.Blazor.InPlaceEditor

<SfInPlaceEditor Mode="RenderMode.Inline" Type="InputType.Date" Value="@DateValue" Model="@DateModel" />

@code {
    public DateTime DateValue { get; set; } = new DateTime(DateTime.Now.Year, DateTime.Now.Month, DateTime.Now.Day);

    public DatePickerModel DateModel = new DatePickerModel()
    {
        Placeholder = "Select date",
        ShowTodayButton = true
    };
}

```

In the following code, it is configured to render the `DatePicker`, `Dropdownlist` and `Textbox` components.

```csharp

@using Syncfusion.Blazor.InPlaceEditor

<div id="container" class="control-group">
    <h3> Modify Basic Details </h3>
    <table style="margin: 10px auto;">
        <tr>
            <td>Name</td>
            <td class='left'>
                <SfInPlaceEditor Mode="RenderMode.Inline" Type="InputType.Text" Value="@TextValue" Model="@TModel">
                </SfInPlaceEditor>
            </td>
        </tr>
        <tr>
            <td>Date of Birth</td>
            <td class='left'>
                <SfInPlaceEditor Mode="RenderMode.Inline" Type="InputType.Date" Value="@DateValue" Model="@DateModel">
                </SfInPlaceEditor>
            </td>
        </tr>
        <tr>
            <td>Gender</td>
            <td class='left'>
                <SfInPlaceEditor Mode="RenderMode.Inline" Type="InputType.DropDownList" Value="@DropdownValue" Model="@DropdownData">
                </SfInPlaceEditor>
            </td>
        </tr>
    </table>
</div>

<style>
    #container {
        text-align: center;
        margin-top: 50px;
    }

        #container table {
            width: 400px;
            margin: auto;
        }

            #container table td {
                height: 70px;
                width: 150px;
            }

            #container table .left {
                text-align: left;
            }
</style>

@code {
    public DateTime DateValue { get; set; } = new DateTime(DateTime.Now.Year, DateTime.Now.Month, DateTime.Now.Day);
    public string TextValue = "Andrew";
    public string DropdownValue = "Male";

    public DropDownListModel<string> DropdownData = new DropDownListModel<string>()
    {
        Placeholder = "Select Gender",
        DataSource = new string[] { "Male", "Female" }
    };

    public DatePickerModel DateModel = new DatePickerModel()
    {
        Placeholder = "Select date",
        ShowTodayButton = true
    };
    public TextBoxModel TModel = new TextBoxModel()
    {
        Placeholder = "Enter your name"
    };
}

```

Output be like the below.

![Inplace-editor components](./images/components.png)

## Submitting data to the server (save)

You can submit editor value to the server by configuring the `Url`, `Adaptor` and `PrimaryKey` property.

| Property   | Usage                                           |
|------------|---------------------------------------------------------|
| **`Url`**        | Gets the URl for server submit action.        |
| **`Adaptor`**    | Specifies the adaptor type that is used by DataManager to communicate with DataSource.                |
| **`PrimaryKey`** | Defines the unique primary key of editable field which can be used for saving data in the data-base.|

> The `PrimaryKey` property is mandatory. If it is not set, edited data are not sent to the server.

## Refresh In-place Editor with modified value

The edited data is submitted to the server and you can see the new values getting reflected in the In-place Editor.

```csharp

@using Syncfusion.Blazor.InPlaceEditor

<div id="container">
    <div class="control-group">
        Best Employee of the year: <SfInPlaceEditor PrimaryKey="Employee" Name="Employee" Adaptor="AdaptorType.UrlAdaptor" Url="https://ej2services.syncfusion.com/production/web-services/api/Editor/UpdateData" Mode="RenderMode.Inline" Type="InputType.DropDownList" Value="@DropdownValue" Model="@DropdownData">
            <InPlaceEditorEvents Created="OnCreate" OnActionSuccess="OnSuccess" TValue="string"></InPlaceEditorEvents>
        </SfInPlaceEditor>
    </div>
    <table style="margin:60px auto;width:25%">
        <tr>
            <td style="text-align: left">
                Old Value :
            </td>
            <td id="oldValue" style="text-align: left">
                @PreviousValue
            </td>
        </tr>
        <tr>
            <td style="text-align: left">
                New Value :
            </td>
            <td id="newValue" style="text-align: left">
                @CurrentValue
            </td>
        </tr>
    </table>
</div>

<style>
    .e-inplaceeditor {
        min-width: 200px;
        text-align: left;
    }

    #container .control-group {
        text-align: center;
        margin: 100px auto;
    }
</style>

@code {
    public string PreviousValue { get; set; }
    public string DropdownValue = "Andrew Fuller";
    public string CurrentValue { get; set; }

    public DropDownListModel<string> DropdownData = new DropDownListModel<string>()
    {
        Placeholder = "Select employee",
        DataSource = new string[] { "Andrew Fuller", "Janet Leverling", "Laura Callahan", "Margaret Hamilt", "Michael Suyama", "Nancy Davloio", "Robert King" },
        PopupHeight = "200px"

    };

    public void OnCreate(object args)
    {
        this.CurrentValue = this.DropdownValue;
    }

    public void OnSuccess(ActionEventArgs args)
    {
        this.PreviousValue = this.CurrentValue;
        this.CurrentValue = args.Value;
    }
}

```

The output will be as follows.

![Getting started](./images/getting-started.png)

## See Also

* [Getting Started with Syncfusion Blazor for client-side in .NET Core CLI](../getting-started/blazor-webassembly-dotnet-cli/)

* [Getting Started with Syncfusion Blazor for server-side in Visual Studio 2019](../getting-started/server-side-blazor/)

* [Getting Started with Syncfusion Blazor for server-side in .NET Core CLI](../getting-started/server-side-blazor-dotnet-cli/)