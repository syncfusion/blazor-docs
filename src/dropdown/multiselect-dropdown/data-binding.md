---
title: "Data-Binding"
component: "MultiSelect"
description: "This section helps to learn how to bind the value in ASP.NET Core Blazor application"
---

# Data Binding

This section briefly explains how to bind the value to the MultiSelect component in the following different ways:

* One-way data binding
* Two-way data binding
* Dynamic value binding

## One-way binding

You can bind the value to the MultiSelect component directly for the `Value` property as mentioned in the following code example. In one-way binding, you have to pass property or variable name along with `@` (For Ex: "@MultiVal").

```csharp
@using Syncfusion.Blazor.DropDowns

<SfMultiSelect Placeholder="e.g. Australia" Value="@MultiVal" DataSource="@Country">
    <MultiSelectFieldSettings Value="Name"></MultiSelectFieldSettings>
</SfMultiSelect>

<button @onclick="@UpdateValue">Clear Value</button>

@code {

    public string MultiVal;
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
        MultiVal = "";
    }
}
```

## Two-way data binding

Two-way binding can be achieved by using the `bind-Value` attribute and its supports string, int, Enum, DateTime, bool types. If component value has been changed, it will affect the all places where we bind the variable for the **bind-value** attribute.

```csharp
@using Syncfusion.Blazor.DropDowns

@foreach (var SelectedValue in MultiVal)
{
    <p>MultiSelect value is:<strong>@SelectedValue</strong></p>
}

<SfMultiSelect Placeholder="e.g. Australia" @bind-Value="@MultiVal" DataSource="@Country">
    <MultiSelectFieldSettings Value="Name"></MultiSelectFieldSettings>
</SfMultiSelect>

@code {

   public string[] MultiVal { get; set; } = new string[] { };

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

You can change the property value dynamically by manually calling the `StateHasChanged()` method inside public event of **Blazor MultiSelect component** only. This method notifies the component that its state has changed and queues a re-render.

There is no need to call this method for native events since it’s called after any lifecycle method has been called and can also be invoked manually to trigger a re-render. Refer to the following code example.

```csharp
@using Syncfusion.Blazor.DropDowns

@foreach (var SelectedValue in MultiVal)
{
    <p>MultiSelect value is:<strong>@SelectedValue</strong></p>
}

<SfMultiSelect Placeholder="e.g. Australia" Value="@MultiVal" DataSource="@Country">
    <MultiSelectEvents TValue="string[]" ValueChange="onChange"></MultiSelectEvents>
    <MultiSelectFieldSettings Value="Name"></MultiSelectFieldSettings>
</SfMultiSelect>

@code {

public string[] MultiVal { get; set; } = new string[] { };

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
private void onChange(MultiSelectChangeEventArgs<string[]> args)
{
    MultiVal = args.Value;
    StateHasChanged();

}
}

```
