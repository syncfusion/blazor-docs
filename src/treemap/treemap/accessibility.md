---
title: "Accessibility in the Blazor TreeMap component | Syncfusion"

component: "TreeMap"

description: "Learn here all about the Accessibility of Syncfusion TreeMap (SfTreeMap) component and more."
---

# Accessibility in the Blazor TreeMap (SfTreeMap)

The TreeMap component provides built-in compliance with the [WAI-ARIA](http://www.w3.org/WAI/PF/aria-practices/) specifications. The WAI-ARIA accessibility supports are achieved using attributes such as `aria-label`. It helps to provide information about the elements in a document for assistive technology.

**Aria-label:**

This attribute provides text label with some default description for the following elements in the TreeMap.

<!-- markdownlint-disable MD033 -->
<table>
<tr>
<td><b>Element</b></td>
<td><b>Default description</b></td>
</tr>
<tr>
<td>TreeMap container</td>
<td>Reads the TreeMap description</td>
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

Change this default description using the `Description` property available in the [`TreeMapLegendSettings`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor.TreeMap.TreeMapLegendSettings.html), [`TreeMapTitleSettings`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.TreeMap.TreeMapTitleSettings.html), [`TreeMapSubTitleSettings`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.TreeMap.TreeMapSubtitleSettings.html), and [`SfTreeMap`](https://help.syncfusion.com/cr/blazor). It helps screen readers to read for assistive purpose.
