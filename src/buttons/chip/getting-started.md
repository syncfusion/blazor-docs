---
title: "Getting Started"
component: "Chip"
description: "Learn how to create an Blazor Chip control in ASP.NET Razor application."
---

# Getting Started

This section briefly explains about how to include a simple Chip in your ASP.NET Core Razor application. You can refer [ASP.NET Core Razor Getting Started documentation](../getting-started/dotnet-cli-blazor) page for introduction part of the system requirements and configure the common specifications.

## Importing Syncfusion Blazor component in the application

1. Install `Syncfusion.EJ2.Blazor` NuGet package to the application by using the NuGet Package Manager.
2. You can add the client-side resources through CDN or local npm package in the `<head>` element of the `~/wwwroot/index.html` page.

```csharp

<head>
    <link href="https://cdn.syncfusion.com/ej2/{:version:}/material.css" rel="stylesheet" />
    <script src="https://cdn.syncfusion.com/ej2/{:version:}/dist/ej2.min.js"></script>
    <script src="https://cdn.syncfusion.com/ej2/{:version:}/dist/ejs.interop.min.js"></script>
</head>

```

## Adding component package to the application

Open `~/_Imports.razor` file and import the `Syncfusion.EJ2.Blazor.Buttons` packages.

 ```csharp

@using Syncfusion.EJ2.Blazor
@using Syncfusion.EJ2.Blazor.Buttons

```

## Adding Chip component to the application

Now, add the Syncfusion Blazor Chip component in any web page `razor` in the `Pages` folder. For example, the Chip component is added in the `~/Pages/Index.razor` page.

```csharp

    @using Syncfusion.EJ2.Blazor.Buttons

    <EjsChipList Text="Janet Leverling"></EjsChipList>

```

## Run the application

 After successful compilation of your application, simply press `F5` to run the application.

Output be like the below.

![Chip Sample](./images/chip.png)

## See Also

[Getting Started with Syncfusion Blazor for Client-Side in Visual Studio 2019 Preview](https://ej2.syncfusion.com/aspnet-core-blazor/documentation/getting-started/vs-blazor/)

[Getting Started with Syncfusion Blazor for Server-Side in Visual Studio 2019 Preview](https://ej2.syncfusion.com/aspnet-core-blazor/documentation/getting-started/vs-blazor-server/)

[Getting Started with Syncfusion Blazor for Server-Side in .NET Core CLI](https://ej2.syncfusion.com/aspnet-core-blazor/documentation/getting-started/dotnet-cli-blazor-server/)