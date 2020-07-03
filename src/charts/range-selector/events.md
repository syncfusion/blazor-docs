---
title: "Events"
component: "Range Navigator"
description: "Learn how to use events in Blazor Range Navigator component."
---

# Events

In this section, we have provided the list of events of Range Navigator component which will be
triggered for appropriate range navigator actions.

The events should be provided to the Range Navigator using **RangeNavigatorEvents** component.

The following are the number of events supported for Range Navigator component.

* [Loaded](events/#loaded)
* [OnPrint](events/#onprint)
* [Changed](events/#changed)
* [Resized](events/#resized)

## Loaded

[`Loaded`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.RangeNavigatorEvents~Loaded.html) event triggers after range navigator is rendered.

```csharp
@using Syncfusion.Blazor.Charts

<SfRangeNavigator Value="@Value" ValueType="Syncfusion.Blazor.Charts.RangeValueType.DateTime" IntervalType="RangeIntervalType.Years">
    <RangeNavigatorEvents Loaded="RangeNavigatorLoaded"></RangeNavigatorEvents>
    <RangeNavigatorSeriesCollection>
        <RangeNavigatorSeries DataSource="@StockDetails" XName="Date" Type="RangeNavigatorType.Line"
                              YName="Close"></RangeNavigatorSeries>
    </RangeNavigatorSeriesCollection>
</SfRangeNavigator>

@code {

    public void RangeNavigatorLoaded(IRangeLoadedEventArgs args)
    {
        // Here you can customize your code
    }

    DateTime[] Value = new DateTime[] { new DateTime(2006, 01, 01), new DateTime(2008, 01, 01) };

    public class Data
    {
        public DateTime Date;
        public double Close;
    }
    public List<Data> StockDetails = new List<Data>
{
        new Data { Date = new DateTime(2005, 01, 01), Close = 21 },
        new Data { Date = new DateTime(2006, 01, 01), Close = 24 },
        new Data { Date = new DateTime(2007, 01, 01), Close = 36 },
        new Data { Date = new DateTime(2008, 01, 01), Close = 38 },
        new Data { Date = new DateTime(2009, 01, 01), Close = 54 },
        new Data { Date = new DateTime(2010, 01, 01), Close = 57 },
        new Data { Date = new DateTime(2011, 01, 01), Close = 70 }
    };
}
```

## OnPrint

[`OnPrint`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.RangeNavigatorEvents~OnPrint.html) event triggers before range navigator prints get started.

```csharp
@using Syncfusion.Blazor.Charts

<SfRangeNavigator Value="@Value" ValueType="Syncfusion.Blazor.Charts.RangeValueType.DateTime" IntervalType="RangeIntervalType.Years">
    <RangeNavigatorEvents OnPrint="PrintHandler"></RangeNavigatorEvents>
    <RangeNavigatorSeriesCollection>
        <RangeNavigatorSeries DataSource="@StockDetails" XName="Date" Type="RangeNavigatorType.Line"
                              YName="Close"></RangeNavigatorSeries>
    </RangeNavigatorSeriesCollection>
</SfRangeNavigator>

@code {

    public void PrintHandler(IPrintEventArgs args)
    {
        // Here you can customize your code
    }

    DateTime[] Value = new DateTime[] { new DateTime(2006, 01, 01), new DateTime(2008, 01, 01) };

    public class Data
    {
        public DateTime Date;
        public double Close;
    }
    public List<Data> StockDetails = new List<Data>
{
        new Data { Date = new DateTime(2005, 01, 01), Close = 21 },
        new Data { Date = new DateTime(2006, 01, 01), Close = 24 },
        new Data { Date = new DateTime(2007, 01, 01), Close = 36 },
        new Data { Date = new DateTime(2008, 01, 01), Close = 38 },
        new Data { Date = new DateTime(2009, 01, 01), Close = 54 },
        new Data { Date = new DateTime(2010, 01, 01), Close = 57 },
        new Data { Date = new DateTime(2011, 01, 01), Close = 70 }
    };
}
```

## Changed

[`Changed`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.RangeNavigatorEvents~Changed.html) event triggers after slider is changed.

```csharp
@using Syncfusion.Blazor.Charts

<SfRangeNavigator Value="@Value" ValueType="Syncfusion.Blazor.Charts.RangeValueType.DateTime" IntervalType="RangeIntervalType.Years">
    <RangeNavigatorEvents Changed="SliderChanged"></RangeNavigatorEvents>
    <RangeNavigatorSeriesCollection>
        <RangeNavigatorSeries DataSource="@StockDetails" XName="Date" Type="RangeNavigatorType.Line"
                              YName="Close"></RangeNavigatorSeries>
    </RangeNavigatorSeriesCollection>
</SfRangeNavigator>

@code {

    public void SliderChanged(IChangedEventArgs args)
    {
        // Here you can customize your code
    }

    DateTime[] Value = new DateTime[] { new DateTime(2006, 01, 01), new DateTime(2008, 01, 01) };

    public class Data
    {
        public DateTime Date;
        public double Close;
    }
    public List<Data> StockDetails = new List<Data>
{
        new Data { Date = new DateTime(2005, 01, 01), Close = 21 },
        new Data { Date = new DateTime(2006, 01, 01), Close = 24 },
        new Data { Date = new DateTime(2007, 01, 01), Close = 36 },
        new Data { Date = new DateTime(2008, 01, 01), Close = 38 },
        new Data { Date = new DateTime(2009, 01, 01), Close = 54 },
        new Data { Date = new DateTime(2010, 01, 01), Close = 57 },
        new Data { Date = new DateTime(2011, 01, 01), Close = 70 }
    };
}
```

## Resized

[`Resized`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.RangeNavigatorEvents~Resized.html) event triggers after range navigator is resized.

```csharp
@using Syncfusion.Blazor.Charts

<SfRangeNavigator Value="@Value" ValueType="Syncfusion.EJ2.Blazor.Charts.RangeValueType.DateTime" IntervalType="RangeIntervalType.Years">
    <RangeNavigatorEvents Resized="RangeNavigatorResized"></RangeNavigatorEvents>
    <RangeNavigatorSeriesCollection>
        <RangeNavigatorSeries DataSource="@StockDetails" XName="Date" Type="RangeNavigatorType.Line"
                              YName="Close"></RangeNavigatorSeries>
    </RangeNavigatorSeriesCollection>
</SfRangeNavigator>

@code {

    public void RangeNavigatorResized(IResizeRangeNavigatorEventArgs args)
    {
        // Here you can customize your code
    }

    DateTime[] Value = new DateTime[] { new DateTime(2006, 01, 01), new DateTime(2008, 01, 01) };

    public class Data
    {
        public DateTime Date;
        public double Close;
    }
    public List<Data> StockDetails = new List<Data>
{
        new Data { Date = new DateTime(2005, 01, 01), Close = 21 },
        new Data { Date = new DateTime(2006, 01, 01), Close = 24 },
        new Data { Date = new DateTime(2007, 01, 01), Close = 36 },
        new Data { Date = new DateTime(2008, 01, 01), Close = 38 },
        new Data { Date = new DateTime(2009, 01, 01), Close = 54 },
        new Data { Date = new DateTime(2010, 01, 01), Close = 57 },
        new Data { Date = new DateTime(2011, 01, 01), Close = 70 }
    };
}
```
