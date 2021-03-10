<!-- markdownlint-disable MD036 -->

# Add or remove a series from the chart dynamically

You can add or remove the chart series dynamically by using the `<ChartSeries/>` Component.

To add or remove the series dynamically, follow the given steps:

**Step 1**:

 Initially render the series using Collection.

```razor
    <SfChart>
        <ChartSeriesCollection>
            @foreach (SeriesData series in SeriesCollection)
            {
                <ChartSeries XName=@series.XName YName=@series.YName DataSource=@series.Data>
                </ChartSeries>
            }
        </ChartSeriesCollection>
    </SfChart>
  ```

**Step 2**:

To add the new series from chart dynamically, using List `Add` method.

 ```razor
    void ChartSeriesAdd()
    {
        SeriesCollection.Add(new SeriesData
        {
          XName = nameof(LineChartData.XValue),
          YName = nameof(LineChartData.YValue),
          Data = GetChartData()
        });
    }
 ```

**Step 3**:

To remove the new series from chart dynamically, using List `Remove` method.

 ```razor
    void ChartSeriesRemove()
    {
      SeriesCollection.Remove(SeriesCollection[SeriesCollection.Count - 1]);
    }
 ```

{% aspTab template="chart/how-to/add-remove", sourceFiles="add-remove.razor" %}

{% endaspTab %}

**New Note:** You can refer to our [`Blazor Charts`](https://www.syncfusion.com/blazor-components/blazor-charts) feature tour page for its groundbreaking feature representations. You can also explore our [`Blazor Chart example`](https://blazor.syncfusion.com/demos/chart/line?theme=bootstrap4) to knows various chart types and how to represent time-dependent data, showing trends in data at equal intervals.