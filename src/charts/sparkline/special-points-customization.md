# Special Points Customization

## Add custom color for special points

You can customize the points by initializing the point colors. This customization is only applicable for line, column, and area type Sparkline Charts.

The customization options allows to differentiate the following cases.

* [`StartPointColor`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.SfSparkline%601~StartPointColor.html)
* [`EndPointColor`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.SfSparkline%601~EndPointColor.html)
* [`NegativePointColor`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.SfSparkline%601~NegativePointColor.html)
* [`LowPointColor`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.SfSparkline%601~LowPointColor.html)
* [`HighPointColor`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.SfSparkline%601~HighPointColor.html)

```csharp
@using Syncfusion.Blazor.Charts

<SfSparkline XName="CarName"
              YName="Rating"
              Width="130px"
              Height="150px"
              TValue="CarRating"
              DataSource="CarRatings"
              Type="SparklineType.Column"
              HighPointColor="blue"
              LowPointColor="orange"
              StartPointColor="green"
              EndPointColor="green"
              NegativePointColor="red"
              ValueType="SparklineValueType.Category">
</SfSparkline>

@code {
    public class CarRating
    {
        public string CarName;
        public double Rating;
    };
    private List<CarRating> CarRatings = new List<CarRating> {
        new CarRating { CarName= "AUDI", Rating= 1 },
        new CarRating { CarName= "BMW", Rating= 5 },
        new CarRating { CarName= "BUICK", Rating= -1 },
        new CarRating { CarName= "CETROEN", Rating= -6 },
        new CarRating { CarName= "CHEVROLET", Rating= 0.01 },
        new CarRating { CarName= "FIAT", Rating= 1 },
        new CarRating { CarName= "FORD", Rating= -2 },
        new CarRating { CarName= "HONDA", Rating= 7 },
        new CarRating { CarName= "HYUNDAI", Rating= -9 },
        new CarRating { CarName= "JEEP", Rating= 0.01 },
        new CarRating { CarName= "KIA", Rating= -10 },
        new CarRating { CarName= "MAZDA", Rating= 3 }
    };
}
```

![Sparkline Charts with point customization](./images/SpecialPoints/SpecialPointCustomization.png)

## Tie point color

Tie point color is used to configure the win-loss series type Sparkline Chart's y-value point color. The following code sample demonstrates the [`TiePointColor`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.SfSparkline%601~TiePointColor.html) of Sparkline Charts series.

```csharp
@using Syncfusion.Blazor.Charts

<SfSparkline Width="130px"
              Height="150px"
              DataSource="new int[]{12, 15, -10, 13, 15, 6, -12, 17, 13, 0, 8, -10}"
              Type="SparklineType.WinLoss"
              TiePointColor="blue">
</SfSparkline>
```

![Sparkline Charts with tie point color](./images/SpecialPoints/TiePoint.png)