---
title: "Create Dropdown Menu with rounded corner"
component: "Dropdown Menu"
description: "Dropdown Menu how to section, hide drop down arrow, group popup items using list view component, dialog open on popup item click."
---

# Create Dropdown Menu with rounded corner

Dropdown Menu with rounded corner can be achieved by adding `border-radius` CSS property to button element.

In the following example, `e-round-corner` class is defined with `5px` `border-radius`
property and added that class to button element using
[`CssClass`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.SplitButtons.SfDropDownButton~CssClass.html) property.

```csharp
@using Syncfusion.Blazor.SplitButtons

<SfDropDownButton CssClass="e-round-corner" Content="Clipboard">
    <DropDownButtonItems>
        <DropDownButtonItem Text="Edit"></DropDownButtonItem>
        <DropDownButtonItem Text="Copy"></DropDownButtonItem>
        <DropDownButtonItem Text="Paste"></DropDownButtonItem>
    </DropDownButtonItems>
</SfDropDownButton>

<style>
    .e-round-corner {
        border-radius: 5px;
    }
</style>

```

Output be like

![Button Sample](./../images/ddb-rounded.png)