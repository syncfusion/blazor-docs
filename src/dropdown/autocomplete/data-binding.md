# Data Binding

Data binding can be achieved by using the `bind-Value` attribute and it supports string, int, Enum, DateTime, and bool types. If component value has been changed, it will affect all places where you bind the variable for the **bind-value** attribute.

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
