---
title: "Disable a Dropdown Menu"
component: "Dropdown Menu"
description: "Dropdown Menu how to section, hide drop down arrow, group popup items using list view component, dialog open on popup item click."
---

# Disable a Dropdown Menu

Dropdown Menu component can be enabled/disabled by giving [`Disabled`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.SplitButtons.SfDropDownButton~Disabled.html) property.
To disable Dropdown Menu component, the disabled property can be set as `true`.

```csharp
@using Syncfusion.Blazor.SplitButtons

<SfDropDownButton Disabled="true" Content="Message">
    <DropDownButtonItems>
        <DropDownButtonItem Text="Edit"></DropDownButtonItem>
        <DropDownButtonItem Text="Delete"></DropDownButtonItem>
        <DropDownButtonItem Text="Mark as Read"></DropDownButtonItem>
        <DropDownButtonItem Text="Like Message"></DropDownButtonItem>
    </DropDownButtonItems>
</SfDropDownButton>
```

Output be like

![Button Sample](./../images/ddb-disable.png)