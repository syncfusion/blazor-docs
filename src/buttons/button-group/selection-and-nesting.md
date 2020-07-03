---
title: "ButtonGroup Selection and Nesting"
component: "ButtonGroup"
description: "ButtonGroup supports single selection, multiple selection, nesting with dropdownbutton and splitbutton components."
---

# Selection and Nesting

## Selection

### Single selection

ButtonGroup supports radio type selection in which only one button can be selected. This can be achieved by adding input element
along with `id` attribute with its corresponding label along with `for` attribute inside the target element. In this ButtonGroup,
the type of the input element should be `radio` and `e-btn` is added to the `label` element.

The following example illustrates the single selection behavior in ButtonGroup.

`Index.razor`

```csharp

  <div class='e-btn-group'>
    <input type="radio" Id="radioleft" name="align" value="left" />
    <label class="e-btn" for="radioleft">Left</label>
    <input type="radio" Id="radiomIddle" name="align" value="mIddle" />
    <label class="e-btn" for="radiomIddle">Center</label>
    <input type="radio" Id="radioright" name="align" value="right" />
    <label class="e-btn" for="radioright">Right</label>
</div>

  ```

### Multiple selection

ButtonGroup supports checkbox type selection in which multiple button can be selected. This can be achieved by adding input element
along with `id` attribute with its corresponding label along with `for` attribute inside the target element. In this ButtonGroup,
the type of the input element should be `checkbox` and `e-btn` is added to the `label` element.

The following example illustrates the multiple selection behavior in ButtonGroup.

`Index.razor`

```csharp

   <div class='e-btn-group'>
    <input type="checkbox" Id="checkbold" name="font" value="bold" />
    <label class="e-btn" for="checkbold">Bold</label>
    <input type="checkbox" Id="checkitalic" name="font" value="italic" />
    <label class="e-btn" for="checkitalic">Italic</label>
    <input type="checkbox" Id="checkline" name="font" value="underline" />
    <label class="e-btn" for="checkline">Underline</label>
</div>

  ```

## Nesting

Nesting with other components can be possible in ButtonGroup. The following components can be nested in ButtonGroup.
* DropDownButton
* SplitButton

### DropDownButton

To initialize DropDownButton component refer [`DropDownButton Getting Started documentation`](./../../drop-down-button/getting-started).

In the following example, the DropDownButton component is rendered in ButtonGroup.

`Index.razor`

```csharp
@using Syncfusion.EJ2.RazorComponents.Navigations

<div class='e-btn-group'>
    <EjsButton ID="html" Content="HTML"></EjsButton>
    <EjsButton ID="css" Content="CSS"></EjsButton>
    <EjsButton ID="javascript" Content="Javascript"></EjsButton>
    <EjsDropDownButton ID="element" Content="More" Items="@items"></EjsDropDownButton>
</div>

@functions {

    public List<MenuItem> items { get; set; } = new List<MenuItem>
{
    new MenuItem{ Text = "Learn SQL" },
    new MenuItem{ Text = "Notifications"},
    new MenuItem{ Text = "User Settings" }
    };

}

  ```

### SplitButton

To initialize SplitButton component refer [`SplitButton Getting Started documentation`](./../../split-button/getting-started).

In the following example, the SplitButton component is rendered in ButtonGroup.

`Index.razor`

```csharp
@using Syncfusion.EJ2.RazorComponents.Navigations

  <div class='e-btn-group'>
    <EjsButton ID="cut" Content="Cut"></EjsButton>
    <EjsButton ID="copy" Content="Copy"></EjsButton>
    <EjsSplitButton ID="element" Content="Paste" Items="@items"></EjsSplitButton>
</div>

@functions {

public List<MenuItem> items { get; set; } = new List<MenuItem>
{
    new MenuItem{ Text = "Paste" },
    new MenuItem{ Text = "Paste Text"},
    new MenuItem{ Text = "Paste Special" }
    };
}
  ```

## See Also

* [Show ButtonGroup selected state on initial render](./how-to/show-buttongroup-selected-state-on-initial-render)
