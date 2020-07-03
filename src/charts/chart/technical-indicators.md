---
title: " Chart Technical Indicators | ASP.NET Core Blazor "

component: "Chart"

description: "Indicators represent a statistical approach to technical analysis as opposed to a subjective approach. we have different types of indicators."
---

<!-- markdownlint-disable MD036 -->

# Technical Indicators

A technical indicator is a mathematical calculation based on historic price, volume or open interest information
that aims to forecast financial market direction.

Chart supports 10 types of technical indicators.

## Accumulation Distribution

Accumulation Distribution combines price and volume to show how money may be flowing into or out of stock.
To render a Accumulation Distribution Indicator,
use indicator [`Type`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartIndicator~Type.html) as `AccumulationDistribution`.
To calculate the signal line [`Volume`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartIndicator~Volume.html) field is additionally added with `DataSource`.

{% aspTab template="chart/technical-indicators/ad", sourceFiles="ad.razor" %}

{% endaspTab %}

![Accumulation Distribution](images/technical-indicator/ad-razor.png)

## Average True Range (ATR)

ATR measures the stock volatility by comparing the current value with the
previous value. To render a Average True Range (ATR) Indicator,
use indicator [`Type`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartIndicator~Type.html) as `Atr`.
{% aspTab template="chart/technical-indicators/atr", sourceFiles="atr.razor" %}

{% endaspTab %}

## Bollinger Band

A chart overlay that shows the upper and lower limits of normal price movements based on the standard deviation of prices.
To render a Bollinger Band, use indicator [`Type`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartIndicator~Type.html) as `BollingerBands`.
Bollinger band will be represented by three lines (upperLine, lowerLine, signalLine).Bollinger Band
default values of the [`Period`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartIndicator~Period.html) is 14 and
[`StandardDeviations`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartIndicator~StandardDeviation.html) is 2.

{% aspTab template="chart/technical-indicators/bollinger", sourceFiles="bollinger.razor" %}

{% endaspTab %}

**Customization of BollingerBand**

`Stroke`, `StrokeWidth`, and `Color` of upperLine can be customized by using,[`UpperLine`](./https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartIndicator~UpperLine.html),
and the lowerLine can be customized by using [`LowerLine`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartIndicator~LowerLine.html) properties of indicator.

{% aspTab template="chart/technical-indicators/custom-bollinger", sourceFiles="custom-bollinger.razor" %}

{% endaspTab %}

## Exponential Moving Average (EMA)

Moving average Indicators are used to define the direction of the trend. To render a EMA Indicator,
use indicator [`Type`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartIndicator~Type.html) as `Ema`.
{% aspTab template="chart/technical-indicators/ema", sourceFiles="ema.razor" %}

{% endaspTab %}

## Momentum

Momentum shows the speed at which the price of the stock is changing. To render a Momentum indicator, use indicator
[`Type`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartIndicator~Type.html) as `Momentum`. Momentum indicator will be represented by two lines (upperLine,
signalLine).In momentum indicator the upperBand value is always render at the value 100.

{% aspTab template="chart/technical-indicators/momentum", sourceFiles="momentum.razor" %}

{% endaspTab %}

**Customization of MomentumIndicator**

`Stroke`, `StrokeWidth`, and `Color` of upperLine can be customized by using,[`UpperLine`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartIndicator~UpperLine.html),
property of indicator.

{% aspTab template="chart/technical-indicators/custom-momentum", sourceFiles="custom-momentum.razor" %}

{% endaspTab %}

## Moving Average Convergence Divergence (MACD)

MACD is based on the difference between two EMA's. To render a MACD Indicator, use indicator [`Type`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartIndicator~Type.html) as
`Macd`.MACD indicator will be represented
by MACD line,signal line, MACD histogram. MACD histogram is used to differentiate MACD line and signal line.

{% aspTab template="chart/technical-indicators/macd", sourceFiles="macd.razor" %}

{% endaspTab %}

**Customization of MACD**

`Stroke`, `StrokeWidth`, and `Color`of macdLine can be customized by using,[`MacdLine`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartIndicator~MacdLine.html),
property of indicator. The positive and negative changes of histogram can be customized by [`MacdPositiveColor`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartIndicator~MacdPositiveColor.html)
and [`MacdNegativeColor`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartIndicator~MacdNegativeColor.html) properties.
The [`MacdType`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartIndicator~MacdType.html) is used to define the type of
MACD indicator. To customize the MACD period using [`SlowPeriod`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartIndicator~SlowPeriod.html) and [`FastPeriod`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartIndicator~FastPeriod.html)
properties.

{% aspTab template="chart/technical-indicators/custom-macd", sourceFiles="custom-macd.razor" %}

{% endaspTab %}

## Relative Strength Index (RSI)

RSI shows how strongly a stock is moving in its current direction. To render a RSI Indicator, use
indicator [`Type`](./https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartIndicator~Type.html) as `Rsi`.RSI indicator will be represented
by three lines (upperBand, lowerBand, signalLine). The upperBand and lowerBand values are customized by
[`OverBought`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartIndicator~OverBought.html)
and [`OverSold`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartIndicator~OverSold.html)
properties of indicator and the signalLine is calculated by RSI formula.

## Simple Moving Average (SMA)

Moving average Indicators are used to define the direction of the trend. To render a SMA Indicator,
use indicator [`Type`](./https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartIndicator~Type.html) as
`Sma`.

## Stochastic

It shows how a stock is, when compared to previous state. To render a Stochastic indicator,
use indicator [`Type`](./https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartIndicator~Type.html) as `Stochastic`.
stochastic indicator will be represented by four lines (upperLine, lowerLine, periodLine, signalLine).
In stochastic indicator the upperBand value and lowerBand value is customized by [`OverBought`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartIndicator~OverBought.html)
and [`OverBought`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartIndicator~OverBought.html)properties of indicators and the periodLine and
signalLine is render based on stochastic formula.

**Customization of StochasticIndicator**

`Stroke`, `StrokeWidth`, and `Color` of upperLine can be customized by using,[`UpperLine`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartIndicator~UpperLine.html),
the lowerLine can be customized by using [`LowerLine`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartIndicator~LowerLine.html)
and the periodLine can be customized by using [`PeriodLine`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartIndicator~PeriodLine.html)
properties of indicator. To customize the period to find the average price
using [`KPeriod`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartIndicator~KPeriod.html)
and [`DPeriod`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartIndicator~DPeriod.html)
properties.

{% aspTab template="chart/technical-indicators/custom-stochastic", sourceFiles="custom-stochastic.razor" %}

{% endaspTab %}

## Triangular Moving Average (TMA)

Moving average indicators are used to define the direction of the trend. To render a TMA Indicator,
use indicator [`Type`](./https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartIndicator~Type.html) as
`TMA`.

**Customization of Technical Indicators**

`Stroke`, `StrokeWidth`, and `Color` of signalLine can be customized by using,[`Fill`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartIndicator~Fill.html),
[`Width`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartIndicator~Width.html)
and [`DashArray`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartIndicator~DashArray.html)
properties and the [`Period`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartIndicator~Period.html)
property is used to predict the data forecast calculations. The [`Field`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartIndicator~Field.html)
value is used to the compare the current price with previous price. It is applicable to Bollinger bands and moving
averages. The [`ShowZones`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartIndicator~ShowZones.html)
property is used to shows/Hides the overBought and overSold regions. It is applicable for RSI and stochastic indicators.

{% aspTab template="chart/technical-indicators/custom-tma", sourceFiles="custom-tma.razor" %}

{% endaspTab %}

**Data Source**

Usually technical indicators are added along with a financial series. The [`SeriesName`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartIndicator~SeriesName.html)
represents the series, the data of which has to be analysed through indicators.

Technical indicators can also be added without series using [`DataSource`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/aspnetcore/Syncfusion.EJ2~Syncfusion.EJ2.Charts.ChartIndicator~DataSource.html) property of indicator.

{% aspTab template="chart/technical-indicators/datasource", sourceFiles="datasource.razor" %}

{% endaspTab %}

## See Also

* [Data label](./data-labels)
* [Tooltip](./tool-tip)
* [Legend](./legend)