---
title: "Upgrade Application To Latest Version"
component: "DataGrid"
description: "Documentation on how to upgrade an application to latest Syncfusion version"
---

# Upgrade Application To Latest Version

**Step 1:** Update the latest Syncfusion blazor [`nuget`](https://www.nuget.org/packages/Syncfusion.Blazor/) from Nuget package manager in your application.

![update syncfusion blazor nuget](../images/upgrade-version.PNG)

**Step 2:** Refer the corresponding Nuget version script files and styles in **~/Pages/_Host.cshtml** page.

```csharp
    <link href="https://cdn.syncfusion.com/blazor/{:version:}/styles/fabric.css" rel="stylesheet" />
    <script src="https://cdn.syncfusion.com/blazor/{:version:}/dist/blazor.min.js"></script>
    <script src="https://cdn.syncfusion.com/blazor/{:version:}/dist/ejs.interop.min.js"></script>
```

> For Blazor client-side web application, include the above scripts and styles in **~/Pages/index.html** page.