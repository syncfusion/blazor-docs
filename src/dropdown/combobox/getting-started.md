# Getting Started

This section briefly explains about how to include a [Blazor ComboBox](https://www.syncfusion.com/blazor-components/blazor-combobox) Component in your Blazor Server-Side and Client-Side application. You can refer to our Getting Started with [Blazor Server-Side TextBox](../getting-started/blazor-server-side-visual-studio-2019/) and [Blazor WebAssembly TextBox](./getting-started-with-blazor-webassembly) documentation pages for configuration specifications.

To get start quickly with Blazor ComboBox component, you can check on this video.

`youtube:VYK2xHC_Lrg`

## Importing Syncfusion Blazor component in the application

* Install `Syncfusion.Blazor.DropDowns` NuGet package to the application by using the `NuGet Package Manager`.

> Please ensure to check the `Include prerelease` option for our Beta release.

* You can add the client-side resources through CDN or from NuGet package in the  **HEAD** element of the **~/wwwroot/index.html** page.

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

## Adding ComboBox component to the application

To initialize the ComboBox component add the below code to your `Index.razor` view page which is present under `~/Pages` folder.

```csharp
<SfComboBox TValue="string" TItem="string" Placeholder="Select a game"></SfComboBox>
```

## Run the application

After successful compilation of your application, press `F5` to run the application.

The output will be as follows.

![ComboBox](./images/default.png)

## Binding data source

After initializing, populate the ComboBox with data using the [DataSource](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.DropDowns.SfDropDownBase-1.html#Syncfusion_Blazor_DropDowns_SfDropDownBase_1_DataSource) property. Here, an array of string values is passed to the ComboBox component.

The following example illustrates the output in your browser.

```csharp
<SfComboBox TValue="string" TItem="Games" Placeholder="Select a game" DataSource="@LocalData">
<ComboBoxFieldSettings Value="ID" Text="Text"></ComboBoxFieldSettings>
</SfComboBox>

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

![ComboBox](./images/data_binding.png)

## Custom values

The ComboBox allows the users to give input as custom value, which is not required to present in predefined
set of values. By default, this support is enabled by [AllowCustom](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.DropDowns.SfComboBox-2.html#Syncfusion_Blazor_DropDowns_SfComboBox_2_AllowCustom) property. In this case, both text field and value field is considered as same. The custom value will be sent to post back handler when a form is about to be submitted.

```csharp
<SfComboBox TValue="string"  TItem="Games" AllowCustom=true Placeholder="Select a game" DataSource="@LocalData">
<ComboBoxFieldSettings Value="ID" Text="Text"></ComboBoxFieldSettings>
</SfComboBox>

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

![ComboBox](./images/custom.png)

## Configure the popup list

By default, the width of the popup list automatically adjusts according to the ComboBox input element's width, and the height of the popup list has `350px`.

The height and width of the popup list can also be customized using the [PopupHeight](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.DropDowns.SfComboBox-2.html) and [PopupWidth](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.DropDowns.SfComboBox-2.html) properties respectively.

In the following sample, popup list's width and height are configured.

```csharp

<SfComboBox TValue="string" TItem="Games"PopupHeight="350px" PopupWidth="350px" Placeholder="Select a game" DataSource="@LocalData">
<ComboBoxFieldSettings Value="ID" Text="Text"></ComboBoxFieldSettings>
</SfComboBox>

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

![ComboBox](./images/width_height.png)

## See Also

* [Getting Started with Syncfusion Blazor for Client-Side in .NET Core CLI](../getting-started/blazor-webassembly-dotnet-cli/)
* [Getting Started with Syncfusion Blazor for Server-side in Visual Studio 2019](../getting-started/blazor-server-side-visual-studio-2019/)
* [Getting Started with Syncfusion Blazor for Server-Side in .NET Core CLI](../getting-started/blazor-server-side-dotnet-cli/)
