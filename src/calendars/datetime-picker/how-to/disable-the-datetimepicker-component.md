---
title: "Disabled State"
component: "DateTimePicker"
description: "Explains how to disable the user interaction on date time picker component."
---

# Disable the component

To disable the DateTimePicker, set its
[Enabled](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/Syncfusion~Syncfusion.Calendars.DateTimePicker~Enabled.html)
property to `false`.

The following code demonstrates the disabled component.

```csharp
@using Syncfusion.Blazor.Calendars

<SfDateTimePicker TValue="DateTime?" Enabled=false Value='@DateTimeValue'></SfDateTimePicker>

@code {
    public DateTime? DateTimeValue { get; set; } = DateTime.Now;
}
```

The output will be as follows.

![DateTimePicker](../images/disabled.png)
