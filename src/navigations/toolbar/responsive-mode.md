---
title: "Toolbar Responsive"
component: "Toolbar"
description: "Toolbar has responsive support to adapt toolbar component’s width based on the devices like mobile and tablet."
---

# Responsive Mode

This section explains the supported display modes of the Toolbar when the content exceeds the viewing area. Possible modes are:

* Scrollable
* Popup

## Scrollable

The default [OverflowMode](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Navigations.SfToolbar.html#Syncfusion_Blazor_Navigations_SfToolbar_OverflowMode) of the Toolbar is `Scrollable`. Scrollable display mode supports display of commands in a single line with horizontal scrolling enabled when commands overflow to available space.

* The right and left navigation arrows are added to the start and end of the Toolbar to navigate to hidden commands.
* You can also see the hidden commands using touch swipe action.
* By default, if navigation icon in the `left` side is disabled, you can see the hidden commands by moving to the `right`.
* By clicking the arrow or by holding the arrow continuously,  hidden commands will become visible.
* If device navigation icons are not available, you can touch swipe to see the hidden commands of the Toolbar.

![Scrollable](images/scrolling.gif)

* Once the Toolbar reaches the last or first command, the  corresponding navigation icon will be disabled and you can move to the opposite direction.

![Touch scroll](images/scrolling_touch.gif)

![Swipe scroll](images/scrolling_swipe.gif)

* You can continuously scroll the Toolbar content by holding the navigation icon.

![Long press scroll](images/scrolling_long_press.gif)

```csharp
@using Syncfusion.Blazor.Navigations

<SfToolbar Width="600">
    <ToolbarItems>
        <ToolbarItem Type="ItemType.Button" PrefixIcon="e-cut-icon" Text="Cut"></ToolbarItem>
        <ToolbarItem Type="ItemType.Button" PrefixIcon="e-copy-icon" Text="Copy"></ToolbarItem>
        <ToolbarItem Type="ItemType.Button" PrefixIcon="e-paste-icon" Text="Paste"></ToolbarItem>
        <ToolbarItem Type="ItemType.Separator"></ToolbarItem>
        <ToolbarItem Type="ItemType.Button" PrefixIcon="e-bold-icon" Text="Bold"></ToolbarItem>
        <ToolbarItem Type="ItemType.Button" PrefixIcon="e-underline-icon" Text="Underline"></ToolbarItem>
        <ToolbarItem Type="ItemType.Button" PrefixIcon="e-italic-icon" Text="Italic"></ToolbarItem>
        <ToolbarItem Type="ItemType.Button" PrefixIcon="e-color-icon" Text="Color-Picker"></ToolbarItem>
        <ToolbarItem Type="ItemType.Separator"></ToolbarItem>
        <ToolbarItem Type="ItemType.Button" PrefixIcon="e-ascending-icon" Text="A-Z Sort"></ToolbarItem>
        <ToolbarItem Type="ItemType.Button" PrefixIcon="e-descending-icon" Text="Z-A Sort"></ToolbarItem>
        <ToolbarItem Type="ItemType.Button" PrefixIcon="e-clear-icon" Text="Clear"></ToolbarItem>
    </ToolbarItems>
</SfToolbar>

<style>
    /* Toolbar Styles */
    .e-cut-icon:before {
        content: "\e604"
    }

    .e-copy-icon:before {
        content: "\e70a"
    }

    .e-paste-icon:before {
        content: "\e712"
    }

    .e-color-icon:before {
        content: "\e703";
    }

    .e-bold-icon:before {
        content: "\e339"
    }

    .e-underline-icon:before {
        content: "\e706";
    }

    .e-italic-icon:before {
        content: "\e710"
    }

    .e-ascending-icon:before {
        content: "\e70f";
    }

    .e-descending-icon:before {
        content: "\e707";
    }

    .e-clear-icon:before {
        content: "\e70d"
    }
</style>
```

## Popup

`Popup` is another type of `OverflowMode` in which the Toolbar container holds the commands that can be placed in the available space. The rest of the overflowing commands that do not fit within
the viewing area moves to the overflow popup container.

The commands placed in the popup can be viewed by opening the popup using the drop down icon given at the end of the Toolbar.

![Toolbar popup](./images/popup.gif)

> If the popup content overflows the height of the page, then the rest of the commands will be hidden.

### Priority of commands

Default popup priority is set as `None`, and when the commands of the Toolbar overflow, the ones listed last will be moved to the popup.

You can customize the priority of commands to be displayed on the Toolbar and popup by using the `Overflow` property.

Property     | Description
------------ | -------------
  Show       | Always shows items on the `Toolbar with primary` priority.
  Hide       | Always shows items in the `popup with secondary` priority.
  None       | No priority display, and as per the `normal order` commands are moved to popup when content exceeds viewing area.

If primary priority commands also exceed available space, they are moved to the popup container at top order position and placed before the secondary priority commands.

> You can maintain toolbar item on popup always by using the [ShowAlwaysInPopup](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Navigations.ToolbarItem.html#Syncfusion_Blazor_Navigations_ToolbarItem_ShowAlwaysInPopup) property, and this behavior is not applicable for toolbar items with [Overflow](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Navigations.ToolbarItem.html#Syncfusion_Blazor_Navigations_ToolbarItem_Overflow) property as 'Show'.

```csharp
@using Syncfusion.Blazor.Navigations

<SfToolbar Width="380" OverflowMode="OverflowMode.Popup">
    <ToolbarItems>
        <ToolbarItem Type="ItemType.Button" PrefixIcon="e-cut-icon" Text="Cut"></ToolbarItem>
        <ToolbarItem Type="ItemType.Button" PrefixIcon="e-copy-icon" Text="Copy"></ToolbarItem>
        <ToolbarItem Type="ItemType.Button" PrefixIcon="e-paste-icon" Text="Paste"></ToolbarItem>
        <ToolbarItem Type="ItemType.Separator"></ToolbarItem>
        <ToolbarItem Type="ItemType.Button" PrefixIcon="e-bold-icon" Text="Bold"></ToolbarItem>
        <ToolbarItem Type="ItemType.Button" PrefixIcon="e-underline-icon" Text="Underline"></ToolbarItem>
        <ToolbarItem Type="ItemType.Button" PrefixIcon="e-italic-icon" Text="Italic"></ToolbarItem>
        <ToolbarItem Type="ItemType.Button" PrefixIcon="e-color-icon" Text="Color-Picker"></ToolbarItem>
        <ToolbarItem Type="ItemType.Separator"></ToolbarItem>
        <ToolbarItem Type="ItemType.Button" PrefixIcon="e-ascending-icon" Text="A-Z Sort"></ToolbarItem>
        <ToolbarItem Type="ItemType.Button" PrefixIcon="e-descending-icon" Text="Z-A Sort"></ToolbarItem>
        <ToolbarItem Type="ItemType.Button" PrefixIcon="e-clear-icon" Text="Clear"></ToolbarItem>
    </ToolbarItems>
</SfToolbar>

<style>
    /* Toolbar Styles */
    .e-cut-icon:before {
        content: "\e604"
    }

    .e-copy-icon:before {
        content: "\e70a"
    }

    .e-paste-icon:before {
        content: "\e712"
    }

    .e-color-icon:before {
        content: "\e703";
    }

    .e-bold-icon:before {
        content: "\e339"
    }

    .e-underline-icon:before {
        content: "\e706";
    }  

    .e-clear-icon:before {
        content: "\e70d"
    }

    .e-italic-icon:before {
        content: "\e710"
    }

    .e-ascending-icon:before {
        content: "\e70f";
    }

    .e-descending-icon:before {
        content: "\e707";
    }
</style>
```

### Text mode for buttons

The `ShowTextOn` property is used to decide button text display area on the Toolbar, popup, or both. This is useful for customization of both text and image representation of commands.

For example, you can show icon only button on the Toolbar, and in the popup container display more information about the commands with icon and text.

Possible values are,

  Property   | Description
------------ | -------------
  Both     | Button text is visible in both `Toolbar` and `Popup`.
  Overflow | Button text is only visible in `Popup`.
  Toolbar  | Button text is only visible on the `Toolbar`.

In the following code sample, text is only visible in the popup container and not in the Toolbar container.

```csharp
@using Syncfusion.Blazor.Navigations

<SfToolbar Width="380" OverflowMode="OverflowMode.Popup">
    <ToolbarItems>
        <ToolbarItem Type="ItemType.Button" PrefixIcon="e-cut-icon" Text="Cut" ShowTextOn="DisplayMode.Overflow" Overflow="OverflowOption.Show"></ToolbarItem>
        <ToolbarItem Type="ItemType.Button" PrefixIcon="e-copy-icon" Text="Copy" ShowTextOn="DisplayMode.Overflow" Overflow="OverflowOption.Show"></ToolbarItem>
        <ToolbarItem Type="ItemType.Button" PrefixIcon="e-paste-icon" Text="Paste" ShowTextOn="DisplayMode.Overflow" Overflow="OverflowOption.Show"></ToolbarItem>
        <ToolbarItem Type="ItemType.Separator"></ToolbarItem>
        <ToolbarItem Type="ItemType.Button" PrefixIcon="e-bold-icon" Text="Bold" ShowTextOn="DisplayMode.Overflow" Overflow="OverflowOption.Show"></ToolbarItem>
        <ToolbarItem Type="ItemType.Button" PrefixIcon="e-underline-icon" Text="Underline" ShowTextOn="DisplayMode.Overflow" Overflow="OverflowOption.Show"></ToolbarItem>
        <ToolbarItem Type="ItemType.Button" PrefixIcon="e-italic-icon" Text="Italic" ShowTextOn="DisplayMode.Overflow" Overflow="OverflowOption.Show"></ToolbarItem>
        <ToolbarItem Type="ItemType.Button" PrefixIcon="e-color-icon" Text="Color-Picker" ShowTextOn="DisplayMode.Overflow" Overflow="OverflowOption.Show"></ToolbarItem>
        <ToolbarItem Type="ItemType.Separator"></ToolbarItem>
        <ToolbarItem Type="ItemType.Button" PrefixIcon="e-ascending-icon" Text="A-Z Sort" ShowTextOn="DisplayMode.Overflow" Overflow="OverflowOption.Show"></ToolbarItem>
        <ToolbarItem Type="ItemType.Button" PrefixIcon="e-descending-icon" Text="Z-A Sort" ShowTextOn="DisplayMode.Overflow" Overflow="OverflowOption.Show"></ToolbarItem>
        <ToolbarItem Type="ItemType.Button" PrefixIcon="e-clear-icon" Text="Clear" ShowTextOn="DisplayMode.Overflow" Overflow="OverflowOption.Show"></ToolbarItem>
    </ToolbarItems>
</SfToolbar>

<style>
    /* Toolbar Styles */
    .e-cut-icon:before {
        content: "\e604"
    }

    .e-copy-icon:before {
        content: "\e70a"
    }

    .e-paste-icon:before {
        content: "\e712"
    }

    .e-color-icon:before {
        content: "\e703";
    }

    .e-bold-icon:before {
        content: "\e339"
    }

    .e-underline-icon:before {
        content: "\e706";
    }

    .e-alignleft-icon:before {
        content: "\e717"
    }

    .e-alignright-icon:before {
        content: "\e715"
    }

    .e-aligncenter-icon:before {
        content: "\e704"
    }

    .e-alignjustify-icon:before {
        content: "\e71b"
    }

    .e-upload-icon:before {
        content: "\e71e"
    }

    .e-download-icon:before {
        content: "\e70a"
    }

    .e-indent-icon:before {
        content: "\e70b"
    }

    .e-outdent-icon:before {
        content: "\e700"
    }

    .e-clear-icon:before {
        content: "\e70d"
    }

    .e-reload-icon:before {
        content: "\e71c"
    }

    .e-export-icon:before {
        content: "\e720";
    }

    .e-italic-icon:before {
        content: "\e710"
    }

    .e-bullets-icon:before {
        content: "\e711";
    }

    .e-numbering-icon:before {
        content: "\e70e";
    }

    .e-ascending-icon:before {
        content: "\e70f";
    }

    .e-descending-icon:before {
        content: "\e707";
    }
</style>
```