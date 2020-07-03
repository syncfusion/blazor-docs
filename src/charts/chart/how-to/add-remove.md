---
title: " Chart How To | ASP.NET Core Blazor "

component: "Chart"

description: "How to section explains knowledge base samples and howto access different types properties and events of the chart."
---

<!-- markdownlint-disable MD036 -->

# Add or remove a series from the chart dynamically

You can add or remove the chart series dynamically by using the `AddSeries` or `RemoveSeries` method.

To add or remove the series dynamically, follow the given steps:

**Step 1**:

To add a new series to chart dynamically, pass the series value to the `AddSeries` method.

```razor
 public void AddChartSeries()
    {
        List<ChartSeries>seriesCollection = new List<ChartSeries>();
        seriesCollection.Add(new ChartSeries { Name = nameof(MyDataModel.XValue), XName = nameof(MyDataModel.XValue), YName = nameof(MyDataModel.YValue), DataSource = this.GetData(), Fill = colors[rnd.Next(colors.Length - 1)], Animation = new ChartSeriesAnimation { Enable = false } });
        Chartobj.AddSeries(seriesCollection);
    }

  ```

**Step 2**:
To remove the new series from chart dynamically, pass the series index to the `RemoveSeries` method.

 ```razor
    public void RemoveChartSeries()
    {
        Chartobj.RemoveSeries(Chartobj.Series.Count - 1);
    }
 ```

{% aspTab template="chart/how-to/add-remove", sourceFiles="add-remove.razor" %}

{% endaspTab %}
