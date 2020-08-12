---
title: "Data-Binding"
component: "MaskedTextBox"
description: "This section helps to learn how to bind the value in ASP.NET Core Blazor application"
---

# Data Binding

This section briefly explains how to bind the value to the MaskedTextBox component in the following different ways:

* One-way data binding
* Two-way data binding
* Dynamic value binding

## One-way binding

You can bind the value to the MaskedTextBox component directly for `Value` property as mentioned in the following code example. In one-way binding, you have to pass the property or variable name along with `@` (For Ex: "@MaskValue").

```csharp
@using Syncfusion.Blazor.Inputs

<SfMaskedTextBox Mask="00000" Value=@MaskValue></SfMaskedTextBox>

<button @onclick="@UpdateValue">Update Value</button>

@code {

    public string MaskValue { get; set; } = "12345";

    public void UpdateValue()
    {
        MaskValue = "67890";
    }
}
```

## Two-way data binding

Two-way binding can be achieved by using the `bind-Value` attribute and it supports string, int, Enum, DateTime, bool types. If component value has been changed, it will affect the all places where you bind the variable for the **bind-value** attribute.

```csharp
@using Syncfusion.Blazor.Inputs

<p>MaskedTextBox value is: @MaskValue</p>

<SfMaskedTextBox @bind-Value="@MaskValue"></SfMaskedTextBox>

@code {
    public string MaskValue { get; set; } = "12345";
}
```

## Dynamic Value Binding

You can change the property value dynamically by manually calling the `StateHasChanged()` method inside public event of **Blazor MaskedTextBox component** only. This method notifies the component that its state has changed and queues a re-render.

There is no need to call this method for native events since it is called after any lifecycle method has been called and can also be invoked manually to trigger a re-render. Refer to the following code example.

```csharp
@using Syncfusion.Blazor.Inputs

<p>MaskedTextBox value is: @MaskValue</p>

<SfMaskedTextBox Value="@MaskValue" ValueChange="@onChange"></SfMaskedTextBox>

@code {

    public string MaskValue { get; set; } = "Syncfusion";

    private void onChange(MaskChangeEventArgs args)
    {
       MaskValue = args.Value;
       StateHasChanged();
    }
}
```
