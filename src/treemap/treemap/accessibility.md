
# Accessibility

The TreeMap component provides built-in compliance with [WAI-ARIA](http://www.w3.org/WAI/PF/aria-practices/) specifications. The WAI-ARIA accessibility supports are achieved using attributes such as `aria-label`. It helps to provide information about elements in a document for assistive technology.

**Aria-label:**

This attribute provides text label with some default description for the following elements in TreeMap.

<!-- markdownlint-disable MD033 -->
<table>
<tr>
<td><b>Element</b></td>
<td><b>Default description</b></td>
</tr>
<tr>
<td>TreeMap container</td>
<td>-</td>
</tr>
<tr>
<td>TreeMap Title</td>
<td>Reads the TreeMap title</td>
</tr>
<tr>
<td>TreeMap Subtitle</td>
<td>Reads the TreeMap subtitle</td>
</tr>
<tr>
<td>Legend Title</td>
<td>Reads the legend title</td>
</tr>
</table>

You can change this default description using the description property available in [`TreeMapLegendSettings`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeMap.TreeMapLegendSettings.html), [`TreeMapTitleSettings`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeMap.TitleSettingsModel.html), [`TreeMapSubTitleSettings`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeMap.SubTitleSettingsModel.html), and [`SfTreeMap`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/webtoc.html#) tags. It helps screen readers to read for assistive purpose.
