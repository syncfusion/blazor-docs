---
component: "TextBox"
---

# Sizing

You can render the TextBox in two different sizes:

Property   | Description
------------ | -------------
  Normal     | By default, the TextBox is rendered with normal size.
  Small      | You need to add `e-small` class to the input element, or else add to the input container.

```csharp
@using Syncfusion.Blazor.Inputs

<label>Normal</label>
<SfTextBox Placeholder="Enter text"></SfTextBox>

<label>Float input</label>
<SfTextBox Placeholder="Focus the input" FloatLabelType="@FloatLabelType.Auto"></SfTextBox>

<label>Small</label>
<SfTextBox Placeholder="Enter text" CssClass="e-small"></SfTextBox>

<label>Float input</label>
<SfTextBox Placeholder="Focus the input" CssClass="e-small" FloatLabelType="@FloatLabelType.Auto"></SfTextBox>
```

The output will be as follows.

![TextBox](./images/sizing.png)
