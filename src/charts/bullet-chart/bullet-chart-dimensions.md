---
title: "Dimensions in Blazor Bullet Chart component | Syncfusion"

component: "Bullet Chart"

description: "Learn here all about dimensions of Syncfusion Bullet Chart (SfBulletChart) component and more."
---

# Dimensions in Blazor Bullet Chart (SfBulletChart)

## Size for Container

The size of the Bullet Chart is determined by the container size, and it can be changed inline or via CSS, as shown below.

```csharp
@using Syncfusion.Blazor.Charts

<div style="width:650px; height:100px;">
    <SfBulletChart DataSource="@BulletChartData" ValueField="FieldValue" TargetField="Target" Minimum="0" Maximum="300" Interval="50" Title="Revenue">
        <BulletChartTooltip TValue="ChartData" Enable="true"></BulletChartTooltip>
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
        public double FieldValue { get; set; }
        public double Target { get; set; }
    }
    public List<ChartData> BulletChartData = new List<ChartData>
    {
        new ChartData { FieldValue = 270, Target = 250 }
    };
}
```

## Size for Bullet Chart

The [`Width`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SfBulletChart-1.html#Syncfusion_Blazor_Charts_SfBulletChart_1_Width) and [`Height`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SfBulletChart-1.html#Syncfusion_Blazor_Charts_SfBulletChart_1_Height) properties are used to adjust the size of the Bullet Chart. Both pixel and percentage values are accepted. If the value is expressed as a percentage, the dimension of the Bullet Chart is determined by its container.

> If the size is not specified, Bullet Chart will be rendered with a height of **126px** and a width of the window.

```csharp
@using Syncfusion.Blazor.Charts

<div style="width:1000px; height:150px;">
    <SfBulletChart DataSource="@BulletChartData" Height="70%" Width="50%" ValueField="FieldValue" TargetField="Target" Minimum="0" Maximum="300" Interval="50" Title="Revenue">
        <BulletChartTooltip TValue="ChartData" Enable="true"></BulletChartTooltip>
        <BulletChartRangeCollection>
            <BulletChartRange End=150> </BulletChartRange>
            <BulletChartRange End=250></BulletChartRange>
            <BulletChartRange End=300></BulletChartRange>
        </BulletChartRangeCollection>
    </SfBulletChart>
</div>
```

> Refer [code block](#size-for-container) to know the property value of **BulletChartData**.

## Margin

The [`BulletChartMargin`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.BulletChartMargin.html) is used to customize the bottom, left, right, and top margins of the Bullet Chart.

```csharp
@using Syncfusion.Blazor.Charts

<div style="width:650px; height:100px;">
    <SfBulletChart DataSource="@BulletChartData" ValueField="FieldValue" TargetField="Target" Minimum="0" Maximum="300" Interval="50" Title="Revenue">
        <BulletChartMargin Bottom="20" Left="20" Right="20" Top="20"></BulletChartMargin>
        <BulletChartBorder Color="#000000" Width="2"></BulletChartBorder>
        <BulletChartTooltip TValue="ChartData" Enable="true"></BulletChartTooltip>
        <BulletChartRangeCollection>
            <BulletChartRange End=150> </BulletChartRange>
            <BulletChartRange End=250></BulletChartRange>
            <BulletChartRange End=300></BulletChartRange>
        </BulletChartRangeCollection>
    </SfBulletChart>
</div>
```

> Refer [code block](#size-for-container) to know the property value of **BulletChartData**.

![Bullet Chart with Margin](images/margin.png)
