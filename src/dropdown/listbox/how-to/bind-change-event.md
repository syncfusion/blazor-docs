---
title: "Binding Change Event in the listbox"
component: "ListBox"
description: "This section explains how to bind change event in listbox"
---

# Binding Change Event

To bind the change event in the listbox [`ValueChange`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.DropDowns.SfListBox%601~ValueChange.html) event is used and the event is triggered when the value in the listbox changes.

```csharp

@using Syncfusion.Blazor.DropDowns

<SfListBox TValue="string[]" TItem="VehicleData" DataSource="@Vehicles">
    <ListBoxEvents TValue="string[]" ValueChange="change"></ListBoxEvents>
    <ListBoxFieldSettings Text="Text" Value="Id" />
</SfListBox>

@code {
    public List<VehicleData> Vehicles = new List<VehicleData>
        {
        new VehicleData { Text = "Hennessey Venom", Id = "Vehicle-01" },
        new VehicleData { Text = "Bugatti Chiron", Id = "Vehicle-02" },
        new VehicleData { Text = "Bugatti Veyron Super Sport", Id = "Vehicle-03" },
        new VehicleData { Text = "SSC Ultimate Aero", Id = "Vehicle-04" },
        new VehicleData { Text = "Koenigsegg CCR", Id = "Vehicle-05" },
        new VehicleData { Text = "McLaren F1", Id = "Vehicle-06" },
        new VehicleData { Text = "Aston Martin One- 77", Id = "Vehicle-07" },
        new VehicleData { Text = "Jaguar XJ220", Id = "Vehicle-08" }
        };

    public class VehicleData {
        public string Text  { get; set; }
        public string Id  { get; set; }
    }

    private void change(ListBoxChangeEventArgs args)
    {
        //Triggers when value changed
    }
}

```

Output will be shown as

![ListBox](./../images/listbox.png)