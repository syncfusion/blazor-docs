# Internationalization

Chart provide supports for internationalization for below chart elements.

* Datalabel.
* Axis label.
* Tooltip.

<!-- markdownlint-disable MD036 -->
**Globalization**

Globalization is the process of designing and developing an component that works in different
cultures/locales.  Internationalization  library is used to globalize number, date, time values in
Chart component using [`LabelFormat`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartAxis.html#Syncfusion_Blazor_Charts_ChartAxis_LabelFormat) property in axis.

**Numeric Format**

In the below example axis, point  and tooltip labels are globalized to EUR.

{% aspTab template="chart/number-format", sourceFiles="number-format.razor" %}

{% endaspTab %}

![Globalization](images/internationalization.png)

## See Also

* [Data label](./data-labels)
* [Tooltip](./tool-tip)
* [Legend](./legend)
* [Marker](./data-markers)