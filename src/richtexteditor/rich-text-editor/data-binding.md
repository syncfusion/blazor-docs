---
title: "Blazor Rich Text Editor | HTML Editor | Two-way binding"
component: "Rich Text Editor"
description: "This section explains how to achieve one-way, two-way, and dynamic value binding using Value property of the Blazor Rich Text Editor (Blazor HTML Editor)."
---

# Data Binding

This section explains how to bind the `Value` to the Rich Text Editor component that can be achieved in the following ways:

* One-way data binding
* Two-way data binding
* Dynamic value binding

## One-way data binding

You can bind the value to the Rich Text Editor by using the `Value` property directly as string or from code-behind as the following example.

```csharp

@using Syncfusion.Blazor.RichTextEditor

<SfRichTextEditor Value="@RTEValue" />

@code {
    private string RTEValue { get; set; } = "Syncfusion RichTextEditor";
}

```

## Two-way data binding

The two-way data binding can be achieved by using the `@bind-Value` attribute from code-behind in Rich Text Editor.

The following example explains how to achieve two-way binding with textarea and the Rich Text Editor.

```csharp

@using Syncfusion.Blazor.RichTextEditor

<SfRichTextEditor @bind-Value="@RTEValue" />

<textarea @bind="@RTEValue" />

@code {
    private string RTEValue { get; set; } = "Syncfusion RichTextEditor";
}

```

## Dynamic value binding

You can update the value dynamically by using the `Value` property.

The following example shows how to update a Rich Text Editor value dynamically on button click.

```csharp

@using Syncfusion.Blazor.RichTextEditor
@using Syncfusion.Blazor.Buttons

<SfButton @onclick="OnClicked">Update Value</SfButton>

<SfRichTextEditor Value="@RTEValue" />

@code {
    private string RTEValue { get; set; } = "Syncfusion RichTextEditor";

    private void OnClicked()
    {
        this.RTEValue = "Dynamic Value";
    }
}

```