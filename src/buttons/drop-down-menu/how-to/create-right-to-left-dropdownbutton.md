---
title: "Create right-to-left Dropdown Menu"
component: "Dropdown Menu"
description: "Dropdown Menu how to section, hide drop down arrow, group popup items using list view component, dialog open on popup item click."
---

# Create right-to-left Dropdown Menu

Dropdown Menu component has RTL support. This can be achieved by setting [`EnableRtl`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.SplitButtons.SfDropDownButton~EnableRtl.html) as true.

The following example illustrates how to enable right-to-left support in Dropdown Menu component.

```csharp
@using Syncfusion.Blazor.SplitButtons

<SfDropDownButton Content="Message" IconCss="e-icons e-message" EnableRtl="true">
    <DropDownMenuItems>
        <DropDownMenuItem IconCss="e-icons e-edit" Text="Edit"></DropDownMenuItem>
        <DropDownMenuItem IconCss="e-icons e-delete" Text="Delete"></DropDownMenuItem>
        <DropDownMenuItem IconCss="e-icons e-like" Text="Like"></DropDownMenuItem>
    </DropDownMenuItems>
</SfDropDownButton>

<style>
    .e-message::before {
        content: '\e7cb';
    }

    .e-edit::before {
        content: '\e78f';
    }

    .e-delete::before {
        content: '\e773';
    }

    .e-like::before {
        content: '\e682';
    }

</style>

```

Output be like

![Button Sample](./../images/ddb-rtl.png)