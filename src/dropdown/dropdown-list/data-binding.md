---
title: "Data-Binding"
component: "DropDownList"
description: "This section helps to learn how to bind the value in ASP.NET Core Blazor application"
---

# Data Binding

This section briefly explains how to bind the value to the DropDownList component in the following ways:

* One-way data binding
* Two-Way data binding
* Dynamic value binding

## One-way binding

You can bind the value to the DropDownList component directly for `Value` property as mentioned in the following code example. In one-way binding, you have to pass the property or variable name along with `@` (For Ex: "@DropVal").

```csharp
@using Syncfusion.Blazor.DropDowns

<SfDropDownList TValue="string" Placeholder="e.g. Australia" TItem="Countries" Value="@DropVal" DataSource="@Country">
    <DropDownListFieldSettings Value="Name"></DropDownListFieldSettings>
</SfDropDownList>

<button @onclick="@UpdateValue">Update Value</button>

@code {

    public string DropVal;
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
        DropVal = "Canada";
    }
}
```

## Two-way data binding

Two-way binding can be achieved by using the `bind-Value` attribute and it supports string, int, Enum, DateTime, and bool types. If component value has been changed, it will affect the all places where you bind the variable for the **bind-value** attribute.

```csharp
@using Syncfusion.Blazor.DropDowns

<p>DropDownList value is:<strong>@DropVal</strong></p>

<SfDropDownList TValue="string" Placeholder="e.g. Australia" TItem="Countries" @bind-Value="@DropVal" DataSource="@Country">
    <DropDownListFieldSettings Value="Name"></DropDownListFieldSettings>
</SfDropDownList>

@code {

    public string DropVal;

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

You can change the property value dynamically by manually calling the `StateHasChanged()` method inside public event of **Blazor DropDownList component** only. This method notifies the component that its state has changed and queues a re-render.

There is no need to call this method for native events since it is called after any lifecycle method has been called and can also be invoked manually to trigger a re-render. Refer to the following code example.

```csharp
@using Syncfusion.Blazor.DropDowns

<p>DropDownList value is:<strong>@DropVal</strong></p>

<SfDropDownList TValue="string" Placeholder="e.g. Australia" TItem="Countries" Value="@DropVal" DataSource="@Country">
    <DropDownListEvents TValue="string" ValueChange="onChange"></DropDownListEvents>
    <DropDownListFieldSettings Value="Name"></DropDownListFieldSettings>
</SfDropDownList>

@code {

    public string DropVal;

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
        DropVal = args.Value;
        StateHasChanged();
    }
}
```
