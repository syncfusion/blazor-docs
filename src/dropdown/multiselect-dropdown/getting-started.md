# Getting Started

This section briefly explains about how to include a [Blazor MultiSelect](https://www.syncfusion.com/blazor-components/blazor-multiselect-dropdown) Component in your Blazor Server-Side and Client-Side application. You can refer to our Getting Started with [Blazor Server-Side TextBox](../getting-started/blazor-server-side-visual-studio-2019/) and [Blazor WebAssembly TextBox](./getting-started-with-blazor-webassembly) documentation pages for configuration specifications.

## Importing Syncfusion Blazor component in the application

* Install `Syncfusion.Blazor.DropDowns` NuGet package to the application by using the `NuGet Package Manager`.

> Please ensure to check the `Include prerelease` option for our Beta release.

* You can add the client-side resources through CDN or from NuGet package in the  **HEAD** element of the **~/wwwroot/index.html**

 ```html
    <head>
            <link href="_content/Syncfusion.Blazor.Themes/bootstrap4.css" rel="stylesheet" />
            <!-- <link href="https://cdn.syncfusion.com/blazor/{{version}}/styles/{{theme}}.css" rel="stylesheet" /> -->
    </head>
```

> For Internet Explorer 11 kindly refer the polyfills. Refer the [documentation](https://ej2.syncfusion.com/blazor/documentation/common/how-to/render-blazor-server-app-in-ie/) for more information.

 ```html
    <head>
        <link href="_content/Syncfusion.Blazor.Themes/bootstrap4.css" rel="stylesheet" />
        <script src="https://github.com/Daddoon/Blazor.Polyfill/releases/download/3.0.1/blazor.polyfill.min.js"></script>
    </head>
```

## Adding component package to the application

Open `~/_Imports.razor` file and import the `Syncfusion.Blazor.DropDowns` package.

```csharp
@using Syncfusion.Blazor.DropDowns
```

## Add SyncfusionBlazor service in Program.cs

Open the **Program.cs** file and add services required by Syncfusion components using  **builder.Services.AddSyncfusionBlazor()** method.

```csharp
using Syncfusion.Blazor;

namespace BlazorApplication
{
    public class Program
    {
        public static async Task Main(string[] args)
        {
            ....
            ....
            builder.Services.AddSyncfusionBlazor();
            await builder.Build().RunAsync();
        }
    }
}
```

> To enable custom client side resource loading from CRG or CDN. You need to disable resource loading by `AddSyncfusionBlazor(true)` and load the scripts in the **HEAD** element of the **~/wwwroot/index.html** page.

 ```html
    <head>
            <script src="https://cdn.syncfusion.com/blazor/{:version:}/syncfusion-blazor.min.js"></script>
    </head>
```

## Adding MultiSelect component to the application

To initialize the MultiSelect component add the below code to your `Index.razor` view page which is present under `~/Pages` folder.

```csharp
<SfMultiSelect TValue="string[]" TItem="string" Placeholder='First Name'></SfMultiSelect>
```

Output be like below

![MultiSelect](./images/default.png)

## Binding data source

After initialization, populate the MultiSelect with data using the [DataSource](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.DropDowns.SfDropDownBase-1.html#Syncfusion_Blazor_DropDowns_SfDropDownBase_1_DataSource) property. Here, an array of string values is passed to the MultiSelect component. `TItem` specifies the type of the Datasource in MultiSelect.

The following example illustrates the output in your browser.

```csharp
<SfMultiSelect TValue="string[]" TItem="Games" Placeholder="Favorite Sports" DataSource="@LocalData">
<MultiSelectFieldSettings Text="Text" Value="ID"></MultiSelectFieldSettings>
</SfMultiSelect>

@code {

    public class Games
    {
        public string ID { get; set; }
        public string Text { get; set; }
    }
    List<Games> LocalData = new List<Games> {
    new Games() { ID= "Game1", Text= "American Football" },
    new Games() { ID= "Game2", Text= "Badminton" },
    new Games() { ID= "Game3", Text= "Basketball" },
    new Games() { ID= "Game4", Text= "Cricket" },
    new Games() { ID= "Game5", Text= "Football" },
    new Games() { ID= "Game6", Text= "Golf" },
    new Games() { ID= "Game7", Text= "Hockey" },
    new Games() { ID= "Game8", Text= "Rugby"},
    new Games() { ID= "Game9", Text= "Snooker" },
    new Games() { ID= "Game10", Text= "Tennis"},
    };
}
```

The output will be as follows.

![DataBinding](./images/data_binding.png)

## Configure the popup list

By default, the width of the popup list automatically adjusts according to the MultiSelect input element's width, and the height auto adjust's according to the height of the popup list items.

The height and width of the popup list can also be customized using the [PopupHeight](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.DropDowns.SfMultiSelect-1.html#Syncfusion_Blazor_DropDowns_SfMultiSelect_1_PopupHeight) and [PopupWidth](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.DropDowns.SfMultiSelect-1.html#Syncfusion_Blazor_DropDowns_SfMultiSelect_1_PopupWidth) properties respectively.

In the following sample, popup list's width and height are configured.

```csharp
<SfMultiSelect TValue="string[]" TItem="Games" Placeholder="Favorite Sports" PopupHeight="350px" PopupWidth="350px" DataSource="@LocalData">
<MultiSelectFieldSettings Text="Text" Value="ID"></MultiSelectFieldSettings>
</SfMultiSelect>

@code {

    public class Games
    {
        public string ID { get; set; }
        public string Text { get; set; }
    }
    List<Games> LocalData = new List<Games> {
    new Games() { ID= "Game1", Text= "American Football" },
    new Games() { ID= "Game2", Text= "Badminton" },
    new Games() { ID= "Game3", Text= "Basketball" },
    new Games() { ID= "Game4", Text= "Cricket" },
    new Games() { ID= "Game5", Text= "Football" },
    new Games() { ID= "Game6", Text= "Golf" },
    new Games() { ID= "Game7", Text= "Hockey" },
    new Games() { ID= "Game8", Text= "Rugby"},
    new Games() { ID= "Game9", Text= "Snooker" },
    new Games() { ID= "Game10", Text= "Tennis"},
    };
}
```

The output will be as follows.

![DataBinding](./images/width_height.png)

## See Also

* [Getting Started with Syncfusion Blazor for Client-Side in .NET Core CLI](../getting-started/blazor-webassembly-dotnet-cli/)
* [Getting Started with Syncfusion Blazor for Server-side in Visual Studio 2019](../getting-started/blazor-server-side-visual-studio-2019/)
* [Getting Started with Syncfusion Blazor for Server-Side in .NET Core CLI](../getting-started/blazor-server-side-dotnet-cli/)
