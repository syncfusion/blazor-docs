---
layout: post
title: Custom Resource Generator (CRG) in Blazor | Syncfusion
description: Learn here about that how to using the custom resource generator in the Syncfusion Blazor Components
platform: Blazor
component: Common
documentation: ug
---

# Custom Resource Generator

Syncfusion provides an option to generate a component's interop script and styles using the [Custom Resource Generator](https://blazor.syncfusion.com/crg) (CRG) web tool for Blazor components from v19.2.0.44.

![Custom resource generator preview for Blazor](images/custom-resource-generator-preview.png)

## Search and select the component list

Search and select the required Syncfusion Blazor UI components from the CRG to generate a specific set of component resources.

Refer to the following steps to search and select the components in CRG:

1. Open [Syncfusion Custom Resource Generator](https://blazor.syncfusion.com/crg) (CRG) application.

2. Type the required component name in the search bar, and then select the checkbox. The dependency of the selected component is resolved in the application itself, so you do not need to choose each dependent component manually.

    ![Search and select Syncfusion Blazor UI components](images/search-non-injectable.png)

3. Select the required built-in themes from the **Select Themes** option. This provides an option to select more than one theme.

    ![Select the built-in themes](images/select-inbuilt-themes.png)

## Download the selected component resources

After selecting the required component resources, download the custom interop script and styles from CRG.

Refer to the following steps to download the custom resources in CRG:

1. Click the **DOWNLOAD** button at the bottom of the page. Select the **Minified** option to generate the minified file output for production.

    ![Download option](images/download-option.png)

2. Change the file name as needed, and then click **GENERATE** button in the pop-up.

    ![Export popup for generation custom resources](images/export-popup.png)

3. Now, the bundling process for the selected components will be started, and the output will be downloaded as a zip file.

    ![blazor Bundle custom resources](images/bundling-custom-resources.png)

4. The final output contains the custom interop script and styles for the selected components and an **import.json** file, which stores the current settings.

    ![Final output of customized resources](images/customized-resources.png)

## How to use custom resources in the Blazor application

1. Copy and paste the downloaded custom resources in the Blazor application `~/wwwroot` folder.

2. Set [IgnoreScriptIsolation](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.GlobalOptions.html#Syncfusion_Blazor_GlobalOptions_IgnoreScriptIsolation) as `true` while adding Syncfusion blazor service using `AddSyncfusionBlazor()` as follows,

### Blazor Server App

* For **.NET 6** app, open the **~/Program.cs** file and register the Syncfusion Blazor Service by setting `IgnoreScriptIsolation`.

* For **.NET 5 and .NET 3.X** app, open the **~/Startup.cs** file and register the Syncfusion Blazor Service by setting `IgnoreScriptIsolation`.

{% tabs %}
{% highlight c# tabtitle=".NET 6 (~/Program.cs)" hl_lines="10" %}

using Microsoft.AspNetCore.Components;
using Microsoft.AspNetCore.Components.Web;
using Syncfusion.Blazor;

var builder = WebApplication.CreateBuilder(args);

// Add services to the container.
builder.Services.AddRazorPages();
builder.Services.AddServerSideBlazor();
builder.Services.AddSyncfusionBlazor(options => { options.IgnoreScriptIsolation = true; );

var app = builder.Build();
....

{% endhighlight %}

{% highlight c# tabtitle=".NET 5 and .NET 3.X (~/Startup.cs)" hl_lines="12" %}

using Syncfusion.Blazor;

namespace BlazorApplication
{
    public class Startup
    {
        ...
        public void ConfigureServices(IServiceCollection services)
        {
            services.AddRazorPages();
            services.AddServerSideBlazor();
            services.AddSyncfusionBlazor(options => { options.IgnoreScriptIsolation = true; );
        }
        ...
    }
}

{% endhighlight %}
{% endtabs %}

### Blazor WASM App

For Blazor WebAssembly App, set [IgnoreScriptIsolation](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.GlobalOptions.html#Syncfusion_Blazor_GlobalOptions_IgnoreScriptIsolation) property as `true` using `AddSyncfusionBlazor` service method in `~/Program.cs` file.

{% tabs %}
{% highlight c# tabtitle=".NET 6 (~/Program.cs)" %}

using Microsoft.AspNetCore.Components.Web;
using Microsoft.AspNetCore.Components.WebAssembly.Hosting;
using Syncfusion.Blazor;

var builder = WebAssemblyHostBuilder.CreateDefault(args);
builder.RootComponents.Add<App>("#app");
builder.RootComponents.Add<HeadOutlet>("head::after");

builder.Services.AddScoped(sp => new HttpClient { BaseAddress = new Uri(builder.HostEnvironment.BaseAddress) });

builder.Services.AddSyncfusionBlazor(options => { options.IgnoreScriptIsolation = true; );
await builder.Build().RunAsync();
....

{% endhighlight %}

{% highlight c# tabtitle=".NET 5 and .NET 3.X (~/Program.cs)" %}
using Syncfusion.Blazor;

namespace WebApplication1
{
    public class Program
    {
        public static async Task Main(string[] args)
        {
            ....
            builder.Services.AddSyncfusionBlazor(options => { options.IgnoreScriptIsolation = true; );
            await builder.Build().RunAsync();
        }
    }
}
{% endhighlight %}
{% endtabs %}

3. Now, manually add the custom interop script and styles in the Blazor App.

    * For **Blazor WASM App**, reference custom interop script in `~/wwwroot/index.html` file. 
    * For **Blazor Server App**, reference custom interop script in `~/Pages/_Layout.cshtml` file for `.NET 6` project and in `~/Pages/_Host.cshtml` file for `.NET 5 and .NET Core 3.X` project.

    ```html
    <head>
        ....
        ....
        <link href="material.css" rel="stylesheet" />
        <script src="syncfusion-blazor.min.js" type="text/javascript"></script>
    </head>
    ```
4. Run the application and it will load the resources with application required components.

## Import previously generated settings into CRG

To add more components or upgrade the latest Syncfusion Blazor library resources, it is not necessary to generate from the scratch in the CRG. Just import the old **import.json** file, make the changes, and then download it again from the CRG application.

Refer to the following steps to import previous settings in CRG:

1. Click the **IMPORT SETTINGS** button at the bottom of the page.

    ![Import option in CRG](images/import-option.png)

2. Upload the **import.json** file, so that the previously stored data will be restored in the CRG application. Now, add more components and export the resources again.

    ![blazor Previous changes restored](images/previous-changes-restored.png)
