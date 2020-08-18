---
title: "Blazor Rich Text Editor | how to | Customize the placeholder"
component: "Rich Text Editor"
description: "This section explains how to customize the font style of placeholder to monospace in the Blazor Rich Text Editor component."
---

# Customize placeholder style

By using `rte-placeholder` class, you can customize the placeholder style.

```csharp

@using Syncfusion.Blazor.RichTextEditor

<SfRichTextEditor Placeholder="Type Something" />

<style>
    .e-richtexteditor .rte-placeholder {
        /* placeholder style */
        font-family: monospace;
        color: deeppink;
    }
</style>

```

The output will be as follows.

![Placeholder Edit](../images/placeholder-edit.png)