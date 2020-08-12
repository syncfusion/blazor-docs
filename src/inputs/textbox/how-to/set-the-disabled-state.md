---
title: "Set the disabled state"
component: "Textbox"
description: "Explains how to disable the user interaction on the text box component."
---

# Set the disabled state

To disable the TextBox, use its
[Enabled](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.Blazor~Syncfusion.Blazor.Inputs.SfTextBox~Enabled.html)
property.

The following example demonstrates the TextBox in
a disabled state.

```csharp
@using Syncfusion.Blazor.Inputs

<SfTextBox Placeholder='First Name' Enabled=false></SfTextBox>
```

The output will be as follows.

![textbox](../images/disabled.png)