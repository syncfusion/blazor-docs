---
title: "ListBox toolbar support"
component: "ListBox"
description: "ListBox supports dual list (i.e) reordering of items within the listbox and between two listboxes."
---

# Dual ListBox

The dual ListBox allows the user to move items between two listbox by clicking the toolbar buttons. Dual ListBox can be created by listing items in the
[`ToolbarSettings`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.DropDowns.SfListBox~ToolbarSettings.html) along with the [`Scope`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.DropDowns.SfListBox%601~Scope.html) property.

The following operations can be performed in dual ListBox,

| Options | Description |
|------|-------------|
| moveUp | Move the selected item in the upward direction within the listbox. |
| moveDown | Move the selected item in the downward direction within the listbox. |
| moveTo |  Move the selected item to the another listbox. |
| moveFrom | Move the selected item from one listbox to the another listbox. |
| moveAllTo | Move all the items to the another listbox. |
| moveAllFrom |  Move all the items from one listbox to the another listbox. |

The following example illustrates how to move items from `Group A` to `Group B` listbox.

```csharp
@using Syncfusion.Blazor.DropDowns

<div id="listbox1">
    <h4>Group A</h4>
<SfListBox TValue="string[]" DataSource="@GroupA" Scope="#listbox" TItem="CountryCode">
<ListBoxFieldSettings Text="Name"></ListBoxFieldSettings>
<ListBoxToolbarSettings Items="@Items"></ListBoxToolbarSettings>
</SfListBox>
</div>
<div id="listbox2">
    <h4>Group B</h4>
<SfListBox TValue="string[]" ID="listbox" DataSource="@GroupB" TItem="CountryCode">
<ListBoxFieldSettings Text="Name"></ListBoxFieldSettings>
</SfListBox>
</div>

@code {
    public string[] Items = new string[] { "moveUp", "moveDown", "moveTo", "moveFrom", "moveAllTo", "moveAllFrom" };
    public List<CountryCode> GroupA = new List<CountryCode>
      {
        new CountryCode{ Name = "Australia", Code = "AU" },
        new CountryCode{ Name = "Bermuda", Code = "BM" },
        new CountryCode{ Name = "Canada", Code = "CA" },
        new CountryCode{ Name = "Cameroon", Code = "CM" },
        new CountryCode{ Name = "Denmark", Code = "DK" },
        new CountryCode{ Name = "France", Code = "FR" },
        new CountryCode{ Name = "Finland", Code = "FI" }
    };

    public List<CountryCode> GroupB = new List<CountryCode>
      {
        new CountryCode{ Name = "India", Code = "IN" },
        new CountryCode{ Name = "Italy", Code = "IT" },
        new CountryCode{ Name = "Japan", Code = "JP" },
        new CountryCode{ Name = "Mexico", Code = "MX" },
        new CountryCode{ Name = "Norway", Code = "NO" },
        new CountryCode{ Name = "Poland", Code = "PL" },
        new CountryCode{ Name = "Switzerland", Code = "CH" }
    };

    public class CountryCode {
        public string Name  { get; set; }
        public string Code  { get; set; }
    }
    }

<style>
    #listbox1 {
        width: 48%;
        float: left;
    }

    #listbox2 {
        width: 48%;
        float: right;
    }
</style>

```

Output will be shown as

![ListBox](./images/duallistbox.png)