---
title: "Split Button Icons and Separator"
component: "Split Button"
description: "Split Button allows the end user to place the icons and separate popup items in Split Button."
---

# Icons

## Split Button Icons

Split Button can have an icon to provide the visual representation of the action. To place the icon on a
Split Button,set the [`IconCss`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.SplitButtons.SfSplitButton~IconCss.html) property to `e-icons` with the required icon CSS. By default, the icon is positioned to the left side of the Split Button. You can customize the icon's position by using the [`IconPosition`](https://help.syncfusion.com/cr/blazor/yncfusion.Blazor~Syncfusion.Blazor.SplitButtons.SfSplitButton~IconPosition.html) property

The following example illustrates how to place icon in Split Button component.

```csharp
@using Syncfusion.Blazor.SplitButtons

<SfSplitButton Items="@SplitbtnItems" Content="Paste" IconCss="e-icons e-paste"></SfSplitButton>
<SfSplitButton Items="@SplitbtnItems" Content="Paste" IconCss="e-icons e-paste" IconPosition="SplitButtonIconPosition.Top"></SfSplitButton>

@code{
    public List<SplitButtonItem> SplitbtnItems = new List<SplitButtonItem>
    {
        new SplitButtonItem{ Text="Cut" },
        new SplitButtonItem{ Text="Copy" },
        new SplitButtonItem{ Text="Paste" }
    };
}

<style>
    .e-paste::before {
        content: '\e501';
    }
</style>

```

Output be like

![Split Button Sample](./images/sb-icon.png)

You can also use third party icons on the Split Button using the [`IconCss`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.SplitButtons.SfSplitButton~IconCss.html) property.

## Vertical Button

Vertical Button in Split Button can be achieved by adding `e-vertical` class using [`CssClass`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.SplitButtons.SfSplitButton~CssClass.html) property.

The following example illustrates how to vertical support in Split Button component.

```csharp
@using Syncfusion.Blazor.SplitButtons

<SfSplitButton Content="Paste" IconCss="e-icons e-paste" CssClass="e-vertical">
    <SplitButtonItems>
        <SplitButtonItem Text="Cut" ></SplitButtonItem>
        <SplitButtonItem Text="Copy" ></SplitButtonItem>
        <SplitButtonItem Text="Paste"></SplitButtonItem>
    </SplitButtonItems>
</SfSplitButton>

<style>
    .e-paste::before {
        content: '\e501';
    }
</style>

```

Output be like

![Split Button Sample](./images/sb-vertical.png)

## Separator

The Separators are the horizontal lines that are used to separate the popup items. You cannot select the separators. You can enable separators to group the popup items using the separator property.

The following example illustrates how to enable [`Separator`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.SplitButtons.ItemModel~Separator.html) support in Split Button component.

```csharp
@using Syncfusion.Blazor.SplitButtons

<SfSplitButton Content="Paste" IconCss="e-icons e-paste" CssClass="e-vertical">
    <SplitButtonItems>
        <SplitButtonItem Text="Cut" ></SplitButtonItem>
        <SplitButtonItem Text="Copy" ></SplitButtonItem>
        <SplitButtonItem Text="Paste"></SplitButtonItem>
    </SplitButtonItems>
</SfSplitButton>

<style>
    .e-paste::before {
        content: '\e501';
    }
</style>

```

Output be like

![Split Button Sample](./images/sb-separator.png)

## See Also

* [Split Button popup with icons](./popup-items#icons)
