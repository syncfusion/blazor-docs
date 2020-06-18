# How to upgrade Syncfusion Blazor Components to latest version

To upgrade Syncfusion Blazor Components to latest version, you need to ensure the following:

## Compatible .NET version

Syncfusion Blazor components in latest version `'{:nuget-version:}'` is compatible with latest version of .NET Core 3.1. So, we suggest you to upgrade the .NET Core 3.1 SDK in your machine before upgrading to latest version. Also, refer to [version compatibility](./version-compatibility) documentation for more information about version compatibility of Syncfusion Blazor components and .NET Core SDK.

## Client resource file references

Ensure our script and CSS files have been properly configured in your application. We suggest you to recheck the following client resources in your application.

If you use Blazor server app, add the following client resource file references in **~/Pages/_Host.cshtml**.

```html
    <link href="https://cdn.syncfusion.com/ej2/{:version:}/material.css" rel="stylesheet" />
    <script src="https://cdn.syncfusion.com/ej2/{:version:}/dist/ej2.min.js"></script>
    <script src="https://cdn.syncfusion.com/ej2/{:version:}/dist/ejs.interop.min.js"></script>
```

If you use Blazor WebAssembly app, add the following client resource file references in **~/wwwroot/index.html**.

```html
    <link href="https://cdn.syncfusion.com/ej2/{:version:}/material.css" rel="stylesheet" />
    <script src="https://cdn.syncfusion.com/ej2/{:version:}/dist/ej2.min.js"></script>
    <script src="https://cdn.syncfusion.com/ej2/{:version:}/dist/ejs.interop.min.js"></script>
```

> **Note:** Versions mentioned in CDN, Scripts, and Styles should be same as the NuGet version.
>
> For production purpose and minimal requirement, Syncfusion provides an option to generate scripts and styles of selective control by using the Custom Resource Generator (CRG) web tool. Refer to this [link](https://crg.syncfusion.com/) for more details on CRG.

## Breaking changes

Some changes have been modified in our Blazor samples for each release. So, we suggest you to ensure the breaking changes. Refer to this [release notes](https://ej2.syncfusion.com/blazor/documentation/release-notes/index/) for our Blazor components.

## Cache problem

Before restoring the NuGet packages, clean the old version Syncfusion.EJ2.Blazor NuGet package.

The following steps explain how to clean the cache:

1. Delete/clear the package Syncfusion.EJ2.Blazor from the installed location `{System-driver}\Users\{user-name}\.nuget\packages\syncfusion.ej2.blazor`. In Windows, the installed location of Syncfusion.EJ2.Blazor package can be found using `%userprofile%\.nuget\packages\syncfusion.ej2.blazor`.

2. Update the latest version of Syncfusion.EJ2.Blazor NuGet package.

## Linker.xml configuration

In Blazor WebAssembly application, ensure if you have configured **Linker.xml** file in your Syncfusion Blazor application. Missing this configuration may prevent the rendering of Syncfusion Blazor components in the application.

Refer to this [KB article](https://www.syncfusion.com/kb/10761/syncfusion-components-doesnt-render-in-blazor-webassembly-application) for more information on Linker.xml file usage.

> **Note:** Linker.xml configuration is applicable only for Blazor WebAssembly application.

## See Also

* [Version Compatibility](./version-compatibility)
