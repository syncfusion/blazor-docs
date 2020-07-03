# Step Area

## Step Area

Like the step line chart, but with the areas connected with lines shaded. To render a step area series, use series [`Type`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartSeries~Type.html) as `StepArea`.

{% aspTab template="chart/series/area-charts/steparea", sourceFiles="steparea.razor" %}

{% endaspTab %}

![Step Area](../images/chart-types-images/steparea.png)

## Customization

You can use the following properties to customize the step area series.

* [`Fill`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartSeries~Fill.html) – used to change the color of the step area.
* [`Opacity`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartSeries~Opacity.html) – used to control the transparency of the chart series.
* [``DashArray``](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartSeries~DashArray.html) – used to render step area series with dashes.
* [`Border`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartSeries~Border.html) – used to render step area series with border.

```csharp
@using Syncfusion.Blazor.Charts

<SfChart Width="60%">
    <ChartSeriesCollection>
        <ChartSeries DataSource="@WeatherReports" DashArray="5,5" Opacity="0.5" Fill="blue" XName="X" YName="Y" Type="ChartSeriesType.StepArea">
            <ChartSeriesBorder Width="2" Color="black"></ChartSeriesBorder>
        </ChartSeries>
    </ChartSeriesCollection>
</SfChart>
@code{
    public class ChartData
    {
        public string X;
        public double Low;
        public double High;
    }

    public List<ChartData> WeatherReports = new List<ChartData>
{
         new ChartData { X= "Sun", Low= 2.5, High= 9.8 },
         new ChartData { X= "Mon", Low= 4.7, High= 11.4 },
         new ChartData { X= "Tue", Low= 6.4, High= 14.4 },
         new ChartData { X= "Wed", Low= 9.6, High= 17.2 },
         new ChartData { X= "Thu", Low= 7.5, High= 15.1 },
         new ChartData { X= "Fri", Low= 3.0, High= 10.5 },
         new ChartData { X= "Sat", Low= 1.2, High= 7.9 }
    };
}
```

![Custom Step Area](../images/chart-types-images/custom-step-area.png)

## See Also

* [Data label](../data-labels)
* [Tooltip](../tool-tip)