---
title: " Chart DataLabel Template| ASP.NET Core Blazor  "

component: "Chart"

description: "How to section explains knowledge base samples and howto access different types properties and events of the chart."
---

<!-- markdownlint-disable MD036 -->

# DataLabel Template

You can bind text and interior information for a point from dataSource other than x and y value.

To access the aggregate values inside the Template, you can use the implicit named parameter context. You can type cast the context as IChartTemplate to get aggregate values inside template.

You can also change this implicit parameter name using Context attribute.

For example, you can access the data label template using context as follows.

```razor
        <ChartDataLabel Visible="true">
                    <Template>
                        @{
                            var data = context as IChartTemplate;
                            <table>
                                <tr><td align="center"> @data.Y</td></tr>
                            </table>
                        }
                    </Template>
         </ChartDataLabel>
  
```

{% aspTab template="chart/data-label-template", sourceFiles="data-label-template.razor" %}

{% endaspTab %}