---
component: "Rich Text Editor"
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

<SfRichTextEditor Value="@Value" />

@code {
    private string Value { get; set; } = "<p>Syncfusion RichTextEditor</p>";
}

```

## Two-way data binding

The two-way data binding can be achieved by using the `@bind-Value` attribute from code-behind in Rich Text Editor.

The following example explains how to achieve two-way binding with textarea and the Rich Text Editor.

```csharp

@using Syncfusion.Blazor.RichTextEditor

<SfRichTextEditor @bind-Value="@Value" />

<br />

<textarea rows="5" cols="60" @bind="@Value" />

@code {
    private string Value { get; set; } = "<p>Syncfusion RichTextEditor</p>";
}

```

## Dynamic value binding

You can update the value dynamically by using the `Value` property.

The following example shows how to update a Rich Text Editor value dynamically on button click.

```csharp

@using Syncfusion.Blazor.Buttons
@using Syncfusion.Blazor.RichTextEditor

<SfButton @onclick="@Update">Update Value</SfButton>

<SfRichTextEditor Value="@Value" />

@code {
    private string Value { get; set; } = "<p>Syncfusion RichTextEditor</p>";

    private void Update()
    {
        this.Value = "<p>Dynamic Value</p>";
    }
}

```