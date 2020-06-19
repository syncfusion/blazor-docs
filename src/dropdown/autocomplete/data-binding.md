---
title: "Data-Binding"
component: "AutoComplete"
description: "This section helps to learn how to bind the value in ASP.NET Core Blazor application"
---

# Data Binding

This section briefly explains how to bind the value to the AutoComplete component in the following different ways:

* One-way data binding
* Two-way data binding
* Dynamic value binding

## One-way binding

You can bind the value to the AutoComplete component directly for `Value` property as mentioned in the following code example. In one-way binding, you have to pass the property or variable name along with `@` (For Ex: "@AutoVal").

```csharp
@using Syncfusion.Blazor.DropDowns

<SfAutoComplete TValue="string" Placeholder="e.g. Australia" TItem="Countries" Value="@AutoVal" DataSource="@Country">
    <AutoCompleteFieldSettings Value="Name"></AutoCompleteFieldSettings>
</SfAutoComplete>

<button @onclick="@UpdateValue">Update Value</button>

@code {

    public string AutoVal;
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
        AutoVal = "Canada";
    }
}
```

## Two-way data binding

Two-way binding can be achieved by using the `bind-Value` attribute and it supports string, int, Enum, DateTime, and bool types. If component value has been changed, it will affect all places where you bind the variable for the **bind-value** attribute.

```csharp
@using Syncfusion.Blazor.DropDowns

<p>AutoComplete value is: @AutoVal</p>

<SfAutoComplete TValue="string" TItem="Countries" Placeholder="e.g. Australia" @bind-Value="@AutoVal" DataSource="@Country">
    <AutoCompleteFieldSettings Value="Name"></AutoCompleteFieldSettings>
</SfAutoComplete>

@code {

    public string AutoVal;

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

## Dynamic value binding

You can change the property value dynamically by manually calling the `StateHasChanged()` method inside the public event of **Blazor AutoComplete component** only. This method notifies the component that its state has changed and queues a re-render.

There is no need to call this method for native events since it’s called after any lifecycle method has been called and can also be invoked manually to trigger a re-render. Refer to the following code example.

```csharp
@using Syncfusion.Blazor.DropDowns

<p>AutoComplete value is:<strong>@AutoVal</strong></p>

<SfAutoComplete TValue="string" TItem="Countries" Placeholder="e.g. Australia" Value="@AutoVal" DataSource="@Country">
    <AutoCompleteEvents TValue="string" ValueChange="onChange"></AutoCompleteEvents>
    <AutoCompleteFieldSettings Value="Name"></AutoCompleteFieldSettings>
</SfAutoComplete>

@code {

    public string AutoVal = "Austarila";

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
        AutoVal = args.Value;
        StateHasChanged();
    }
}
```
