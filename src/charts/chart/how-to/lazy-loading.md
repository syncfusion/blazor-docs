---
title: " Chart Lazy Loading | ASP.NET Core Blazor "

component: "Chart"

description: "Chart can be rendered by using different types of data source. Lazy loading explains that allows you to load data for chart on demand"
---

# Lazy loading

Lazy loading allows you to load data for chart on demand. Chart will fire the `ScrollEnd` event, in that we can get the minimum and maximum range of the axis, based on this, we can upload the data to chart.

```razor
   <ChartEvents OnScrollEnd="@ScrollChange"></ChartEvents>

  void ScrollChange(IScrollEventArgs e)
    {
        this.dataSource = GetRangeData(Convert.ToInt32(e.CurrentRange.Minimum), Convert.ToInt32(e.CurrentRange.Maximum));
        this.StateHasChanged();
    }

```

{% aspTab template="chart/how-to/lazy-loading", sourceFiles="lazy-loading.razor" %}

{% endaspTab %}