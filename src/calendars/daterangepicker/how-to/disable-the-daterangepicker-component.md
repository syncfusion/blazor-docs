# Disable the component

DateRangePicker can be inactivated on a page. By setting [Enabled](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Calendars.SfDateRangePicker.html#Syncfusion_Blazor_Calendars_SfDateRangePicker_Enabled) value to false will disable the component completely from all the user interactions including in the form post. The following code demonstrates the disabled component.

```csharp
@using Syncfusion.Blazor.Calendars

<SfDateRangePicker TValue="DateTime?" Enabled=false StartDate="@Start" EndDate="@End"></SfDateRangePicker>

@code {
    public DateTime? Start { get; set; } = new DateTime(DateTime.Now.Year, DateTime.Now.Month, 20);
    public DateTime? End { get; set; } = new DateTime(DateTime.Now.Year, DateTime.Now.Month + 1, 25);
}
```

The output will be as follows.

![DateRangePicker](../images/disabled.png)