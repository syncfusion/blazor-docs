---
title: "Stock Chart Tooltip   | ASP.NET Core Blazor "

component: "Stock Chart"

description: "Tooltip is used to show the data value when mouse hover on the stockchart.We can able to customize format,template and appearance."
---

# Tooltip

<!-- markdownlint-disable MD036 -->

Stock Chart will display details about the points through tooltip, when the mouse is moved over the point.

## Default Tooltip

By default, tooltip is not visible. Enable the tooltip by setting
[`Enable`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.StockChartTooltipSettings~Enable.html) property to true .

{% aspTab template="stock-chart/stockchart-feature/tooltip", sourceFiles="tooltip.razor" %}

{% endaspTab %}

![Tooltip](images/common/tooltip.png)

<!-- markdownlint-disable MD013 -->

## Format the Tooltip

<!-- markdownlint-disable MD013 -->

By default, tooltip shows information of x and y value in points. In addition to that, you can show more information in tooltip. For example the format `${point.x} : ${point.high}` shows point x and high value.

{% aspTab template="stock-chart/stockchart-feature/format", sourceFiles="format.razor" %}

{% endaspTab %}

## Customize the Appearance of Tooltip

The [`Fill`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.StockChartTooltipSettings~Fill.html) and [`Border`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.StockChartTooltipSettings~Border.html) properties are used to customize the background color and border of the tooltip respectively. The [`TextStyle`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.StockChartTooltipSettings~TextStyle.html) property in the tooltip is used to customize the font of the tooltip text.

{% aspTab template="stock-chart/stockchart-feature/customtooltip", sourceFiles="customtooltip.razor" %}

{% endaspTab %}

![Tooltip Customization](images/common/custom-tooltip.png)
