---
title: "Split Button Popup Items"
component: "Split Button"
description: "Split Button allows the end user to customize the whole popup or action items in popup using templates, and to place icons in popup items."
---

# Popup Items

## Icons

The Popup action item have an icon or image to provide visual representation of the action. To place the icon on a popup
item, set the [`IconCss`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.SplitButtons.SfSplitButton~IconCss.html) property to `e-icons` with the required icon CSS. By default, the icon is positioned to the left side of the popup action item.

In the following sample, the icons for Cut, Copy, Paste menu items are added using the IconCss property.

```csharp
@using Syncfusion.Blazor.SplitButtons

<SfSplitButton Content="Paste" IconCss="e-icons e-paste">
    <DropDownMenuItems>
        <DropDownMenuItem IconCss="e-icons e-cut" Text="Cut"></DropDownMenuItem>
        <DropDownMenuItem IconCss="e-icons e-copy" Text="Copy"></DropDownMenuItem>
        <DropDownMenuItem IconCss="e-icons e-paste" Text="Paste"></DropDownMenuItem>
    </DropDownMenuItems>
</SfSplitButton>

<style>
    .e-paste::before {
        content: '\e739';
    }

    .e-cut::before {
        content: '\e73f';
    }

    .e-copy::before {
        content: '\e77b';
    }

</style>

```

Output be like

![Split Button Sample](./images/sb-icons.png)

## Template

### Item Templating

Popup items can be customized by using the [`OnItemRender`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.SplitButtons.SfSplitButton~OnItemRender.html) event. The item render event triggers while rendering each Popup action item. The event argument will be used to customize the items based on the requirement.

```csharp

@using Syncfusion.Blazor.SplitButtons

<SfSplitButton Content="Edit">
    <SplitButtonEvents OnItemRender="Render"></SplitButtonEvents>
    <DropDownMenuItems>
        <DropDownMenuItem Text="Cut" ></DropDownMenuItem>
        <DropDownMenuItem Text="Copy" ></DropDownMenuItem>
        <DropDownMenuItem Text="Paste"></DropDownMenuItem>
    </DropDownMenuItems>
</SfSplitButton>

@code {
    public void Render(MenuEventArgs args)
    {
        args.Element.AddClass(new string[] { "custom" });
    }
}

<style>
    .custom {
        float: left;
        font-size: 10px;
        padding-left: 50px;
        font-style: oblique;
    }
</style>

```

Output be like

![Split Button Sample](./images/sb-template.png)