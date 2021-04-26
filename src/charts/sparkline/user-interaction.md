---
title: "User Interaction in Blazor Sparkline component | Syncfusion"

component: "Sparkline"

description: "Learn here all about User Interaction of Syncfusion Sparkline (SfSparkline) component and more."
---

# User Interaction in Blazor Sparkline (SfSparkline)

The tooltip and tracker line are user interaction features in the Sparkline.

## Tooltip

The Sparkline provide options to display details about, values of data points through tooltip when mouse hover data point.

The following code example demonstrates, how to enable tooltip for Sparkline with custom format.

```csharp
@using Syncfusion.Blazor.Charts

<SfSparkline Width="500" Height="200" TValue="WorkLog" DataSource="WorkLogs" XName="Day" YName="Hour" Fill="blue" ValueType="SparklineValueType.Category">
    <SparklineAxisSettings MinX="-1" MaxX="7" MaxY="8" MinY="-1">
    </SparklineAxisSettings>
    <SparklineTooltipSettings TValue="WorkLog" Visible="true" Format="${Day} : ${Hour}">
    </SparklineTooltipSettings>
</SfSparkline>

@code {
    public class WorkLog
    {
        public string Day { get; set; }
        public double Hour { get; set; }
    };
    public List<WorkLog> WorkLogs = new List<WorkLog> {
        new WorkLog {Day= "Mon", Hour= 3 },
        new WorkLog {Day= "Tue", Hour= 5 },
        new WorkLog {Day= "Wed", Hour= 2 },
        new WorkLog {Day= "Thu", Hour= 4 },
        new WorkLog {Day= "Fri", Hour= 6 }
    };
}
```

![Sparkline with tooltip](/images/UserInteraction/Tooltip.png)

### customization

Sparkline tooltip can be customized using following properties:

* [`Fill`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SparklineTooltipSettings-1.html#Syncfusion_Blazor_Charts_SparklineTooltipSettings_1_Fill) - Specifies fill color for tooltip.
* [`Format`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SparklineTooltipSettings-1.html#Syncfusion_Blazor_Charts_SparklineTooltipSettings_1_Format) - Specifies custom content of tooltip by assigning properties from data source.
* [`SparklineTooltipTextStyle`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SparklineTooltipTextStyle.html) - Specifies font family, style, weight, color, opacity and size of tooltip content.
* [`SparklineTooltipBorder`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SparklineTooltipBorder.html) - To customize tooltip border width and color

The following code example shows customizing tooltip format, text color and fill color.

```csharp
@using Syncfusion.Blazor.Charts

<SfSparkline Width="500" Height="200" TValue="WorkLog" DataSource="WorkLogs" XName="Day" YName="Hour" Fill="blue" ValueType="SparklineValueType.Category">
    <SparklineAxisSettings MinX="-1" MaxX="7" MaxY="8" MinY="-1">
    </SparklineAxisSettings>
    <SparklineTooltipSettings TValue="WorkLog" Visible="true" Format="${Day} : ${Hour}" Fill="lightgray">
        <SparklineTooltipTextStyle Color="darkblue"></SparklineTooltipTextStyle>
        <SparklineTooltipBorder Color="red" Width="1"></SparklineTooltipBorder>
    </SparklineTooltipSettings>
</SfSparkline>
```

> Refer [code block](#tooltip) to know the property value of **WorkLogs**.

![Sparkline with custom tooltip](/images/UserInteraction/TooltipCustomization.png)

### Template

Tooltip can be render as a custom component using [`Template`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SparklineTooltipSettings-1.html#Syncfusion_Blazor_Charts_SparklineTooltipSettings_1_Template) property in the [`SparklineTooltipSettings`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SparklineTooltipSettings-1.html) which accepts one or more UI elements as an input, that can be rendered as part of the tooltip rendering.

```csharp
@using Syncfusion.Blazor.Charts

<SfSparkline Width="500" Height="200" TValue="WorkLog" DataSource="WorkLogs" XName="Day" YName="Hour" Fill="blue" ValueType="SparklineValueType.Category">
    <SparklineAxisSettings MinX="-1" MaxX="7" MaxY="8" MinY="-1">
    </SparklineAxisSettings>
    <SparklineTooltipSettings TValue="WorkLog" Visible="true" Fill="lightgray">
        <Template>
            @{
                <table style="width:100%; background-color: #ffffff; border-spacing: 0px; border-collapse:separate; border: 1px solid grey; border-radius:10px; padding-top: 5px; padding-bottom:5px">
                    <tr>
                        <td style="font-weight:bold; color:black; padding-left: 5px;padding-top: 2px;padding-bottom: 2px;">Worklog</td>
                    </tr>
                    <tr>
                        <td style="padding-left: 5px; color:black; padding-right: 5px; padding-bottom: 2px;">Day : @context.Day  </td>
                    </tr>
                    <tr>
                        <td style="padding-left: 5px; color:black; padding-right: 5px">Hour : @context.Hour hrs </td>
                    </tr>
                </table>
            }
        </Template>
    </SparklineTooltipSettings>
</SfSparkline>
```

> Refer [code block](#tooltip) to know the property value of **WorkLogs**.

![Sparkline with template](/images/UserInteraction/tooltiptemplate.png)

## Track line

The track line, tracks the data points that are closer to the mouse position or touch interaction and it can be enabled by setting the [`Visible`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SparklineTrackLineSettings.html#Syncfusion_Blazor_Charts_SparklineTrackLineSettings_Visible) property to **true** in  [`SparklineTrackLineSettings`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SparklineTrackLineSettings.html). The track line color and width can be customized using [`Color`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SparklineTrackLineSettings.html#Syncfusion_Blazor_Charts_SparklineTrackLineSettings_Color) and [`Width`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SparklineTrackLineSettings.html#Syncfusion_Blazor_Charts_SparklineTrackLineSettings_Width) properties in [`SparklineTrackLineSettings`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.SparklineTrackLineSettings.html).

```csharp
@using Syncfusion.Blazor.Charts

<SfSparkline Width="500px" Height="200px"
             DataSource="new int[]{ 5, 3, 4, 6, 8, 7, 9, 1, 3, 5, 3, 4, 6, 8, 7, 9, 1, 3, 5, 2, 4, 6, 7, 9, 5, 8, 3, 6, 1, 7, 4, 2, 5, 2, 4, 6, 7, 9, 5, 8, 3, 6, 1, 7, 4, 2 }">
    <SparklineAxisSettings MinX="-1" MaxX="46" MaxY="10" MinY="-1">
    </SparklineAxisSettings>
    <SparklineTooltipSettings TValue="int" Visible="true">
        <SparklineTrackLineSettings Visible="true" Color="#033e96" Width="1">
        </SparklineTrackLineSettings>
    </SparklineTooltipSettings>
</SfSparkline>
```

![Sparkline Charts with track line](/images/UserInteraction/Trackline.png)
