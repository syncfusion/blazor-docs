# Axis Customization

## MajorTickLines and MinorTickLines Customization

Following properties can be used to customize major and minor tick lines.

* **Width** - Specifies the width of tick lines.
* **Height** -  Specifies the height of tick lines.
* **Color** -  Specifies the color of tick lines.
* **EnableRangeColor** -  Specifies the color of tick lines which to be based on corresponding range colors.

```csharp
@using Syncfusion.Blazor.Charts

<SfBulletChart DataSource="@BulletChartData" ValueField="FieldValue" TargetField="Target" Minimum="0" Maximum="30" Interval="5">
    <BulletChartMinorTickLines Width="4" Height="10" EnableRangeColor="true"></BulletChartMinorTickLines>
    <BulletChartMajorTickLines Width="5" Height="15" Color="red"></BulletChartMajorTickLines>
    <BulletChartRangeCollection>
        <BulletChartRange End=20 Color="#DBE7F3"></BulletChartRange>
        <BulletChartRange End=25 Color="#BBCEE7"></BulletChartRange>
        <BulletChartRange End=30 Color="#96B2D7"></BulletChartRange>
    </BulletChartRangeCollection>
</SfBulletChart>

@code{
    public class ChartData
    {
        public double FieldValue { get; set; }
        public double Target { get; set; }
    }
    public List<ChartData> BulletChartData = new List<ChartData>
    {
        new ChartData { FieldValue = 25, Target = 20 }
    };
}
```

![Axis Customization](images/tick-line.png)

## Tick Placement

Major and minor ticks can be placed [`Inside`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.TickPosition.html#Syncfusion_Blazor_Charts_TickPosition_Inside) or [`Outside`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.TickPosition.html#Syncfusion_Blazor_Charts_TickPosition_Outside) to the ranges using the [`TickPosition`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SfBulletChart-1.html#Syncfusion_Blazor_Charts_SfBulletChart_1_TickPosition) property.

```csharp
@using Syncfusion.Blazor.Charts

<SfBulletChart DataSource="@BulletChartData" TickPosition="TickPosition.Inside" ValueField="FieldValue" TargetField="Target" Minimum="0" Maximum="30" Interval="5">
    <BulletChartRangeCollection>
        <BulletChartRange End=20> </BulletChartRange>
        <BulletChartRange End=25></BulletChartRange>
        <BulletChartRange End=30></BulletChartRange>
    </BulletChartRangeCollection>
</SfBulletChart>
```

> Refer [code block](#majorTickLines-and-minorTickLines-customization) to know the property value of **BulletChartData**.

![Axis Customization](images/tick-position.png)

## Label Format

Axis labels support all globalize formats and it can be enabled by specify in [`Format`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SfBulletChart-1.html#Syncfusion_Blazor_Charts_SfBulletChart_1_Format) property.

The following code demonstrates the axis label with currency format.

```csharp
@using Syncfusion.Blazor.Charts

<SfBulletChart DataSource="@BulletChartData" Format="C" ValueField="FieldValue" TargetField="Target" Minimum="0" Maximum="30" Interval="5">
    <BulletChartRangeCollection>
        <BulletChartRange End=20> </BulletChartRange>
        <BulletChartRange End=25></BulletChartRange>
        <BulletChartRange End=30></BulletChartRange>
    </BulletChartRangeCollection>
</SfBulletChart>
```

> Refer [code block](#majorTickLines-and-minorTickLines-customization) to know the property value of **BulletChartData**.

![Axis Customization](images/label-format.png)

The following **Table** describes the result of applying some commonly used formats on numeric axis values.

<!-- markdownlint-disable MD033 -->
<table>
<tr>
<td><b>Label Value</b></td>
<td><b>Label Format property value</b></td>
<td><b>Result </b></td>
<td><b>Description </b></td>
</tr>
<tr>
<td>1000</td>
<td>n1</td>
<td>1000.0</td>
<td>The result is rounded to 1 decimal place</td>
</tr>
<tr>
<td>1000</td>
<td>n2</td>
<td>1000.00</td>
<td>The result is rounded to 2 decimal place</td>
</tr>
<tr>
<td>1000</td>
<td>n3</td>
<td>1000.000</td>
<td>The result is rounded to 3 decimal place</td>
</tr>
<tr>
<td>0.01</td>
<td>p1</td>
<td>1.0%</td>
<td>The result is converted to percentage with 1 decimal place</td>
</tr>
<tr>
<td>0.01</td>
<td>p2</td>
<td>1.00%</td>
<td>The result is converted to percentage with 2 decimal place</td>
</tr>
<tr>
<td>0.01</td>
<td>p3</td>
<td>1.000%</td>
<td>The result is converted to percentage with 3 decimal place</td>
</tr>
<tr>
<td>1000</td>
<td>c1</td>
<td>$1000.0</td>
<td>The currency symbol is appended to result and it is rounded to 1 decimal place</td>
</tr>
<tr>
<td>1000</td>
<td>c2</td>
<td>$1000.00</td>
<td>The currency symbol is appended to result and it is rounded to 2 decimal place</td>
</tr>
</table>

## GroupingSeparator

Separate groups of thousands by setting the [`EnableGroupSeparator`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SfBulletChart-1.html#Syncfusion_Blazor_Charts_SfBulletChart_1_EnableGroupSeparator) property to **true** along with specify the numeric axis label by setting the [`Format`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SfBulletChart-1.html#Syncfusion_Blazor_Charts_SfBulletChart_1_Format) property to **N0**.

```csharp
@using Syncfusion.Blazor.Charts

<SfBulletChart DataSource="@BulletChartData" EnableGroupSeparator="true" Format="N0" ValueField="FieldValue" TargetField="Target" Minimum="0" Maximum="2500" Interval="250">
    <BulletChartRangeCollection>
        <BulletChartRange End=500> </BulletChartRange>
        <BulletChartRange End=1500></BulletChartRange>
        <BulletChartRange End=2500></BulletChartRange>
    </BulletChartRangeCollection>
</SfBulletChart>

@code{
    public class ChartData
    {
        public double FieldValue { get; set; }
        public double Target { get; set; }
    }
    public List<ChartData> BulletChartData = new List<ChartData>
    {
        new ChartData { FieldValue = 1500, Target = 1300 }
    };
}
```

![Axis Customization](images/grouping.png)

## Custom Label Format

Axis labels can be specifies with custom defined format along with axis value by using the [`LabelFormat`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SfBulletChart-1.html#Syncfusion_Blazor_Charts_SfBulletChart_1_LabelFormat) property. The label format using a placeholder like **${value}K**, which value represents the axis label.

```csharp
@using Syncfusion.Blazor.Charts

<SfBulletChart DataSource="@BulletChartData" LabelFormat="${value}K" ValueField="FieldValue" TargetField="Target" Minimum="0" Maximum="2500" Interval="250">
    <BulletChartRangeCollection>
        <BulletChartRange End=500> </BulletChartRange>
        <BulletChartRange End=1500></BulletChartRange>
        <BulletChartRange End=2500></BulletChartRange>
    </BulletChartRangeCollection>
</SfBulletChart>
```

> Refer [code block](#groupingSeparator) to know the property value of **BulletChartData**.

![Axis Customization](images/labels-custom.png)

## Label Placement

Labels can be placed [`Inside`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.LabelsPlacement.html#Syncfusion_Blazor_Charts_LabelsPlacement_Inside) or [`Outside`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.LabelsPlacement.html#Syncfusion_Blazor_Charts_LabelsPlacement_Outside) to the ranges using the [`LabelPosition`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SfBulletChart-1.html#Syncfusion_Blazor_Charts_SfBulletChart_1_LabelPosition) property.

```csharp
@using Syncfusion.Blazor.Charts

<SfBulletChart DataSource="@BulletChartData" LabelPosition="LabelsPlacement.Inside" ValueField="FieldValue" TargetField="Target" Minimum="0" Maximum="30" Interval="5">
    <BulletChartRangeCollection>
        <BulletChartRange End=20></BulletChartRange>
        <BulletChartRange End=25></BulletChartRange>
        <BulletChartRange End=30></BulletChartRange>
    </BulletChartRangeCollection>
</SfBulletChart>
```

> Refer [code block](#groupingSeparator) to know the property value of **BulletChartData**.

![Axis Customization](images/labels-position.png)

## Opposed Position

To place an axis opposite to its original position,
by setting the [`OpposedPosition`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SfBulletChart-1.html#Syncfusion_Blazor_Charts_SfBulletChart_1_OpposedPosition) property to **true**.

```csharp
@using Syncfusion.Blazor.Charts

<SfBulletChart DataSource="@BulletChartData" OpposedPosition="true" ValueField="FieldValue" TargetField="Target" Minimum="0" Maximum="30" Interval="5">
    <BulletChartRangeCollection>
        <BulletChartRange End=20></BulletChartRange>
        <BulletChartRange End=25></BulletChartRange>
        <BulletChartRange End=30></BulletChartRange>
    </BulletChartRangeCollection>
</SfBulletChart>
```

> Refer [code block](#groupingSeparator) to know the property value of **BulletChartData**.

![Axis Customization](images/opposed.png)

## Category Label

Bullet Chart supports the X axis label by specifies the property from data source to [`CategoryField`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SfBulletChart-1.html#Syncfusion_Blazor_Charts_SfBulletChart_1_CategoryField). It helps to understand the data in more efficient way.

```csharp
@using Syncfusion.Blazor.Charts

<SfBulletChart DataSource="@BulletChartData" CategoryField="Category" ValueField="FieldValue" TargetField="Target" Minimum="0" Maximum="30" Interval="5">
    <BulletChartRangeCollection>
        <BulletChartRange End=20></BulletChartRange>
        <BulletChartRange End=25></BulletChartRange>
        <BulletChartRange End=30></BulletChartRange>
    </BulletChartRangeCollection>
</SfBulletChart>

@code{
    public class ChartData
    {
        public double FieldValue { get; set; }
        public double Target { get; set; }
        public string Category { get; set; }
    }
    public List<ChartData> BulletChartData = new List<ChartData>
    {
        new ChartData { FieldValue = 23, Target = 25, Category="Product A" }
    };
}
```

![Axis Customization](images/category.png)

## Axis and Category Label Customization

Customize the label color, opacity, font size, font family, font weight and font style by using [`BulletChartCategoryLabelStyle`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.BulletChartCategoryLabelStyle.html) for category and [`BulletChartLabelStyle`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.BulletChartLabelStyle.html) for axis label. [`EnableRangeColor`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.BulletChartCommonFont.html#Syncfusion_Blazor_Charts_BulletChartCommonFont_EnableRangeColor) property represents the color of axis label which to be based on corresponding range colors.

```csharp
@using Syncfusion.Blazor.Charts

<SfBulletChart DataSource="@BulletChartData" CategoryField="Category" ValueField="FieldValue" TargetField="Target" Minimum="0" Maximum="30" Interval="5">
    <BulletChartCategoryLabelStyle Color="red" Opacity="0.8" Size="15px" FontStyle="italic"></BulletChartCategoryLabelStyle>
    <BulletChartLabelStyle Color="red" Opacity="1" Size="15px" FontStyle="italic" EnableRangeColor="true"></BulletChartLabelStyle>
    <BulletChartRangeCollection>
        <BulletChartRange End=20 Color="#959595"></BulletChartRange>
        <BulletChartRange End=25 Color="#BDBDBD"></BulletChartRange>
        <BulletChartRange End=30 Color="#E3E2E2"></BulletChartRange>
    </BulletChartRangeCollection>
</SfBulletChart>
```

> Refer [code block](#category-label) to know the property value of **BulletChartData**.

![Axis Customization](images/label-custom.png)
