# User Interaction

The Sparkline Charts have two user interaction features: tooltip and tracker line.

## Tooltip

The Sparkline Charts provides options to display details about values of data points through tooltips when hovering the mouse over data point.

The following code example demonstrates how to enable tooltip for Sparkline Charts with format.

```csharp
@using Syncfusion.Blazor.Charts

<SfSparkline Width="500"
              Height="200"
              TValue="WorkLog"
              DataSource="WorkLogs"
              Xname="Day"
              YName="Hour"
              Fill="blue"
              ValueType="SparklineValueType.Category">
    <SparklineAxisSettings MinX="-1" MaxX="7" MaxY="8" MinY="-1"></SparklineAxisSettings>
    <SparklineTooltipSettings Visible="true" Format="${Day} : ${Hour}"></SparklineTooltipSettings>
</SfSparkline>

@code {
    public class WorkLog
    {
        public string Day;
        public double Hour;
    };
    private List<WorkLog> WorkLogs = new List<WorkLog> {
        new WorkLog {Day= "Mon", Hour= 3 },
        new WorkLog {Day= "Tue", Hour= 5 },
        new WorkLog {Day= "Wed", Hour= 2 },
        new WorkLog {Day= "Thu", Hour= 4 },
        new WorkLog {Day= "Fri", Hour= 6 }
    };
}
```

![Sparkline Charts with tooltip](./images/UserInteraction/Tooltip.png)

### Tooltip customization

Following data label properties can be customized using `SparklineDataLabelSettings` tag.

* `Fill` - Specifies fill color for tooltip
* `Format` - To set custom content in the tooltip
* `SparklineTooltipTextStyle` - To customize tooltip font family, style, weight, color, opacity and size
* `SparklineTooltipBorder` - To customize tooltip border width and color

The following code example shows customizing tooltip format, text color and fill color.

```csharp
@using Syncfusion.Blazor.Charts

<SfSparkline Width="500"
              Height="200"
              TValue="WorkLog"
              DataSource="WorkLogs"
              Xname="Day"
              YName="Hour"
              Fill="blue"
              ValueType="SparklineValueType.Category">
    <SparklineAxisSettings MinX="-1"
                           MaxX="7"
                           MaxY="8"
                           MinY="-1">
    </SparklineAxisSettings>
    <SparklineTooltipSettings Visible="true"
                              Format="${Day} : ${Hour}"
                              Fill="lightgray">
        <SparklineTooltipTextStyle Color="darkblue"></SparklineTooltipTextStyle>
    </SparklineTooltipSettings>
</SfSparkline>
```

> Refer [code block](#tooltip) to know the property value of `WorkLogs`.

![Sparkline with custom tooltip](./images/UserInteraction/TooltipCustomization.png)

## Track line

The track line tracks the data points that are closer to the mouse position or touch contact.

To enable track lines for Sparkline Charts, set the [`Visible`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.SparklineTrackLineSettings~ChildContent.html) option of  [`SparklineTrackLineSettings`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.SparklineTrackLineSettings.html) to true. Based on theme, the tracker color will be changed. The default value of the tracker color is black.

```csharp
@using Syncfusion.Blazor.Charts

<SfSparkline Width="500px"
              Height="200px"
              DataSource="new int[]{ 5, 3, 4, 6, 8, 7, 9, 1, 3, 5, 3, 4, 6, 8, 7, 9, 1, 3, 5, 2, 4, 6, 7, 9, 5, 8, 3, 6, 1, 7, 4, 2, 5, 2, 4, 6, 7, 9, 5, 8, 3, 6, 1, 7, 4, 2 }">
    <SparklineAxisSettings MinX="-1"
                           MaxX="46"
                           MaxY="10"
                           MinY="-1">
    </SparklineAxisSettings>
    <SparklineTooltipSettings Visible="true">
        <SparklineTrackLineSettings Visible="true"
                                    Color="#033e96"
                                    Width="1">
        </SparklineTrackLineSettings>
    </SparklineTooltipSettings>
</SfSparkline>
```

![Sparkline Charts with track line](./images/UserInteraction/Trackline.png)