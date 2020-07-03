# Accessibility

## Keyboard Interaction

The following shortcut keys are used to access the Chip control without any interruption.

| Keyboard shortcuts | Actions |
|------------|-------------------|
| <kbd>Enter</kbd> | Selects the targeted chip from the ChipList/ChipCollection. |
| <kbd>Delete</kbd> | Deletes the targeted chip from the ChipList/ChipCollection. |

```csharp
@using Syncfusion.Blazor.Buttons
<SfChipList ID="chip-avatar" EnableDelete="true" Selection="Selection.Single">
    <ChipCollection>

        <ChipListChip Text="Andrew" AvatarIconCss='andrew'></ChipListChip>
        <ChipListChip Text="Janet" AvatarIconCss='janet'></ChipListChip>
        <ChipListChip Text="Laura" AvatarIconCss='laura'></ChipListChip>
        <ChipListChip Text="Margaret" AvatarIconCss='margaret'></ChipListChip>

    </ChipCollection>
</SfChipList>

<style>
    #chip-avatar .andrew {
        background-image: url('./andrew.png')
    }

    #chip-avatar .margaret {
        background-image: url('./margaret.png')
    }

    #chip-avatar .laura {
        background-image: url('./laura.png')
    }

    #chip-avatar .janet {
        background-image: url('./janet.png')
    }
</style>

```

Output be like the below.

![Chip with avatarIcon and selection](./images/accessibility.gif)