# How to upgrade Syncfusion Blazor Components to the latest version

To upgrade Syncfusion Blazor Components to the latest version, you need to ensure the following:

## Compatible .NET version

Syncfusion Blazor components in the latest version `'{:nuget-version:}'` are compatible with the latest version of .NET Core 3.1. So, we suggest you to upgrade the .NET Core 3.1 SDK in your machine before upgrading to the latest version. Also, refer to [version compatibility](./version-compatibility) documentation for more information about version compatibility of Syncfusion Blazor components and .NET Core SDK.

## Client resource file references

Ensure our CSS files have been properly configured in your application.

* If you use the Blazor server app, add the following style file references in **~/Pages/_Host.cshtml**.

* If you use the Blazor WebAssembly app, add the following style file references in **~/wwwroot/index.html**.

```html
    <link href="_content/Syncfusion.Blazor/styles/bootstrap4.css" rel="stylesheet" />
```

> For production purpose and minimal requirement, Syncfusion provides an option to generate scripts and styles of selective control by using the Custom Resource Generator (CRG) web tool. Refer to this [link](https://crg.syncfusion.com/) for more details on CRG.

## Breaking changes

Some changes have been modified in our Blazor samples for each release. So, we suggest you to ensure the breaking changes. Refer to this [release notes](https://blazor.syncfusion.com/documentation/release-notes/index/) for our Blazor components.

## Cache problem

Before restoring the NuGet packages, clean the old version Syncfusion.Blazor NuGet package.

The following steps explain how to clean the cache:

1. Delete/clear the package Syncfusion.Blazor from the installed location `{System-driver}\Users\{user-name}\.nuget\packages\syncfusion.blazor`. In Windows, the installed location of Syncfusion.Blazor package can be found using `%userprofile%\.nuget\packages\syncfusion.blazor`.

2. Update the latest version of Syncfusion.Blazor NuGet package.

## Linker.xml configuration

In Blazor WebAssembly application, ensure if you have configured **Linker.xml** file in your Syncfusion Blazor application. Missing this configuration may prevent the rendering of Syncfusion Blazor components in the application.

Refer to this [KB article](https://www.syncfusion.com/kb/10761/syncfusion-components-doesnt-render-in-blazor-webassembly-application) for more information on Linker.xml file usage.

> **Note:** Linker.xml configuration is applicable only for the Blazor WebAssembly application.

## See Also

* [Version Compatibility](./version-compatibility)
