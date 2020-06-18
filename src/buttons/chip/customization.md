# Chip Customization

This section explains the customization of styles, leading icons, avatar, and trailing icons in Chip control.

## Styles

The Chip control has the following predefined styles that can be defined using the `CssClass` property.

| Class | Description |
| -------- | -------- |
| e-primary | Represents a primary chip. |
| e-success | Represents a positive chip. |
| e-info |  Represents an informative chip. |
| e-warning | Represents a chip with caution. |
| e-danger | Represents a negative chip. |

```csharp

@using Syncfusion.EJ2.Blazor.Buttons

<EjsChipList>
    <ChipCollection>
                <ChipListChip Text="Default"></ChipListChip>
                <ChipListChip Text="Primary" CssClass="e-primary"></ChipListChip>
                <ChipListChip Text="Success" CssClass="e-success"></ChipListChip>
                <ChipListChip Text="Info" CssClass="e-info"></ChipListChip>
                <ChipListChip Text="Warning" CssClass="e-warning"></ChipListChip>
                <ChipListChip Text="Danger" CssClass="e-danger"></ChipListChip>
    </ChipCollection>
</EjsChipList>

```

Output be like the below.

![Chip Styles](./images/styleChip.png)

## Leading Icon

You can add and customize the leading icon of chip using the `LeadingIconCss` property.

```csharp

@using Syncfusion.EJ2.Blazor.Buttons

<EjsChipList EnableDelete="true" CssClass="chip-avatar">
    <ChipCollection>
        <ChipListChip Text="Anne" LeadingIconCss="anne"></ChipListChip>
        <ChipListChip Text="Janet" LeadingIconCss="janet"></ChipListChip>
        <ChipListChip Text="Laura" LeadingIconCss="laura"></ChipListChip>
        <ChipListChip Text="Margaret" LeadingIconCss="margaret"></ChipListChip>
    </ChipCollection>
</EjsChipList>

<style>
    .chip-avatar .anne {
        background-image: url('./anne.png')
    }
    .chip-avatar .margaret {
        background-image: url('./margaret.png')
    }
    .chip-avatar .laura {
        background-image: url('./laura.png')
    }
    .chip-avatar .janet {
        background-image: url('./janet.png')
    }
</style>

```

Output be like the below.

![Chip LeadingIcon](./images/leadingIcon.gif)

## Avatar

You can add and customize the avatar of chip using the `AvatarIconCss` property.

```csharp

@using Syncfusion.EJ2.Blazor.Buttons

<EjsChipList EnableDelete="true" CssClass="chip-avatar">
    <ChipCollection>
        <ChipListChip Text="Andrew" AvatarIconCss="andrew"></ChipListChip>
        <ChipListChip Text="Janet" AvatarIconCss="janet"></ChipListChip>
        <ChipListChip Text="Laura" AvatarIconCss="laura"></ChipListChip>
        <ChipListChip Text="Margaret" AvatarIconCss="margaret"></ChipListChip>
    </ChipCollection>
</EjsChipList>

<style>
    .chip-avatar .andrew {
        background-image: url('./andrew.png')
    }
    .chip-avatar .margaret {
        background-image: url('./margaret.png')
    }
    .chip-avatar .laura {
        background-image: url('./laura.png')
    }
    .chip-avatar .janet {
        background-image: url('./janet.png')
    }
</style>

```

Output be like the below.

![Chip Avatar Icon](./images/avatar.gif)

## Avatar Content

You can add and customize the avatar content of chip using the `AvatarText` property.

```csharp

@using Syncfusion.EJ2.Blazor.Buttons

<EjsChipList EnableDelete="true">
    <ChipCollection>
        <ChipListChip Text="Andrew" AvatarText="A"></ChipListChip>
        <ChipListChip Text="Janet" AvatarText="J"></ChipListChip>
        <ChipListChip Text="Laura" AvatarText="L"></ChipListChip>
        <ChipListChip Text="Margaret" AvatarText="M"></ChipListChip>
    </ChipCollection>
</EjsChipList>

```

Output be like the below.

![Chip Avatar Text](./images/avatarcontent.gif)

## Trailing Icon

You can add and customize the trailing icon of chip using the `TrailingIconCss` property.

```csharp

@using Syncfusion.EJ2.Blazor.Buttons

<EjsChipList>
    <ChipCollection>
        <ChipListChip Text="Andrew" TrailingIconCss="e-dlt-btn"></ChipListChip>
        <ChipListChip Text="Janet" TrailingIconCss="e-dlt-btn"></ChipListChip>
        <ChipListChip Text="Laura" TrailingIconCss="e-dlt-btn"></ChipListChip>
        <ChipListChip Text="Margaret" TrailingIconCss="e-dlt-btn"></ChipListChip>
    </ChipCollection>
</EjsChipList>

```

Output be like the below.

![Chip TrailingIcon](./images/trailingIcon.png)

## Outline Chip

Outline chip has the border with the background transparent. It can be set using the `CssClass` property.

```csharp

@using Syncfusion.EJ2.Blazor.Buttons

<EjsChipList EnableDelete="true" CssClass="e-outline">
    <ChipCollection>
        <ChipListChip Text="Andrew"></ChipListChip>
        <ChipListChip Text="Janet"></ChipListChip>
        <ChipListChip Text="Laura"></ChipListChip>
        <ChipListChip Text="Margaret"></ChipListChip>
    </ChipCollection>
</EjsChipList>

```

Output be like the below.

![Chip Outline](./images/outlinechip.gif)
