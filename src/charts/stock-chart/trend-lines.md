# Trendlines

Trendlines are used to show the direction and speed of price.

Stock Chart supports 6 types of trendlines namely `Linear`,`Exponential`,`Logarithmic`,`Polynomial`,`Power`,`Moving Average`. By using trendline dropdown button you can add or remove the required trendline type.

## Linear

A linear trendline is a best fit straight line that is used with simpler data sets. To render a linear trendline,
use trendline [`Type`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.StockChartTrendline.html#Syncfusion_Blazor_Charts_StockChartTrendline_Type) as `Linear`.

{% aspTab template="stock-chart/trendlines", sourceFiles="linear.razor" %}

{% endaspTab %}

![Linear](images/trendlines/linear.png)

## Logarithmic

A logarithmic trendline is a best-fit curved line that is most useful when the rate of change in the data increases or decreases quickly and then levels out. A logarithmic trendline can use negative and/or positive values.
To render a logarithmic trendline, use trendline [`Type`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.StockChartTrendline.html#Syncfusion_Blazor_Charts_StockChartTrendline_Type) as `Logarithmic`.

{% aspTab template="stock-chart/trendlines", sourceFiles="logarithmic.razor" %}

{% endaspTab %}

![Logarithmic](images/trendlines/logarithmic.png)

## Exponential

An exponential trendline is a curved line that is most useful when data values rise or fall at increasingly higher rates. You cannot create an exponential trendline, if your data contains zero or negative values.
To render a exponential trendline,
use trendline [`Type`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.StockChartTrendline.html#Syncfusion_Blazor_Charts_StockChartTrendline_Type) as `Exponential`.

{% aspTab template="stock-chart/trendlines", sourceFiles="exponential.razor" %}

{% endaspTab %}

![Exponential](images/trendlines/exponential.png)

## Polynomial

A polynomial trendline is a curved line that is used when data fluctuates.
to render a polynomial trendline,
use trendline [`Type`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.StockChartTrendline.html#Syncfusion_Blazor_Charts_StockChartTrendline_Type) as `Polynomial`.
`PolynomialOrder` used to define the polynomial value.

{% aspTab template="stock-chart/trendlines", sourceFiles="polynomial.razor" %}

{% endaspTab %}

![Polynomial](images/trendlines/polynomial.png)

## Power

A power trendline is a curved line that is best used with data sets that compare measurements that increase at a specific rate.
To render a power trendline, use trendline [`Type`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.StockChartTrendline.html#Syncfusion_Blazor_Charts_StockChartTrendline_Type) as `Power`.

## Moving Average

A moving average trendline smoothen out fluctuations in data to show a pattern or trend more clearly.
To render a moving average trendline, use trendline [`Type`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.StockChartTrendline.html#Syncfusion_Blazor_Charts_StockChartTrendline_Type) as `MovingAverage`.

`Period` property defines the period to find the moving average.

{% aspTab template="stock-chart/stockchart-feature/trendlines", sourceFiles="trendlines.razor" %}

{% endaspTab %}

![Trendline](images/common/trendlines.png)

## Customization of Trendline

The [`Fill`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.StockChartTrendline.html#Syncfusion_Blazor_Charts_StockChartTrendline_Fill) and [`Width`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.StockChartTrendline.html#Syncfusion_Blazor_Charts_StockChartTrendline_Width) properties are used to customize the appearance of the trendline.

{% aspTab template="stock-chart/stockchart-feature/customtrendlines", sourceFiles="customtrendlines.razor" %}

{% endaspTab %}

![Trendline Customization](images/common/custom-trendlines.png)