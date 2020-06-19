---
title: " RangeNavigator Export and Print | ASP.NET Core Blazor "

component: "RangeNavigator"

description: "The rendered rangenavigator can be printed or exported directly from the browser by calling the public method print and export."
---

# Print and Export

## Print

The rendered range navigator can be printed directly from the browser by calling the public method print. The ID of the range navigator div element must be passed as argument to that method.

{% aspTab template="range-navigator/print/print", sourceFiles="print.razor" %}

{% endaspTab %}

## Export

The rendered range navigator can be exported to JPEG, PNG, SVG, or PDF format using the export method in the range navigator. The input parameters for this method are Export Type for format and fileName for result.