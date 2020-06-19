---
title: "Events"
component: "Chart"
description: "Learn how to use events in Blazor Data Chart component."
---

# Events

In this section, we have provided the list of events of the Chart component which will be
triggered for appropriate Chart actions.

The events should be provided to the Chart using [`ChartEvents`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartEvents.html) component.

> From `v17.2.*`, we have added only the limited number of events for the Chart component. The event names are different from the previous releases and also removed several events. The following are the event name changes from `v17.1.*` to `v17.2.*`

Event Name(`v17.1.*`) |Event Name(`v17.2.*`)
-----|-----
animationComplete |[OnAnimationComplete](events/#onanimationcomplete)
beforePrint |[OnPrint](events/#onprint)
chartMouseClick |[OnChartMouseClick](events/#onchartmouseclick)
chartMouseDown |[OnChartMouseDown](events/#onchartmousedown)
chartMouseLeave |[OnChartMouseLeave](events/#onchartmouseleave)
chartMouseMove |[OnChartMouseMove](events/#onchartmousemove)
chartMouseUp |[OnChartMouseUp](events/#onchartmouseup)
dragComplete |[OnDragComplete](events/#ondragcomplete)
loaded |[Loaded](events/#loaded)
pointClick |[OnPointClick](events/#onpointclick)
pointMove |[PointMoved](events/#pointmoved)
resized |[Resized](events/#resized)
scrollChanged |[ScrollChanged](events/#scrollchanged)
scrollEnd |[OnScrollEnd](events/#onscrollstart)
scrollStart |[OnScrollStart](events/#onscrollend)

## OnAnimationComplete

[`OnAnimationComplete`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartEvents~OnAnimationComplete.html) event is triggers after animation is completed for the series.

```csharp
@using Syncfusion.Blazor.Charts

<SfChart>
    <ChartEvents OnAnimationComplete="@AnimationHandler"></ChartEvents>

    <ChartPrimaryXAxis ValueType="Syncfusion.Blazor.Charts.ValueType.Category"></ChartPrimaryXAxis>
    <ChartSeriesCollection>
        <ChartSeries DataSource="@Sales" XName="Month" YName="SalesValue" Type="ChartSeriesType.Column">
        </ChartSeries>
    </ChartSeriesCollection>
</SfChart>

@code{
    public class SalesInfo
    {
        public string Month;
        public double SalesValue;
    }
    public List<SalesInfo> Sales = new List<SalesInfo>
{
        new SalesInfo { Month = "Jan", SalesValue = 35 },
        new SalesInfo { Month = "Feb", SalesValue = 28 },
        new SalesInfo { Month = "Mar", SalesValue = 34 },
        new SalesInfo { Month = "Apr", SalesValue = 32 },
        new SalesInfo { Month = "May", SalesValue = 40 },
        new SalesInfo { Month = "Jun", SalesValue = 32 },
        new SalesInfo { Month = "Jul", SalesValue = 35 }
    };

    public void AnimationHandler(IAnimationCompleteEventArgs args)
    {
        // Here you can customize your code
    }
}
```

## OnPrint

[`OnPrint`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartEvents~OnPrint.html) event is triggers before the prints gets started.

```csharp
@using Syncfusion.Blazor.Charts

<SfChart>
    <ChartEvents OnPrint="@PrintHandler"></ChartEvents>

    <ChartPrimaryXAxis ValueType="Syncfusion.Blazor.Charts.ValueType.Category"></ChartPrimaryXAxis>
    <ChartSeriesCollection>
        <ChartSeries DataSource="@Sales" XName="Month" YName="SalesValue" Type="ChartSeriesType.Column">
        </ChartSeries>
    </ChartSeriesCollection>
</SfChart>

@code{
    public class SalesInfo
    {
        public string Month;
        public double SalesValue;
    }
    public List<SalesInfo> Sales = new List<SalesInfo>
{
        new SalesInfo { Month = "Jan", SalesValue = 35 },
        new SalesInfo { Month = "Feb", SalesValue = 28 },
        new SalesInfo { Month = "Mar", SalesValue = 34 },
        new SalesInfo { Month = "Apr", SalesValue = 32 },
        new SalesInfo { Month = "May", SalesValue = 40 },
        new SalesInfo { Month = "Jun", SalesValue = 32 },
        new SalesInfo { Month = "Jul", SalesValue = 35 }
    };

    public void PrintHandler(IPrintEventArgs args)
    {
        // Here you can customize your code
    }
}
```

## OnChartMouseClick

[`OnChartMouseClick`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartEvents~OnChartMouseClick.html) event is triggers on clicking the chart.

```csharp
@using Syncfusion.Blazor.Charts

<SfChart>
    <ChartEvents OnChartMouseClick="@ChartMouseClickHandler"></ChartEvents>

    <ChartPrimaryXAxis ValueType="Syncfusion.Blazor.Charts.ValueType.Category"></ChartPrimaryXAxis>
    <ChartSeriesCollection>
        <ChartSeries DataSource="@Sales" XName="Month" YName="SalesValue" Type="ChartSeriesType.Column">
        </ChartSeries>
    </ChartSeriesCollection>
</SfChart>

@code{
    public class SalesInfo
    {
        public string Month;
        public double SalesValue;
    }
    public List<SalesInfo> Sales = new List<SalesInfo>
{
        new SalesInfo { Month = "Jan", SalesValue = 35 },
        new SalesInfo { Month = "Feb", SalesValue = 28 },
        new SalesInfo { Month = "Mar", SalesValue = 34 },
        new SalesInfo { Month = "Apr", SalesValue = 32 },
        new SalesInfo { Month = "May", SalesValue = 40 },
        new SalesInfo { Month = "Jun", SalesValue = 32 },
        new SalesInfo { Month = "Jul", SalesValue = 35 }
    };

    public void ChartMouseClickHandler(IMouseEventArgs args)
    {
        // Here you can customize your code
    }
}
```

## OnChartMouseDown

[`OnChartMouseDown`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartEvents~OnChartMouseDown.html) event is triggers on mouse down.

```csharp
@using Syncfusion.Blazor.Charts

<SfChart>
    <ChartEvents OnChartMouseDown="@ChartMouseDownHandler"></ChartEvents>

    <ChartPrimaryXAxis ValueType="Syncfusion.Blazor.Charts.ValueType.Category"></ChartPrimaryXAxis>
    <ChartSeriesCollection>
        <ChartSeries DataSource="@Sales" XName="Month" YName="SalesValue" Type="ChartSeriesType.Column">
        </ChartSeries>
    </ChartSeriesCollection>
</SfChart>

@code{
    public class SalesInfo
    {
        public string Month;
        public double SalesValue;
    }
    public List<SalesInfo> Sales = new List<SalesInfo>
{
        new SalesInfo { Month = "Jan", SalesValue = 35 },
        new SalesInfo { Month = "Feb", SalesValue = 28 },
        new SalesInfo { Month = "Mar", SalesValue = 34 },
        new SalesInfo { Month = "Apr", SalesValue = 32 },
        new SalesInfo { Month = "May", SalesValue = 40 },
        new SalesInfo { Month = "Jun", SalesValue = 32 },
        new SalesInfo { Month = "Jul", SalesValue = 35 }
    };

    public void ChartMouseDownHandler(IMouseEventArgs args)
    {
        // Here you can customize your code
    }
}
```

## OnChartMouseLeave

[`OnChartMouseLeave`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartEvents~OnChartMouseLeave.html) event is triggers when cursor leaves the chart.

```csharp
@using Syncfusion.Blazor.Charts

<SfChart>
    <ChartEvents OnChartMouseLeave="@ChartMouseLeaveHandler"></ChartEvents>

    <ChartPrimaryXAxis ValueType="Syncfusion.Blazor.Charts.ValueType.Category"></ChartPrimaryXAxis>
    <ChartSeriesCollection>
        <ChartSeries DataSource="@Sales" XName="Month" YName="SalesValue" Type="ChartSeriesType.Column">
        </ChartSeries>
    </ChartSeriesCollection>
</SfChart>

@code{
    public class SalesInfo
    {
        public string Month;
        public double SalesValue;
    }
    public List<SalesInfo> Sales = new List<SalesInfo>
{
        new SalesInfo { Month = "Jan", SalesValue = 35 },
        new SalesInfo { Month = "Feb", SalesValue = 28 },
        new SalesInfo { Month = "Mar", SalesValue = 34 },
        new SalesInfo { Month = "Apr", SalesValue = 32 },
        new SalesInfo { Month = "May", SalesValue = 40 },
        new SalesInfo { Month = "Jun", SalesValue = 32 },
        new SalesInfo { Month = "Jul", SalesValue = 35 }
    };

    public void ChartMouseLeaveHandler(IMouseEventArgs args)
    {
        // Here you can customize your code
    }
}
```

## OnChartMouseMove

[`OnChartMouseMove`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartEvents~OnChartMouseMove.html) event is triggers on hovering the chart.

```csharp
@using Syncfusion.Blazor.Charts

<SfChart>
    <ChartEvents OnChartMouseMove="@ChartMouseMoveHandler"></ChartEvents>

    <ChartPrimaryXAxis ValueType="Syncfusion.Blazor.Charts.ValueType.Category"></ChartPrimaryXAxis>
    <ChartSeriesCollection>
        <ChartSeries DataSource="@Sales" XName="Month" YName="SalesValue" Type="ChartSeriesType.Column">
        </ChartSeries>
    </ChartSeriesCollection>
</SfChart>

@code{
    public class SalesInfo
    {
        public string Month;
        public double SalesValue;
    }
    public List<SalesInfo> Sales = new List<SalesInfo>
{
        new SalesInfo { Month = "Jan", SalesValue = 35 },
        new SalesInfo { Month = "Feb", SalesValue = 28 },
        new SalesInfo { Month = "Mar", SalesValue = 34 },
        new SalesInfo { Month = "Apr", SalesValue = 32 },
        new SalesInfo { Month = "May", SalesValue = 40 },
        new SalesInfo { Month = "Jun", SalesValue = 32 },
        new SalesInfo { Month = "Jul", SalesValue = 35 }
    };

    public void ChartMouseMoveHandler(IMouseEventArgs args)
    {
        // Here you can customize your code
    }
}
```

## OnChartMouseUp

[`OnChartMouseUp`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartEvents~OnChartMouseUp.html) event is triggers on mouse up.

```csharp
@using Syncfusion.Blazor.Charts

<Sfchart>
    <ChartEvents OnChartMouseUp="@ChartMouseUpHandler"></ChartEvents>

    <ChartPrimaryXAxis ValueType="Syncfusion.Blazor.Charts.ValueType.Category"></ChartPrimaryXAxis>
    <ChartSeriesCollection>
        <ChartSeries DataSource="@Sales" XName="Month" YName="SalesValue" Type="ChartSeriesType.Column">
        </ChartSeries>
    </ChartSeriesCollection>
</Sfchart>

@code{
    public class SalesInfo
    {
        public string Month;
        public double SalesValue;
    }
    public List<SalesInfo> Sales = new List<SalesInfo>
    {
        new SalesInfo { Month = "Jan", SalesValue = 35 },
        new SalesInfo { Month = "Feb", SalesValue = 28 },
        new SalesInfo { Month = "Mar", SalesValue = 34 },
        new SalesInfo { Month = "Apr", SalesValue = 32 },
        new SalesInfo { Month = "May", SalesValue = 40 },
        new SalesInfo { Month = "Jun", SalesValue = 32 },
        new SalesInfo { Month = "Jul", SalesValue = 35 }
    };

    public void ChartMouseUpHandler(IMouseEventArgs args)
    {
        // Here you can customize your code
    }
}
```

## OnDragComplete

[`OnDragComplete`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartEvents~OnDragComplete.html) event is triggers after the drag selection is completed.

```csharp
@using Syncfusion.Blazor.Charts

<Sfchart>
    <ChartEvents OnDragComplete="@DragCompleteHandler"></ChartEvents>

    <ChartPrimaryXAxis ValueType="Syncfusion.Blazor.Charts.ValueType.Category"></ChartPrimaryXAxis>
    <ChartSeriesCollection>
        <ChartSeries DataSource="@Sales" XName="Month" YName="SalesValue" Type="ChartSeriesType.Column">
        </ChartSeries>
    </ChartSeriesCollection>
</Sfchart>

@code{
    public class SalesInfo
    {
        public string Month;
        public double SalesValue;
    }
    public List<SalesInfo> Sales = new List<SalesInfo>
    {
        new SalesInfo { Month = "Jan", SalesValue = 35 },
        new SalesInfo { Month = "Feb", SalesValue = 28 },
        new SalesInfo { Month = "Mar", SalesValue = 34 },
        new SalesInfo { Month = "Apr", SalesValue = 32 },
        new SalesInfo { Month = "May", SalesValue = 40 },
        new SalesInfo { Month = "Jun", SalesValue = 32 },
        new SalesInfo { Month = "Jul", SalesValue = 35 }
    };

    public void DragCompleteHandler(IDragCompleteEventArgs args)
    {
        // Here you can customize your code
    }
}
```

## Loaded

[`Loaded`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartEvents~Loaded.html) event is triggers after chart load.

```csharp
@using Syncfusion.Blazor.Charts

<Sfchart>
    <ChartEvents Loaded="@LoadedHandler"></ChartEvents>

    <ChartPrimaryXAxis ValueType="Syncfusion.Blazor.Charts.ValueType.Category"></ChartPrimaryXAxis>
    <ChartSeriesCollection>
        <ChartSeries DataSource="@Sales" XName="Month" YName="SalesValue" Type="ChartSeriesType.Column">
        </ChartSeries>
    </ChartSeriesCollection>
</Sfchart>

@code{
    public class SalesInfo
    {
        public string Month;
        public double SalesValue;
    }
    public List<SalesInfo> Sales = new List<SalesInfo>
    {
        new SalesInfo { Month = "Jan", SalesValue = 35 },
        new SalesInfo { Month = "Feb", SalesValue = 28 },
        new SalesInfo { Month = "Mar", SalesValue = 34 },
        new SalesInfo { Month = "Apr", SalesValue = 32 },
        new SalesInfo { Month = "May", SalesValue = 40 },
        new SalesInfo { Month = "Jun", SalesValue = 32 },
        new SalesInfo { Month = "Jul", SalesValue = 35 }
    };

    public void LoadedHandler(ILoadedEventArgs args)
    {
        // Here you can customize your code
    }
}
```

## OnPointClick

[`OnPointClick`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartEvents~OnPointClick.html) event is triggers on point click.

```csharp
@using Syncfusion.Blazor.Charts

<Sfchart>
    <ChartEvents OnPointClick="@PointClickHandler"></ChartEvents>

    <ChartPrimaryXAxis ValueType="Syncfusion.Blazor.Charts.ValueType.Category"></ChartPrimaryXAxis>
    <ChartSeriesCollection>
        <ChartSeries DataSource="@Sales" XName="Month" YName="SalesValue" Type="ChartSeriesType.Column">
        </ChartSeries>
    </ChartSeriesCollection>
</Sfchart>

@code{
    public class SalesInfo
    {
        public string Month;
        public double SalesValue;
    }
    public List<SalesInfo> Sales = new List<SalesInfo>
    {
        new SalesInfo { Month = "Jan", SalesValue = 35 },
        new SalesInfo { Month = "Feb", SalesValue = 28 },
        new SalesInfo { Month = "Mar", SalesValue = 34 },
        new SalesInfo { Month = "Apr", SalesValue = 32 },
        new SalesInfo { Month = "May", SalesValue = 40 },
        new SalesInfo { Month = "Jun", SalesValue = 32 },
        new SalesInfo { Month = "Jul", SalesValue = 35 }
    };

    public void PointClickHandler(IPointEventArgs args)
    {
        // Here you can customize your code
    }
}
```

## PointMoved

[`PointMoved`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartEvents~PointMoved.html) event is triggers on point move.

```csharp
@using Syncfusion.Blazor.Charts

<Sfchart>
    <ChartEvents PointMoved="@PointMovedHandler"></ChartEvents>

    <ChartPrimaryXAxis ValueType="Syncfusion.Blazor.Charts.ValueType.Category"></ChartPrimaryXAxis>
    <ChartSeriesCollection>
        <ChartSeries DataSource="@Sales" XName="Month" YName="SalesValue" Type="ChartSeriesType.Column">
        </ChartSeries>
    </ChartSeriesCollection>
</Sfchart>

@code{
    public class SalesInfo
    {
        public string Month;
        public double SalesValue;
    }
    public List<SalesInfo> Sales = new List<SalesInfo>
    {
        new SalesInfo { Month = "Jan", SalesValue = 35 },
        new SalesInfo { Month = "Feb", SalesValue = 28 },
        new SalesInfo { Month = "Mar", SalesValue = 34 },
        new SalesInfo { Month = "Apr", SalesValue = 32 },
        new SalesInfo { Month = "May", SalesValue = 40 },
        new SalesInfo { Month = "Jun", SalesValue = 32 },
        new SalesInfo { Month = "Jul", SalesValue = 35 }
    };

    public void PointMovedHandler(IPointEventArgs args)
    {
        // Here you can customize your code
    }
}
```

## Resized

[`Resized`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartEvents~Resized.html) event is triggers after resizing of chart.

```csharp
@using Syncfusion.Blazor.Charts

<Sfchart>
    <ChartEvents Resized="@ResizeHandler"></ChartEvents>

    <ChartPrimaryXAxis ValueType="Syncfusion.Blazor.Charts.ValueType.Category"></ChartPrimaryXAxis>
    <ChartSeriesCollection>
        <ChartSeries DataSource="@Sales" XName="Month" YName="SalesValue" Type="ChartSeriesType.Column">
        </ChartSeries>
    </ChartSeriesCollection>
</Sfchart>

@code{
    public class SalesInfo
    {
        public string Month;
        public double SalesValue;
    }
    public List<SalesInfo> Sales = new List<SalesInfo>
    {
        new SalesInfo { Month = "Jan", SalesValue = 35 },
        new SalesInfo { Month = "Feb", SalesValue = 28 },
        new SalesInfo { Month = "Mar", SalesValue = 34 },
        new SalesInfo { Month = "Apr", SalesValue = 32 },
        new SalesInfo { Month = "May", SalesValue = 40 },
        new SalesInfo { Month = "Jun", SalesValue = 32 },
        new SalesInfo { Month = "Jul", SalesValue = 35 }
    };

    public void ResizeHandler(IResizeEventArgs args)
    {
        // Here you can customize your code
    }
}
```

## ScrollChanged

[`ScrollChanged`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartEvents~ScrollChanged.html) event is triggers when change the scroll.

```csharp
@using Syncfusion.Blazor.Charts

<Sfchart>
    <ChartEvents ScrollChanged="@ScrollChangeHandler"></ChartEvents>

    <ChartPrimaryXAxis ValueType="Syncfusion.Blazor.Charts.ValueType.Category"></ChartPrimaryXAxis>
    <ChartSeriesCollection>
        <ChartSeries DataSource="@Sales" XName="Month" YName="SalesValue" Type="ChartSeriesType.Column">
        </ChartSeries>
    </ChartSeriesCollection>
</Sfchart>

@code{
    public class SalesInfo
    {
        public string Month;
        public double SalesValue;
    }
    public List<SalesInfo> Sales = new List<SalesInfo>
    {
        new SalesInfo { Month = "Jan", SalesValue = 35 },
        new SalesInfo { Month = "Feb", SalesValue = 28 },
        new SalesInfo { Month = "Mar", SalesValue = 34 },
        new SalesInfo { Month = "Apr", SalesValue = 32 },
        new SalesInfo { Month = "May", SalesValue = 40 },
        new SalesInfo { Month = "Jun", SalesValue = 32 },
        new SalesInfo { Month = "Jul", SalesValue = 35 }
    };

    public void ScrollChangeHandler(IScrollEventArgs args)
    {
        // Here you can customize your code
    }
}
```

## OnScrollStart

[`OnScrollStart`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartEvents~OnScrollStart.html) event is triggers when start the scroll.

```csharp
@using Syncfusion.Blazor.Charts

<Sfchart>
    <ChartEvents OnScrollStart="@ScrollStartHandler"></ChartEvents>

    <ChartPrimaryXAxis ValueType="Syncfusion.Blazor.Charts.ValueType.Category"></ChartPrimaryXAxis>
    <ChartSeriesCollection>
        <ChartSeries DataSource="@Sales" XName="Month" YName="SalesValue" Type="ChartSeriesType.Column">
        </ChartSeries>
    </ChartSeriesCollection>
</Sfchart>

@code{
    public class SalesInfo
    {
        public string Month;
        public double SalesValue;
    }
    public List<SalesInfo> Sales = new List<SalesInfo>
    {
        new SalesInfo { Month = "Jan", SalesValue = 35 },
        new SalesInfo { Month = "Feb", SalesValue = 28 },
        new SalesInfo { Month = "Mar", SalesValue = 34 },
        new SalesInfo { Month = "Apr", SalesValue = 32 },
        new SalesInfo { Month = "May", SalesValue = 40 },
        new SalesInfo { Month = "Jun", SalesValue = 32 },
        new SalesInfo { Month = "Jul", SalesValue = 35 }
    };

    public void ScrollStartHandler(IScrollEventArgs args)
    {
        // Here you can customize your code
    }
}
```

## OnScrollEnd

[`OnScrollEnd`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartEvents~OnScrollEnd.html) event is triggers after the scroll end.

```csharp
@using Syncfusion.Blazor.Charts

<Sfchart>
    <ChartEvents OnScrollEnd="@ScrollEndHandler"></ChartEvents>

    <ChartPrimaryXAxis ValueType="Syncfusion.Blazor.Charts.ValueType.Category"></ChartPrimaryXAxis>
    <ChartSeriesCollection>
        <ChartSeries DataSource="@Sales" XName="Month" YName="SalesValue" Type="ChartSeriesType.Column">
        </ChartSeries>
    </ChartSeriesCollection>
</Sfchart>

@code{
    public class SalesInfo
    {
        public string Month;
        public double SalesValue;
    }
    public List<SalesInfo> Sales = new List<SalesInfo>
    {
        new SalesInfo { Month = "Jan", SalesValue = 35 },
        new SalesInfo { Month = "Feb", SalesValue = 28 },
        new SalesInfo { Month = "Mar", SalesValue = 34 },
        new SalesInfo { Month = "Apr", SalesValue = 32 },
        new SalesInfo { Month = "May", SalesValue = 40 },
        new SalesInfo { Month = "Jun", SalesValue = 32 },
        new SalesInfo { Month = "Jul", SalesValue = 35 }
    };

    public void ScrollEndHandler(IScrollEventArgs args)
    {
        // Here you can customize your code
    }
}
```