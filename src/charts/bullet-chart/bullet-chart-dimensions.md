---
title: "Bullet Chart Appearance | ASP.NET Core Blazor "

component: "Bullet Chart"

description: "We can set bullet chart size manually by using width and height properties. We can set percentage or pixel size values to the bullet chart."
---

# Chart Dimensions

## Size for Container

Chart can render to its container size. You can set the size inline or through CSS as demonstrated below.

```csharp
@using Syncfusion.Blazor.Charts

<div style="width:650px; height:100px;">
    <SfBulletChart DataSource="@BulletChartData" ValueField="value" TargetField="target" Minimum="0" Maximum="300" Interval="50" Title="Revenue">
        <BulletChartTooltip Enable="true"></BulletChartTooltip>
        <BulletChartRangeCollection>
            <BulletChartRange End=150> </BulletChartRange>
            <BulletChartRange End=250></BulletChartRange>
            <BulletChartRange End=300></BulletChartRange>
        </BulletChartRangeCollection>
    </SfBulletChart>
</div>

@code{
    public class ChartData
    {
        public double value { get; set; }
        public double target { get; set; }
    }
    public List<ChartData> BulletChartData = new List<ChartData>
{
        new ChartData { value = 270, target = 250 }
    };
}
```

## Size for Bullet Chart

You can also set size for bullet chart directly through [`Width`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.BulletChartModel~Width.html) and
[`Height`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.BulletChartModel~Height.html) properties.

<!-- markdownlint-disable MD036 -->
**In Pixel**
<!-- markdownlint-disable MD036 -->

You can set the size of bullet chart in pixel as demonstrated below.

```csharp
@using Syncfusion.Blazor.Charts

<SfBulletChart Width="650px" Height="100px" DataSource="@BulletChartData" ValueField="value" TargetField="target" Minimum="0" Maximum="300" Interval="50" Title="Revenue">
    <BulletChartTooltip Enable="true"></BulletChartTooltip>
    <BulletChartRangeCollection>
        <BulletChartRange End=150> </BulletChartRange>
        <BulletChartRange End=250></BulletChartRange>
        <BulletChartRange End=300></BulletChartRange>
    </BulletChartRangeCollection>
</SfBulletChart>

@code{
    public class ChartData
    {
        public double value { get; set; }
        public double target { get; set; }
    }
    public List<ChartData> BulletChartData = new List<ChartData>
{
        new ChartData { value = 270, target = 250 }
    };
}
```

**In Percentage**

By setting value in percentage, bullet chart gets its dimension with respect to its container. For example,
when the height is ‘50%’, chart renders to half of the container height.

```csharp
@using Syncfusion.Blazor.Charts

<SfBulletChart Width="80%" Height="90%" DataSource="@BulletChartData" ValueField="value" TargetField="target" Minimum="0" Maximum="300" Interval="50" Title="Revenue">
    <BulletChartTooltip Enable="true"></BulletChartTooltip>
    <BulletChartRangeCollection>
        <BulletChartRange End=150> </BulletChartRange>
        <BulletChartRange End=250></BulletChartRange>
        <BulletChartRange End=300></BulletChartRange>
    </BulletChartRangeCollection>
</SfBulletChart>

@code{
    public class ChartData
    {
        public double value { get; set; }
        public double target { get; set; }
    }
    public List<ChartData> BulletChartData = new List<ChartData>
{
        new ChartData { value = 270, target = 250 }
    };
}
```

> Note:  When you do not specify the size, it takes `126px` as its height and window size as its width.