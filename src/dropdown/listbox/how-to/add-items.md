---
title: "Adding items to the listbox"
component: "ListBox"
description: "ListBox component supports adding of items to the listbox."
---

# Add items to the listbox

To add an item or multiple items, [`AddItems`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.DropDowns.SfListBox%601~AddItems.html) method can be used. In the following example, the `Ferrari LaFerrari` and `McLaren P1` items will be added while clicking `Add Items` button.

```csharp
@using Syncfusion.Blazor.DropDowns
@using Syncfusion.Blazor.Buttons

<SfListBox TValue="string[]" TItem="VehicleData" DataSource="@Vehicles" @ref="ListBoxObj">
  <ListBoxFieldSettings Text="Text" Value="Id" />
</SfListBox>
<SfButton @onclick="addData">ADD ITEMS</SfButton>

@code {
      SfListBox<string[]> ListBoxObj;
      public List<VehicleData> Vehicles = new List<VehicleData> {
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

      public List<VehicleData> Item = new List<VehicleData>{
        new VehicleData{ Text = "Ferrari LaFerrari", Id = "Vehicle-09"},
        new VehicleData{ Text = "McLaren P1", Id = "Vehicle-10"}
      };

      private void addData() {
        ListBoxObj.AddItems(Item);
      }
}
```

Output will be shown as

![ListBox](./../images/additems.png)

# Remove items from the listbox

To remove an item or multiple items, [`RemoveItems`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.DropDowns.SfListBox%601~RemoveItems.html) method can be used. In the following example, the `Ferrari LaFerrari` and `McLaren P1` items will be removed while clicking `Remove Items` button.

```csharp
@using Syncfusion.Blazor.DropDowns
@using Syncfusion.Blazor.Buttons

<SfListBox TValue="string[]" DataSource="@Vehicles" @ref="ListBoxObj">
  <ListBoxFieldSettings Text="Text" Value="Id" />
</SfListBox>
<SfButton @onclick="removeData">REMOVE ITEMS</SfButton>

@code {
      SfListBox<string[]> ListBoxObj;
      public List<VehicleData> Vehicles = new List<VehicleData> {
        new VehicleData { Text = "Hennessey Venom", Id = "Vehicle-01" },
        new VehicleData { Text = "Bugatti Chiron", Id = "Vehicle-02" },
        new VehicleData { Text = "Bugatti Veyron Super Sport", Id = "Vehicle-03" },
        new VehicleData { Text = "SSC Ultimate Aero", Id = "Vehicle-04" },
        new VehicleData { Text = "Koenigsegg CCR", Id = "Vehicle-05" },
        new VehicleData { Text = "McLaren F1", Id = "Vehicle-06" },
        new VehicleData { Text = "Aston Martin One- 77", Id = "Vehicle-07" },
        new VehicleData { Text = "Jaguar XJ220", Id = "Vehicle-08" },
        new VehicleData{ Text = "Ferrari LaFerrari", Id = "Vehicle-09"},
        new VehicleData{ Text = "McLaren P1", Id = "Vehicle-10"}
    };

    public class VehicleData {
      public string Text  { get; set; }
      public string Id  { get; set; }
    }

    public List<VehicleData> Item = new List<VehicleData>{
        new VehicleData{ Text = "Ferrari LaFerrari", Id = "Vehicle-09"},
        new VehicleData{ Text = "McLaren P1", Id = "Vehicle-10"}
    };

    private void removeData() {
      ListBoxObj.RemoveItems(Item);
    }
}
```

Output will be shown as

![ListBox](./../images/remitems.png)