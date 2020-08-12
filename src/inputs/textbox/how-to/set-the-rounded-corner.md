---
title: "Set the rounded corner"
component: "Textbox"
description: "Explains how to render the text box component with a rounded corner."
---

# Set the rounded corner

Render the TextBox with `rounded corner` by adding the `e-corner` class to the input parent element.

```csharp
@using Syncfusion.Blazor.Inputs

<SfTextBox Placeholder='First Name' CssClass="e-corner"></SfTextBox>
<style>
    .e-input-group.e-corner {
        border-radius: 4px;
    }
</style>
```