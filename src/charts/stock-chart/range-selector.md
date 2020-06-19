---
title: "Stock Chart Range Selector | ASP.NET Core Blazor "

component: "Stock Chart"

description: "we can able to select the particular range data by dragging thumbs or by tapping on the labels or by setting the start and end value properties. "
---

# Range selector

The range selector allows to select a range with specified periods. By default the range selector is enabled in stock chart.

# Selecting Range

The left and right thumb of RangeNavigator are used to indicate the selected range in the large collection of data. Following are the ways you can select a range.

* By dragging the thumbs.
* By tapping on the labels.
* By setting the start and end through Date Range button.

Following code example shows the [`EnableSelector`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.StockChartModel~EnableSelector.html) property allows users to toggle the visibility of enable selector.

{% aspTab template="stock-chart/getting-started/range", sourceFiles="range.razor" %}

{% endaspTab %}

![Selecting Range](images/common/range.png)