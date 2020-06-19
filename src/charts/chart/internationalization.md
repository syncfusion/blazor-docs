---
title: " Chart Internationalization | ASP.NET Core Blazor "

component: "Chart"

description: "Chart provides the support for internationalization for dataLabel, axis label and tooltip elements."
---

# Internationalization

Chart provide supports for internationalization for below chart elements.

* Datalabel.
* Axis label.
* Tooltip.

<!-- markdownlint-disable MD036 -->
**Globalization**

Globalization is the process of designing and developing an component that works in different
cultures/locales.  Internationalization  library is used to globalize number, date, time values in
Chart component using [`LabelFormat`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.ChartAxis~LabelFormat.html) property in axis.

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