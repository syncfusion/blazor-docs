---
title: " Chart How To | ASP.NET Core Blazor "

component: "Chart"

description: "How to section explains knowledge base samples and howto access different types properties and events of the chart."
---

<!-- markdownlint-disable MD036 -->

# Mark a threshold in chart

You can mark a threshold in chart by using the `ChartStripLine`.

To mark a threshold in chart, follow the given steps:

**Step 1**:

By using the start and end properties of `ChartStripLines` object in vertical axis, you can mark the threshold
for y values of the series.

```razor
 <ChartPrimaryYAxis>
        <ChartStripLines>
            <ChartStripLine Start="30" SizeType="SizeType.Pixel" Color="red"></ChartStripLine>
        </ChartStripLines>
  </ChartPrimaryYAxis>

  ```

{% aspTab template="chart/how-to/threshold", sourceFiles="threshold.razor" %}

{% endaspTab %}
