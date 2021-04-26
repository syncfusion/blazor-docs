---
title: "Legend in Blazor Bullet Chart component | Syncfusion"

component: "Bullet Chart"

description: "Learn here all about Legend of Syncfusion Bullet Chart (SfBulletChart) component and more."
---

# Legend in Blazor Bullet Chart (SfBulletChart)

Legend is used to provide valuable information for interpreting what the Bullet Chart displays. The legends can be represented in various colors, positions, shapes or other identifiers based on data and it can be enabled by [`Visible`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.BulletChartLegendSettings.html#Syncfusion_Blazor_Charts_BulletChartLegendSettings_Visible) property to **true** in [`BulletChartLegendSettings`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.BulletChartLegendSettings.html).

```csharp
@using Syncfusion.Blazor.Charts

<SfBulletChart DataSource="@BulletChartData" Height="300px" Title="Sales Rate" ValueField="FieldValue" TargetField="TargetValue" Minimum="0" Maximum="100" Interval="20">
    <BulletChartLegendSettings Visible="true"></BulletChartLegendSettings>
    <BulletChartRangeCollection>
        <BulletChartRange End=35> </BulletChartRange>
        <BulletChartRange End=50></BulletChartRange>
        <BulletChartRange End=100></BulletChartRange>
    </BulletChartRangeCollection>
</SfBulletChart>

@code{
    public class ChartData
    {
        public double FieldValue { get; set; }
        public double TargetValue { get; set; }
    }
    public List<ChartData> BulletChartData = new List<ChartData>
    {
        new ChartData { FieldValue = 55, TargetValue = 75 },
        new ChartData { FieldValue = 45, TargetValue = 15 },
        new ChartData { FieldValue = 75, TargetValue = 35 }
    };
}
```

![Legend](images/legend.png)

## Legend items from color mapping

Legend items will be render based on mapping ranges from Bullet Chart. The legend item name can be determine from [`Name`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.BulletChartRange.html#Syncfusion_Blazor_Charts_BulletChartRange_Name) property and the shape of legend item can be customized using [`Shape`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.BulletChartRange.html#Syncfusion_Blazor_Charts_BulletChartRange_Shape) property in [`BulletChartRange`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.BulletChartRange.html). By default legend item rendered on [`Rectangle`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.LegendShape.html) shape.

Legend item to be customized by following properties.

* [`Padding`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.BulletChartLegendSettings.html#Syncfusion_Blazor_Charts_BulletChartLegendSettings_Padding) - Specifies the padding between legend items.
* [`ShapeHeight`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.BulletChartLegendSettings.html#Syncfusion_Blazor_Charts_BulletChartLegendSettings_ShapeHeight) - Specifies the shape height of legend items.
* [`ShapeWidth`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.BulletChartLegendSettings.html#Syncfusion_Blazor_Charts_BulletChartLegendSettings_ShapeWidth) - Specifies the shape width of legend items.
* [`ShapePadding`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.BulletChartLegendSettings.html#Syncfusion_Blazor_Charts_BulletChartLegendSettings_ShapePadding) - Specifies the padding between the shape and text of the legend item.
* [`BulletChartLegendTextStyle`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.BulletChartLegendTextStyle.html) - Specifies the text style of legend item.

```csharp
@using Syncfusion.Blazor.Charts

<SfBulletChart DataSource="@BulletChartData" Height="300px" Title="Sales Rate" ValueField="FieldValue" TargetField="TargetValue" Minimum="0" Maximum="100" Interval="20">
    <BulletChartLegendSettings Visible="true"></BulletChartLegendSettings>
    <BulletChartRangeCollection>
        <BulletChartRange End=35 Name="Apple"></BulletChartRange>
        <BulletChartRange End=50 Name="Mango" Color="lightgreen" Shape="LegendShape.Pentagon"></BulletChartRange>
        <BulletChartRange End=100 Name="Papaya"></BulletChartRange>
    </BulletChartRangeCollection>
</SfBulletChart>
```

> Refer [code block](#legend) to know the property value of **BulletChartData**.

![Legend items with color mapping](images/legend-color-mapping.png)

## Legend size

Customize the legend size by modifying the [`Height`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.BulletChartLegendSettings.html#Syncfusion_Blazor_Charts_BulletChartLegendSettings_Height) and [`Width`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.BulletChartLegendSettings.html#Syncfusion_Blazor_Charts_BulletChartLegendSettings_Width) properties in [`BulletChartLegendSettings`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.BulletChartLegendSettings.html). It accepts values in both percentage and pixel.

```csharp
@using Syncfusion.Blazor.Charts

<SfBulletChart DataSource="@BulletChartData" Height="300px" Title="Sales Rate" ValueField="FieldValue" TargetField="TargetValue" Minimum="0" Maximum="100" Interval="20">
    <BulletChartLegendSettings Visible="true" Width="15%"></BulletChartLegendSettings>
    <BulletChartRangeCollection>
        <BulletChartRange End=35 Name="Apple"></BulletChartRange>
        <BulletChartRange End=50 Name="Mango" Color="lightgreen" Shape="LegendShape.Pentagon"></BulletChartRange>
        <BulletChartRange End=100 Name="Papaya"></BulletChartRange>
    </BulletChartRangeCollection>
</SfBulletChart>
```

> Refer [code block](#legend) to know the property value of **BulletChartData**.

![Legend with custom legend size](images/legend-size.png)

## Legend with paging support

Bullet Chart supports the legend paging, if the legend items cannot be placed within the provided [`Height`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.BulletChartLegendSettings.html#Syncfusion_Blazor_Charts_BulletChartLegendSettings_Height) and [`Width`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.BulletChartLegendSettings.html#Syncfusion_Blazor_Charts_BulletChartLegendSettings_Width) of legend.

```csharp
@using Syncfusion.Blazor.Charts

<SfBulletChart DataSource="@BulletChartData" Height="300px" Title="Sales Rate" ValueField="FieldValue" TargetField="TargetValue" Minimum="0" Maximum="100" Interval="20">
    <BulletChartLegendSettings Visible="true" Width="15%" Height="15%">
        <BulletChartLegendBorder Color="red" Width="1"></BulletChartLegendBorder>
    </BulletChartLegendSettings>
    <BulletChartRangeCollection>
        <BulletChartRange End=35 Name="Apple"></BulletChartRange>
        <BulletChartRange End=50 Name="Mango" Color="lightgreen" Shape="LegendShape.Pentagon"></BulletChartRange>
        <BulletChartRange End=100 Name="Papaya"></BulletChartRange>
    </BulletChartRangeCollection>
</SfBulletChart>
```

> Refer [code block](#legend) to know the property value of **BulletChartData**.

![Legend with custom legend size](images/legend-paging.png)

## Position and Alignment

The legend can be place to various positions and following options are available to customize the legend position using [`Position`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.BulletChartLegendSettings.html#Syncfusion_Blazor_Charts_BulletChartLegendSettings_Position) property:

* [`Auto`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.LegendPosition.html#Syncfusion_Blazor_Charts_LegendPosition_Auto)
* [`Bottom`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.LegendPosition.html#Syncfusion_Blazor_Charts_LegendPosition_Bottom)
* [`Top`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.LegendPosition.html#Syncfusion_Blazor_Charts_LegendPosition_Top)
* [`Left`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.LegendPosition.html#Syncfusion_Blazor_Charts_LegendPosition_Left)
* [`Right`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.LegendPosition.html#Syncfusion_Blazor_Charts_LegendPosition_Right)
* [`Custom`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.LegendPosition.html#Syncfusion_Blazor_Charts_LegendPosition_Custom)

The following code example demonstrates the top legend position.

```csharp
@using Syncfusion.Blazor.Charts

<SfBulletChart DataSource="@BulletChartData" Height="300px" ValueField="FieldValue" TargetField="TargetValue" Minimum="0" Maximum="100" Interval="20">
    <BulletChartLegendSettings Height="40px" Visible="true" Position="LegendPosition.Top"></BulletChartLegendSettings>
    <BulletChartRangeCollection>
        <BulletChartRange End=35 Name="Apple"></BulletChartRange>
        <BulletChartRange End=50 Name="Mango" Color="lightgreen" Shape="LegendShape.Pentagon"></BulletChartRange>
        <BulletChartRange End=100 Name="Papaya"></BulletChartRange>
    </BulletChartRangeCollection>
</SfBulletChart>
```

> Refer [code block](#legend) to know the property value of **BulletChartData**.

![Legend on top position](images/legend-top.png)

[`Auto`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.LegendPosition.html#Syncfusion_Blazor_Charts_LegendPosition_Auto) position will be render with responsive legend height to [`Bottom`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.LegendPosition.html#Syncfusion_Blazor_Charts_LegendPosition_Bottom) of the component and [`Custom`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.LegendPosition.html#Syncfusion_Blazor_Charts_LegendPosition_Custom) position renders based on x and y coordinates by specified to [`X`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.BulletChartLegendLocation.html#Syncfusion_Blazor_Charts_BulletChartLegendLocation_X) and [`Y`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.BulletChartLegendLocation.html#Syncfusion_Blazor_Charts_BulletChartLegendLocation_Y) properties in [`BulletChartLegendLocation`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.BulletChartLegendLocation.html).

The following code example demonstrates the [`Custom`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.LegendPosition.html#Syncfusion_Blazor_Charts_LegendPosition_Custom) legend position.

```csharp
@using Syncfusion.Blazor.Charts

<SfBulletChart DataSource="@BulletChartData" Height="300px" ValueField="FieldValue" TargetField="TargetValue" Minimum="0" Maximum="100" Interval="20">
    <BulletChartMargin Top="30"></BulletChartMargin>
    <BulletChartLegendSettings Height="40px" Visible="true" Position="LegendPosition.Custom">
        <BulletChartLegendLocation X="5" Y="0"></BulletChartLegendLocation>
    </BulletChartLegendSettings>
    <BulletChartRangeCollection>
        <BulletChartRange End=35 Name="Apple"></BulletChartRange>
        <BulletChartRange End=50 Name="Mango" Color="lightgreen" Shape="LegendShape.Pentagon"></BulletChartRange>
        <BulletChartRange End=100 Name="Papaya"></BulletChartRange>
    </BulletChartRangeCollection>
</SfBulletChart>
```

> Refer [code block](#legend) to know the property value of **BulletChartData**.

![Legend on custom position](images/legend-custom-position.png)

The legend alignment is used to align the legend items to specific location. The following options are available to customize using [`Alignment`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.BulletChartLegendSettings.html#Syncfusion_Blazor_Charts_BulletChartLegendSettings_Alignment)  property:

* [`Near`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.Alignment.html#Syncfusion_Blazor_Charts_Alignment_Near)
* [`Center`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.Alignment.html#Syncfusion_Blazor_Charts_Alignment_Center)
* [`Far`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.Alignment.html#Syncfusion_Blazor_Charts_Alignment_Far)

The following code example demonstrates legend item alignment.

```csharp
@using Syncfusion.Blazor.Charts

<SfBulletChart DataSource="@BulletChartData" Height="300px" ValueField="FieldValue" TargetField="TargetValue" Minimum="0" Maximum="100" Interval="20">
    <BulletChartLegendSettings Height="40px" Visible="true" Position="LegendPosition.Top" Alignment="Alignment.Near"></BulletChartLegendSettings>
    <BulletChartRangeCollection>
        <BulletChartRange End=35 Name="Apple"></BulletChartRange>
        <BulletChartRange End=50 Name="Mango" Color="lightgreen" Shape="LegendShape.Pentagon"></BulletChartRange>
        <BulletChartRange End=100 Name="Papaya"></BulletChartRange>
    </BulletChartRangeCollection>
</SfBulletChart>
```

> Refer [code block](#legend) to know the property value of **BulletChartData**.

![Legend item with alignment](images/legend-align.png)

## Customization

Legend can be customized by following properties:

* [`Background`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.BulletChartLegendSettings.html#Syncfusion_Blazor_Charts_BulletChartLegendSettings_Background) - Specifies the fill color of the legend.
* [`Opacity`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.BulletChartLegendSettings.html#Syncfusion_Blazor_Charts_BulletChartLegendSettings_Opacity) - Specifies the opacity of legend background.
* [`BulletChartLegendMargin`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.BulletChartLegendMargin.html) - Specifies the bottom, left, right, top margin of the legend.
* [`BulletChartLegendBorder`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.BulletChartLegendBorder.html) - Specifies the color and width of the legend border.

```csharp
@using Syncfusion.Blazor.Charts

<SfBulletChart DataSource="@BulletChartData" Height="300px" ValueField="FieldValue" TargetField="TargetValue" Minimum="0" Maximum="100" Interval="20">
    <BulletChartLegendSettings Height="40px" Visible="true" Position="LegendPosition.Top" Background="lightgray" Opacity="0.4" ShapeHeight="15" ShapeWidth="15">
        <BulletChartMargin Top="5"></BulletChartMargin>
        <BulletChartLegendTextStyle Size="15px" Color="red" Opacity="1" FontStyle="italic"></BulletChartLegendTextStyle>
        <BulletChartLegendBorder Color="#000000" Width="2"></BulletChartLegendBorder>
    </BulletChartLegendSettings>
    <BulletChartRangeCollection>
        <BulletChartRange End=35 Name="Apple"></BulletChartRange>
        <BulletChartRange End=50 Name="Mango" Shape="LegendShape.Pentagon"></BulletChartRange>
        <BulletChartRange End=100 Name="Papaya"></BulletChartRange>
    </BulletChartRangeCollection>
</SfBulletChart>
```

> Refer [code block](#legend) to know the property value of **BulletChartData**.

![Legend with customization](images/custom-legend.png)
