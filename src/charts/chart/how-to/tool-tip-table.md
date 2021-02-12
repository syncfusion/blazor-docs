---

component: "Chart"

---

# Create a table in tooltip

You can show the tooltip as table by using Template property in tooltip.

To access the aggregate values inside the Template, you can use the implicit named parameter context. You can type cast the context as `ChartTooltipInfo` to get aggregate values inside template

```razor
            <ChartTooltipSettings Enable="true">
                <Template>
                    @{
                        var data = context as ChartTooltipInfo;
                        <table>
                            <tr><td>Point Value: </td><td>@data.X : @data.Y</td></tr>
                            <tr><td><div id="chart_cloud"><img src="https://ej2.syncfusion.com/demos/src/chart/images/cloud.png" style="width: 41px; height: 41px" /></div></td></tr>
                        </table>
                    }
                </Template>
            </ChartTooltipSettings>

```

{% aspTab template="chart/how-to/tooltip", sourceFiles="tooltip.razor" %}

{% endaspTab %}