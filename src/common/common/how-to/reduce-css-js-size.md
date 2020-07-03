# How to reduce the CSS/JS size in Syncfusion Blazor Components

The CDN links containing all Syncfusion Blazor components script and styles. Such CDN links are intended only to get started with any Syncfusion Blazor component, primarily by considering the novice.

Using CDN styles and scripts in real-time applications that use a very small set of Syncfusion Blazor components may have an impact on performance due to the size of the CSS/JS file that eventually increases the loading time of the application. Here, we will discuss some of the possible ways to reduce the size of CSS/JS files.

## Custom Resource Generator (CRG)

Syncfusion provides a utility application named ***[Custom Resource Generator (CRG)](https://crg.syncfusion.com/)*** to download script and style files for selected components based on our requirement.

You can find detailed information about the CRG [here](https://blazor.syncfusion.com/documentation/common/custom-resource-generator/).

Using the CSS/JS files that only contain the scripts and styles of the Syncfusion Blazor components used in an application will reduce the loading time of the application.

## Compressing the CSS/JS files

Using `gzip` compression, We can further reduce the size of the scripts and styles file after generating CSS/JS files from CRG for required Syncfusion Blazor components. The `gzip` compression is the recommended approach for production applications.

For more information regarding the IIS configuration for `gzip` files refer [here](https://docs.microsoft.com/en-us/iis/configuration/system.webserver/httpcompression/).