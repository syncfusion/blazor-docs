---

component: "Chart"

---

# Lazy loading

Lazy loading allows you to load data for chart on demand. Chart will fire the `OnScrollChanged` event, in that we can get the minimum and maximum range of the axis, based on this, we can upload the data to chart.

```razor
   <ChartEvents OnScrollChanged="@ScrollChange"></ChartEvents>

  void ScrollChange(ScrollEventArgs e)
    {
        this.dataSource = GetRangeData(Convert.ToInt32(e.CurrentRange.Minimum), Convert.ToInt32(e.CurrentRange.Maximum));
        this.StateHasChanged();
    }

```

{% aspTab template="chart/how-to/lazy-loading", sourceFiles="lazy-loading.razor" %}

{% endaspTab %}