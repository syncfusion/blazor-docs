# Sparkline Dimensions

## Size for container

The Sparkline Charts can be rendered to its container size. You can set the size through inline or CSS as demonstrated in the following code.

```csharp
@using Syncfusion.Blazor.Charts

<div style="width:650px; height:350px;">
    <SfSparkline XName="Year" YName="Population" TValue="PopulationReport" DataSource="PopulationData"></SfSparkline>
</div>

@code {
    public class PopulationReport
    {
        public int Year;
        public int Population;
    };
    private List<PopulationReport> populationData = new List<PopulationReport> {
        new  PopulationReport { Year= 2005, Population= 20090440 },
        new  PopulationReport { Year= 2006, Population= 20264080 },
        new  PopulationReport { Year= 2007, Population= 20434180 },
        new  PopulationReport { Year= 2008, Population= 21007310 },
        new  PopulationReport { Year= 2009, Population= 21262640 },
        new  PopulationReport { Year= 2010, Population= 21515750 },
        new  PopulationReport { Year= 2011, Population= 21766710 },
        new  PopulationReport { Year= 2012, Population= 22015580 },
        new  PopulationReport { Year= 2013, Population= 22262500 },
        new  PopulationReport { Year= 2014, Population= 22507620 }
    };
}
```

![Sparkline Charts with Container Sample](./images/SparklineDimension/ContainerSize.png)

## Size for sparkline

You can also set the size for Sparkline Charts directly using the [`Width`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SfSparkline-1.html#Syncfusion_Blazor_Charts_SfSparkline_1_Width) and [`Height`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SfSparkline-1.html#Syncfusion_Blazor_Charts_SfSparkline_1_Height) properties.

### In pixel

You can set the size for Sparkline Charts in pixels as demonstrated in the following code.

```csharp
@using Syncfusion.Blazor.Charts

<SfSparkline XName="Year"
              YName="Population"
              TValue="PopulationReport"
              DataSource="PopulationData"
              Width="350px"
              Height="150px">
</SfSparkline>
```

> Refer [code block](#size-for-container) to know the property value of `populationData`.

![Sparkline Charts with size in pixel](./images/SparklineDimension/Inpixel.png)

### In percentage

By setting values in percentage, the Sparkline Charts get their dimension with respect to their containers. For example, when the height is set to ‘50%’, Sparkline Chart is rendered to half of its container width.

```csharp
@using Syncfusion.Blazor.Charts

<div style="width:650px; height:350px;">
    <SfSparkline XName="Year"
                  YName="Population"
                  TValue="PopulationReport"
                  DataSource="PopulationData"
                  Width="50%"
                  Height="80%">
    </SfSparkline>
</div>
```

> Refer [code block](#size-for-container) to know the property value of `populationData`.

![Sparkline Charts with size in percentage](./images/SparklineDimension/Inpercentage.png)

**New Note:** You can refer to our [`Blazor Charts`](https://www.syncfusion.com/blazor-components/blazor-charts) feature tour page for its groundbreaking feature representations. You can also explore our [`Blazor Chart example`](https://blazor.syncfusion.com/demos/chart/line?theme=bootstrap4) to knows various chart types and how to represent time-dependent data, showing trends in data at equal intervals.