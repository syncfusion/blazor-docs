# Types

The ChipList control has the following types.

* Input Chip
* Choice Chip
* Filter Chip
* Action Chip

## Input Chip

Input Chip holds information in compact form. It converts user input into chips.

```csharp
@using Syncfusion.EJ2.Blazor.Buttons

<EjsChipList>
    <ChipCollection>
        <ChipListChip Text="Anne" LeadingIconCss="anne"></ChipListChip>
        <ChipListChip Text="Janet" LeadingIconCss="janet"></ChipListChip>
        <ChipListChip Text="Laura" LeadingIconCss="laura"></ChipListChip>
        <ChipListChip Text="Margaret" LeadingIconCss="margaret"></ChipListChip>
    </ChipCollection>
</EjsChipList>

<style>
    .anne {
        background-image: url('./anne.png');
    }
    .janet {
        background-image: url('./janet.png');
    }
    .laura {
        background-image: url('./laura.png');
    }
    .margaret {
        background-image: url('./margaret.png');
    }
</style>

```

Output be like the below.

![Chip inputs](./images/inputChips.png)

## Choice Chip

Choice Chip allows you to select a single chip from the set of ChipList/ChipCollection. It can be enabled by setting the `Selection` property to `Single`.

```csharp

@using Syncfusion.EJ2.Blazor.Buttons

<EjsChipList Selection="Selection.Single">
    <ChipCollection>
        <ChipListChip Text="Small"></ChipListChip>
        <ChipListChip Text="Medium"></ChipListChip>
        <ChipListChip Text="Large"></ChipListChip>
        <ChipListChip Text="Extra Large"></ChipListChip>
    </ChipCollection>
</EjsChipList>

```

Output be like the below.

![Chip Choice](./images/choicechip.gif)

## Filter Chip

Filter Chip allows you to select a multiple chip from the set of ChipList/ChipCollection. It can be enabled by setting the `Selection` property to `Multiple`.

```csharp

@using Syncfusion.EJ2.Blazor.Buttons

<EjsChipList Selection="Selection.Multiple">
    <ChipCollection>
      <ChipListChip Text="Chai"></ChipListChip>
      <ChipListChip Text="Chang"></ChipListChip>
      <ChipListChip Text="Aniseed Syrup"></ChipListChip>
      <ChipListChip Text="Ikura"></ChipListChip>
    </ChipCollection>
</EjsChipList>

```

Output be like the below.

![Chip Filter](./images/filterchip.gif)

## Action Chip

The Action Chip triggers the event like click or delete, which helps doing action based on the event.

```csharp

@using Syncfusion.EJ2.Blazor.Buttons

<EjsChipList>
    <ChipListEvents OnClick="@OnClick"></ChipListEvents>
    <ChipCollection>
        <ChipListChip Text="Sent a text"></ChipListChip>
        <ChipListChip Text="Set a remainder"></ChipListChip>
        <ChipListChip Text="Read my emails"></ChipListChip>
        <ChipListChip Text="Set alarm"></ChipListChip>
    </ChipCollection>
</EjsChipList>
<div>@ChipText</div>

@code
{
    public string ChipText = "";
    private void OnClick(ClickEventArgs args)
    {
        ChipText = args.Text;
        this.StateHasChanged();
    }
}

```

Output be like the below.

![Chip Action](./images/actionchip.gif)

### Deletable Chip

Deletable Chip allows you to delete a chip from ChipList/ChipCollection. It can be enabled by setting the `EnableDelete` property to `true`.

```csharp

@using Syncfusion.EJ2.Blazor.Buttons

<EjsChipList EnableDelete="true">
    <ChipCollection>
        <ChipListChip Text="Sent a text"></ChipListChip>
        <ChipListChip Text="Set a remainder"></ChipListChip>
        <ChipListChip Text="Read my emails"></ChipListChip>
        <ChipListChip Text="Set alarm"></ChipListChip>
    </ChipCollection>
</EjsChipList>

```

Output be like the below.

![Chip Delete](./images/deletablechip.gif)