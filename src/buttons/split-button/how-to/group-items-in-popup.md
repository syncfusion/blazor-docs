---
title: "Group items in Popup"
component: "Split Button"
description: "This section explains how to group popup items using list view component in Blazor."
---

# Group items in Popup

Items in popup can be grouped in Split Button by templating entire popup with ListView. To achieve grouping in ListView,
check [`ListView Grouping`](../../listview/grouping#grouping) documentation. To template ListView in popup, create
ListView with ID `listview` and provide it as [`Target`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.SplitButtons.SfSplitButton~Target.html) for Split Button.

The following example illustrates how to group items in popup using ListView component.

```csharp

@using Syncfusion.Blazor.SplitButtons
@using Syncfusion.Blazor.Lists

<SfSplitButton Target="#listview" Content="ClipBoard" ></SfSplitButton>
<SfListView ID="listview" DataSource="@Data" SortOrder="SortOrder.Descending">
    <ListViewFieldSettings Text="Text" GroupBy="Category"></ListViewFieldSettings>
</SfListView>

@code {
    public List<ListData> Data = new List<ListData>{
        new ListData{ Text = "Cut", Category = "Basic" },
        new ListData{ Text = "Copy", Category = "Basic" },
        new ListData{ Text = "Paste", Category = "Basic" },
        new ListData{ Text = "Paste as Formula", Category = "Advanced" },
        new ListData{ Text = "Paste as Hyperlink", Category = "Advanced" }
    };

    public class ListData
    {
        public string Text { get; set; }
        public string Category { get; set; }
    }
}

```

Output be like

![Split Button Sample](./../images/sb-listview.png)