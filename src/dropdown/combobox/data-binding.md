---
title: "Data-Binding"
component: "ComboBox"
description: "This section helps to learn how to bind the value in ASP.NET Core Blazor application"
---

# Data Binding

This section briefly explains how to bind the value to the ComboBox component in the below different ways:

* One-way data binding
* Two-way data binding
* Dynamic value binding

## One-way binding

You can bind value to the ComboBox component directly for the `Value` property as mentioned in the following code example. In one-way binding, you have to pass the property or variable name along with `@` (For Ex: "@ComboVal").

```csharp
@using Syncfusion.Blazor.DropDowns

<SfComboBox Placeholder="e.g. Australia" Value="@ComboVal" DataSource="@Country">
    <ComboBoxFieldSettings Value="Name"></ComboBoxFieldSettings>
</SfComboBox>

<button @onclick="@UpdateValue">Update Value</button>

@code {

    public string ComboVal = "Austarila";
    public class Countries
    {
        public string Name { get; set; }

        public string Code { get; set; }
    }

    List<Countries> Country = new List<Countries>
    {
        new Countries() { Name = "Australia", Code = "AU" },
        new Countries() { Name = "Bermuda", Code = "BM" },
        new Countries() { Name = "Canada", Code = "CA" },
        new Countries() { Name = "Cameroon", Code = "CM" },
    };

    public void UpdateValue()
    {
        ComboVal = "Canada";
    }
}
```

## Two-way data binding

Two-way binding can be achieved by using the `bind-Value` attribute and its supports string, int, Enum, DateTime, and bool types. If component value has been changed, it will affect the all places where we bind the variable for the **bind-value** attribute.

```csharp
@using Syncfusion.Blazor.DropDowns

<p>ComboBox value is:<strong>@ComboVal</strong></p>

<SfComboBox Placeholder="e.g. Australia" @bind-Value="@ComboVal" DataSource="@Country">
    <ComboBoxFieldSettings Value="Name"></ComboBoxFieldSettings>
</SfComboBox>

@code {

    public string ComboVal = "Austarila";

    public class Countries
    {
        public string Name { get; set; }

        public string Code { get; set; }
    }

    List<Countries> Country = new List<Countries>
    {
        new Countries() { Name = "Australia", Code = "AU" },
        new Countries() { Name = "Bermuda", Code = "BM" },
        new Countries() { Name = "Canada", Code = "CA" },
        new Countries() { Name = "Cameroon", Code = "CM" },
    };
}
```

## Dynamic Value Binding

You can change the property value dynamically by manually calling the `StateHasChanged()` method inside public event of **Blazor ComboBox component** only. This method notifies the component that its state has changed and queues a re-render.

There is no need to call this method for native events since it is called after any lifecycle method has been called and can also be invoked manually to trigger a re-render. Refer to the following code example.

```csharp
@using Syncfusion.Blazor.DropDowns

<p>ComboBox value is:<strong>@ComboVal</strong></p>

<SfComboBox Placeholder="e.g. Australia" Value="@ComboVal" DataSource="@Country">
    <ComboBoxEvents TValue="string" ValueChange="onChange"></ComboBoxEvents>
    <ComboBoxFieldSettings Value="Name"></ComboBoxFieldSettings>
</SfComboBox>

@code {

    public string ComboVal = "Austarila";

    public class Countries
    {
        public string Name { get; set; }

        public string Code { get; set; }
    }

    List<Countries> Country = new List<Countries>
{
        new Countries() { Name = "Australia", Code = "AU" },
        new Countries() { Name = "Bermuda", Code = "BM" },
        new Countries() { Name = "Canada", Code = "CA" },
        new Countries() { Name = "Cameroon", Code = "CM" },
    };
    private void onChange(Syncfusion.Blazor.DropDowns.ChangeEventArgs<string> args)
    {
        ComboVal = args.Value;
        StateHasChanged();
    }
}
```
