---
title: "Customize icon and width"
component: "Dropdown Menu"
description: "Dropdown Menu how to section, hide drop down arrow, group popup items using list view component, dialog open on popup item click."
---

# Customize icon and width

Width of the Dropdown Menu can be customized by setting required width to the dropdown element.

The following UI can be achieved by setting [`IconPosition`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.SplitButtons.SfDropDownButton~IconPosition.html) as `Top`, width as `85px` and size of the font icon as `40px` by adding `e-custom` class.

```csharp
@using Syncfusion.Blazor.SplitButtons

<SfDropDownButton IconCss="e-icons e-search" CssClass="e-custom" IconPosition ="SplitButtonIconPosition.Top" Content="Search">
  <DropDownButtonItems>
      <DropDownButtonItem Text="Find"></DropDownButtonItem>
      <DropDownButtonItem Text="Replace"></DropDownButtonItem>
      <DropDownButtonItem Text="Go To"></DropDownButtonItem>
  </DropDownButtonItems>
</SfDropDownButton>

<style>

.e-search::before {
  content: '\ec0d';
}

.e-dropdown-btn.e-custom {
  width: 85px;
}

.e-dropdown-btn.e-custom .e-search::before {
  font-size: 40px;
}
</style>
```

Output be like

![Button Sample](./../images/ddb-custom.png)