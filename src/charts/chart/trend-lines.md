---
title: " Chart Trendlines | ASP.NET Core Blazor "

component: "Chart"

description: "Trendlines are used to show the direction and speed of price. Chart supports 6 types of trendlines and also provides trendlines customization."
---

<!-- markdownlint-disable MD036 -->

# Trendlines

Trendlines are used to show the direction and speed of price.

Trendlines can be generated for Cartesian type series (Line, Column, Scatter, Area, Candle, Hilo etc.)
except bar type series. You can add more than one trendline to a series.

Chart supports 6 types of trendlines.

## Linear

A linear trendline is a best fit straight line that is used with simpler data sets. To render a linear trendline,
use trendline [`Type`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartTrendline~Type.html) as `Linear`.

{% aspTab template="chart/trendlines", sourceFiles="linear.razor" %}

{% endaspTab %}

![Linear](images/trend-lines/linear-razor.png)

## Exponential

An exponential trendline is a curved line that is most useful when data values rise or fall
at increasingly higher rates. You cannot create an exponential trendline, if your data contains zero or negative values.

To render a exponential trendline,
use trendline [`Type`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartTrendline~Type.html) as `Exponential`.

{% aspTab template="chart/trendlines", sourceFiles="exponential.razor" %}

{% endaspTab %}

## Logarithmic

A logarithmic trendline is a best-fit curved line that is most useful when the rate of change
in the data increases or decreases quickly and then levels out.

A logarithmic trendline can use negative and/or positive values.

To render a logarithmic trendline, use trendline [`Type`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartTrendline~Type.html) as `Logarithmic`.

{% aspTab template="chart/trendlines", sourceFiles="logarithmic.razor" %}

{% endaspTab %}

## Polynomial

A polynomial trendline is a curved line that is used when data fluctuates.

To render a polynomial trendline,
use trendline [`Type`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartTrendline~Type.html) as `Polynomial`.

`PolynomialOrder` used to define the polynomial value.

{% aspTab template="chart/trendlines", sourceFiles="polynomial.razor" %}

{% endaspTab %}

## Power

A power trendline is a curved line that is best used with data sets that compare measurements that increase at a specific rate.

To render a power trendline, use trendline [`Type`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartTrendline~Type.html) as `Power`.

{% aspTab template="chart/trendlines", sourceFiles="power.razor" %}

{% endaspTab %}

## Moving Average

A moving average trendline smoothen out fluctuations in data to show a pattern or trend more clearly.

To render a moving average trendline, use trendline [`Type`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartTrendline~Type.html) as `MovingAverage`.

`Period` property defines the period to find the moving average.

{% aspTab template="chart/trendlines", sourceFiles="movingaverage.razor" %}

{% endaspTab %}

**Customization of Trendlines**

The [`Fill`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartTrendline~Fill.html)
and [`Width`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartTrendline~Width.html)
properties are used to customize the appearance of the trendline.

## Forecasting

Trendlines forecasting is the prediction of future/past situations.

Forecasting can be classified into two types as follows

Forward Forecasting
Backward Forecasting

**Forward Forecasting**

The value set for ForwardForecast is used to determine the distance moving towards the future trend.

{% aspTab template="chart/trendlines", sourceFiles="forward-forecast.razor" %}

{% endaspTab %}

**Backward Forecasting**

The value set for the BackwardForecast is used to determine the past trends.

{% aspTab template="chart/trendlines", sourceFiles="backward-forecast.razor" %}

{% endaspTab %}

## See Also

* [Data label](./data-labels)
* [Tooltip](./tool-tip)
* [Marker](./data-markers)