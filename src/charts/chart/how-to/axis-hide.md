---
title: " Chart How To | ASP.NET Core Blazor "

component: "Chart"

description: "How to section explains knowledge base samples and howto access different types properties and events of the chart."
---

<!-- markdownlint-disable MD036 -->

# Hide axis line when clicking the legend

By using the `OnChartMouseClick` event, you can hide the axis line through legend.

To hide the axis line through legend click, follow the given steps:

**Step 1**:

Create a chart with multiple axes.

By using the `OnChartMouseClick`event, you can get the legend's target ids. Using this event, you can also get the `YAxisName` of each axis, based on which you can hide the axis line when clicking the legend.

```razor
<ChartEvents OnChartMouseClick="@ChartMouseClick"></ChartEvents>
 public void ChartMouseClick(IMouseEventArgs Args)
        {
            Int32 Id;
            if (((Args.Target).IndexOf("chart_legend_text") > -1) || ((Args.Target).IndexOf("chart_legend_shape") > -1))
            {
                if ((Args.Target).IndexOf("chart_legend_text") > -1)
                {
                    Id = Int32.Parse((Args.Target).Split("chart_legend_text_")[1]);
                }
                else
                {
                    Id = Int32.Parse(Args.Target.Split("chart_legend_shape_")[1]);

                }
                if (Id == 0)
                {
                    this.AxisVisible1 = this.SeriesVisible1 = !this.SeriesVisible1;
                }
                else if (Id == 1)
                {
                    this.AxisVisible2 = this.SeriesVisible2 = !this.SeriesVisible2;
                }
                else
                {
                    this.AxisVisible3 = this.SeriesVisible3 = !this.SeriesVisible3;
                }
            }
        }

  ```

{% aspTab template="chart/how-to/axis-hide", sourceFiles="axis-hide.razor" %}

{% endaspTab %}
