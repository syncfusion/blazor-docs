---
component: "ListView"
---

# UI Virtualization

UI virtualization loads only viewable list items in a view port, which will improve the ListView performance while loading a large number of data.

## Getting started

UI virtualization can be enabled in the ListView by setting the `EnableVirtualization` property to true.

It has two types of scrollers as follows:

**Window scroll**: This scroller is used in the ListView by default.

**Container scroll**: This scroller is used, when the height property of the ListView is set.

```csharp
@using Syncfusion.Blazor.Lists
<SfListView DataSource="@ListData" EnableVirtualization="true">
    <ListViewFieldSettings TValue="DataModel" Id="Id" Text="Text"></ListViewFieldSettings>
</SfListView>

@code{
    List<DataModel> ListData = new List<DataModel>();

    protected override void OnInitialized()
    {
        base.OnInitialized();

        ListData.Add(new DataModel
        {
            Text = "Nancy",
            Id = "0"
        });
        ListData.Add(new DataModel
        {
            Text = "Andrew",
            Id = "1"
        });
        ListData.Add(new DataModel
        {
            Text = "Janet",
            Id = "2"
        });
        ListData.Add(new DataModel
        {
            Text = "Margaret",
            Id = "3"
        });
        ListData.Add(new DataModel
        {
            Text = "Steven",
            Id = "4"
        });
        ListData.Add(new DataModel
        {
            Text = "Laura",
            Id = "5"
        });
        ListData.Add(new DataModel
        {
            Text = "Robert",
            Id = "6"
        });
        ListData.Add(new DataModel
        {
            Text = "Michael",
            Id = "7"
        });
        ListData.Add(new DataModel
        {
            Text = "Albert",
            Id = "8"
        });
        ListData.Add(new DataModel
        {
            Text = "Nolan",
            Id = "9"
        });

        for (int i = 10; i < 1000; i++)
        {
            int index = new Random().Next(0, 10);
            ListData.Add(new DataModel
            {
                Text = ListData[index].GetType().GetProperty("Text").GetValue(ListData[index], null).ToString(),
                Id = i.ToString()
            });
        }

    }

    class DataModel
    {
        public string Id { get; set; }
        public string Text { get; set; }
    }
}
```

![ListView - Virtualization](./images/list/list-virtual.png)
