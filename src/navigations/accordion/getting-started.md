---
title: "Getting Started"
component: "Accordion"
description: "Rendering Accordion using Blazor."
---

# Getting Started

This section briefly explains about how to include a `Accordion` in your Blazor server-side application. You can refer [Getting Started with Syncfusion Blazor for Server-Side in Visual Studio 2019](../getting-started/server-side-blazor/) page for the introduction and configuring the common specifications.

## Importing Syncfusion Blazor component in the application

1. Install **Syncfusion.Blazor** NuGet package to the application by using the `NuGet Package Manager`.

2. You can add the client-side resources through CDN or from NuGet package in the `<head>` element of the **~/Pages/_Host.cshtml** page.

 ```html
    <head>
        ...
            <link href="_content/Syncfusion.Blazor/styles/bootstrap4.css" rel="stylesheet" />
            @*<link href="https://cdn.syncfusion.com/blazor/{{version}}/styles/{{theme}}.css" rel="stylesheet" />*@
        ...
    </head>
```

> For Internet Explorer 11 kindly refer the polyfills. Refer the [documentation](../../common/how-to/render-blazor-server-app-in-ie/) for more information.

 ```html
    <head>
        ...
            <link href="https://cdn.syncfusion.com/blazor/{{version}}/styles/{{theme}}.css" rel="stylesheet" />
            <script src="https://github.com/Daddoon/Blazor.Polyfill/releases/download/3.0.1/blazor.polyfill.min.js"></script>
        ..
    </head>
```

## Adding component package to the application

Open `~/_Imports.razor` file and import the `Syncfusion.Blazor.Navigations` package.

```csharp
    @using Syncfusion.Blazor.Navigations
```

## Add SyncfusionBlazor service in Startup file

Open the **Startup.cs** file and add services required by Syncfusion components using  **services.AddSyncfusionBlazor()** method. Add this method in the **ConfigureServices** function as follows.

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

> To enable custom client side resource loading from CRG or CDN. You need to disable resource loading by `AddSyncfusionBlazor(true)` and load the scripts in the HEAD element of the `~/Pages/_Host.cshtml` page.

 ```html
    <head>
        ...
            <link href="https://cdn.syncfusion.com/blazor/{{version}}/styles/{{theme}}.css" rel="stylesheet" />
            <script src="https://cdn.syncfusion.com/blazor/{:version:}/syncfusion-blazor.min.js"></script>
        ...
    </head>
```

## Adding Accordion component to the application

Now, add the Syncfusion Blazor Accordion component in any web page (razor) in the `Pages` folder. For example, the Accordion component is added in the `~/Pages/Index.razor` page.

```csharp
@using Syncfusion.Blazor.Navigations

<SfAccordion>
    <AccordionItems>
        <AccordionItem Header="Margeret Peacock" Content="Margeret Peacock was born on Saturday , 01 December 1990. Now lives at Coventry House Miner Rd., London,UK. Margeret Peacock holds a position of Sales Coordinator in our WA department, (Seattle USA). Joined our company on Saturday , 01 May 2010"></AccordionItem>
        <AccordionItem Header="Laura Callahan" Content="Laura Callahan was born on Tuesday , 06 November 1990. Now lives at Edgeham Hollow Winchester Way, London,UK. Laura Callahan holds a position of Sales Coordinator in our WA department, (Seattle USA). Joined our company on Saturday , 01 May 2010"></AccordionItem>
        <AccordionItem Header="Albert Dodsworth" Content="Albert Dodsworth was born on Thursday , 19 October 1989. Now lives at 4726 - 11th Ave. N.E., Seattle,USA.Albert Dodsworth holds a position of Sales Representative in our WA department, (Seattle USA). Joined our company on Friday , 01 May 2009"></AccordionItem>
    </AccordionItems>
</SfAccordion>
```

## Run the application

After successful compilation of your application, simply press `F5` to run the application.

![Default Accordion](./images/browser-output.png)

## Initialize Accordion using Template

The following code explains how to initialize accordion using `Template`.

```csharp
@using Syncfusion.Blazor.Navigations

<SfAccordion>
    <AccordionItems>
        <AccordionItem>
            <HeaderTemplate>
                <div>Margeret Peacock</div>
            </HeaderTemplate>
            <ContentTemplate>
                <div class='container'><img src='images/margeret.png' /><div class='content'><b>Margeret Peacock</b> was born on Saturday , 01 December 1990. Now lives at Coventry House Miner Rd., London,UK. Margeret Peacock holds a position of <b>Sales Coordinator</b> in our WA department, (Seattle USA). Joined our company on Saturday , 01 May 2010.</div></div>">
            </ContentTemplate>
        </AccordionItem>
        <AccordionItem>
            <HeaderTemplate>
                <div>Laura Callahan</div>
            </HeaderTemplate>
            <ContentTemplate>
                <div class='container'><img src='images/laura.png'/><div class='content'><b>Laura Callahan</b> was born on Tuesday , 06 November 1990. Now lives at Edgeham Hollow Winchester Way, London,UK. Laura Callahan holds a position of <b>Sales Coordinator</b> in our WA department, (Seattle USA). Joined our company on Saturday , 01 May 2010.</div></div>
            </ContentTemplate>
        </AccordionItem>
        <AccordionItem>
            <HeaderTemplate>
                <div>Albert Dodsworth</div>
            </HeaderTemplate>
            <ContentTemplate>
                <div class='container'><img src='images/albert.png' /><div class='content'> <b>Albert Dodsworth</b> was born on Thursday , 19 October 1989. Now lives at 4726 - 11th Ave. N.E., Seattle,USA.Albert Dodsworth holds a position of <b>Sales Representative</b> in our WA department, (Seattle USA). Joined our company on Friday , 01 May 2009.</div></div>
            </ContentTemplate>
        </AccordionItem>
    </AccordionItems>
</SfAccordion>

<style>
    img {
        height: 40px;
        width: 50px;
        margin-top: 13px;
    }

    .container {
        display: inline-flex;
        width: auto;
        padding: 0;
    }

    .content {
        margin-left: 10px;
    }
</style>
```

Output be like the below.

![Accordion with template](./images/template.png)

## See Also

1. [Getting Started with Syncfusion Blazor for client-side in .NET Core CLI](../getting-started/blazor-webassembly-dotnet-cli/)
2. [Getting Started with Syncfusion Blazor for client-side in Visual Studio 2019](../getting-started/blazor-webassembly/)
3. [Getting Started with Syncfusion Blazor for server-side in .NET Core CLI](../getting-started/server-side-blazor-dotnet-cli/)
