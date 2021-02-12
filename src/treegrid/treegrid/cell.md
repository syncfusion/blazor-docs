---
component: "Tree Grid"
---

# Cell

## Displaying the HTML content

The HTML tags can be displayed in the Tree Grid header and content by enabling the [`DisableHtmlEncode`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.TreeGridColumn~DisableHtmlEncode.html) property.

{% aspTab template="tree-grid/cell/disphtml", sourceFiles="index.razor,treegriddata.cs" %}

{% endaspTab %}

The following output is displayed as a result of the above code example.

![Display HTML Content](images/disphtml.png)

## Customize cell styles

The appearance of cells can be customized by using the [`QueryCellInfo`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.SfTreeGrid~QueryCellInfo.html) event.
The [`QueryCellInfo`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.SfTreeGrid~QueryCellInfo.html) event triggers for every cell. In that event handler, you can get **QueryCellInfoEventArgs** that contains the details of the cell.

{% aspTab template="tree-grid/cell/cellstyling", sourceFiles="index.razor,treegriddata.cs" %}

{% endaspTab %}

The following output is displayed as a result of the above code example.

![Customize cell styles](images/cell-styling.png)

## Auto wrap

The auto wrap allows the cell content of the tree grid to wrap to the next line when it exceeds the boundary of the cell width. The Cell Content wrapping works based on the position of white space between words.
To enable auto wrap, set the [`AllowTextWrap`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.SfTreeGrid%601~AllowTextWrap.html) property to **true**.
<!-- You can configure the auto wrap mode by setting the [`textWrapSettings.wrapMode`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.SfTreeGrid%601~TextWrapSettings.html) property.

There are three types of `wrapMode`. They are:

* **`Both`**: `Both` value is set by default. Auto wrap will be enabled for both the content and the header.
* **`Header`**: Auto wrap will be enabled only for the header.
* **`Content`**: Auto wrap will be enabled only for the content.

In the following example, the `textWrapSettings.wrapMode` is set to `Content`.
-->
Note: When a column width is not specified, then auto wrap of columns will be adjusted with respect to the tree grid's width.

{% aspTab template="tree-grid/cell/autowrap", sourceFiles="index.razor,treegriddata.cs" %}

{% endaspTab %}

The following output is displayed as a result of the above code example.

![Auto Wrap](images/autowrap.png)

<!--
 Custom Attributes

You can customize the tree grid cells by adding a CSS class to the [`customAttribute`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.TreeGridColumn~CustomAttributes.html) property of the column.

```CSS
.e-attr {
    background: '#d7f0f4';
}
```

In the below example, we have customized the cells of `TaskID` and `StartDate` columns.

````csharp

@using TreeGridComponent.Data
@using Syncfusion.Blazor.Grids;
@using Syncfusion.Blazor.Data;

<SfTreeGrid ChildMapping="Children" TreeColumnIndex="1" AllowTextWrap="true">
    <SfDataManager Json="@TreeGridData" Adaptor="Syncfusion.Blazor.Adaptors.JsonAdaptor" ></SfDataManager>
    <TreeGridColumns>
        <TreeGridColumn Field="TaskId" HeaderText="Task ID" Width="80" TextAlign="Syncfusion.Blazor.Grids.TextAlign.Right"></TreeGridColumn>
        <TreeGridColumn Field="TaskName" HeaderText="Task Name" CustomAttributes="@attribute" Width="100"></TreeGridColumn>
        <TreeGridColumn Field="StartDate" HeaderText="Start Date" Format="yMd" type="date" Width="100" TextAlign="Syncfusion.Blazor.Grids.TextAlign.Right"></TreeGridColumn>
        <TreeGridColumn Field="Duration" HeaderText="Duration" Width="100" TextAlign="Syncfusion.Blazor.Grids.TextAlign.Right"></TreeGridColumn>
        <TreeGridColumn Field="Progress" HeaderText="Progress" Width="100" TextAlign="Syncfusion.Blazor.Grids.TextAlign.Right"></TreeGridColumn>
        <TreeGridColumn Field="Priority" HeaderText="Priority" Width="100"></TreeGridColumn>
    </TreeGridColumns>
</SfTreeGrid>

@code{
    public object[] TreeGridData { get; set; }
    public object attribute { get; set; }
    protected override void OnInitialized()
    {
        this.attribute = new { @class = "customcss" };
        this.TreeGridData = TreeData.GetDefaultData().ToList().Cast<object>().ToArray();
    }
}

<style>
    .e-attr {
        background: #d7f0f4;
    }
</style>

```
-->

## Grid lines

The [`GridLines`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.SfTreeGrid~GridLines.html) have option to display cell border and it can be defined by the
[`GridLines`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.SfTreeGrid~GridLines.html) property.

The available modes of grid lines are:

| Modes | Actions |
|-------|---------|
| Both | Displays both the horizontal and vertical grid lines.|
| None | No grid lines are displayed.|
| Horizontal | Displays the horizontal grid lines only.|
| Vertical | Displays the vertical grid lines only.|
| Default | Displays grid lines based on the theme.|

{% aspTab template="tree-grid/cell/gridlines", sourceFiles="index.razor,treegriddata.cs" %}

{% endaspTab %}

The following output is displayed as a result of the above code example.

![Grid Lines](images/gridlines.png)

>By default, the tree grid renders with **Default** mode.

## Clip Mode

The clip mode provides options to display its overflow cell content and it can be defined by the [`ClipMode`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.TreeGridColumn~ClipMode.html) property.

There are three types of [`ClipMode`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.TreeGridColumn~ClipMode.html). They are:

* **Clip**: Truncates the cell content when it overflows its area.
* **Ellipsis**: Displays ellipsis when the cell content overflows its area.
* **EllipsisWithTooltip**: Displays ellipsis when the cell content overflows its area, also it will display the tooltip while hover on ellipsis is applied.

{% aspTab template="tree-grid/cell/clipmode", sourceFiles="index.razor,treegriddata.cs" %}

{% endaspTab %}

The following output is displayed as a result of the above code example.

![Clip Mode](images/clipmode.png)

> By default, [`ClipMode`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.TreeGridColumn~ClipMode.html) value is **Ellipsis**.
