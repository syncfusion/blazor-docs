---
title: "Columns"
component: "Tree Grid"
description: "Documentation on column reordering, resizing, header templates (custom header content), and column templates (custom cell content) in the Blazor Tree Grid."
---

# Columns

The column definitions are used as the datasource schema in the Tree Grid. This plays a vital role in rendering column values in the required format.
The tree grid operations such as sorting, filtering and searching etc. are performed based on column definitions. The [`Field`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.TreeGridColumn~Field.html) property of [`TreeGridColumns`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.TreeGridColumns.html) tag helper
is necessary to map the data source values in Tree Grid columns.

> 1. If the column [`Field`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.TreeGridColumn~Field.html) is not specified in the dataSource, the column values will be empty.

[`TreeColumnIndex`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.SfTreeGrid~TreeColumnIndex.html) property denotes the column that is used to expand and collapse child rows.

## Header template

You can customize the header element by using the [`HeaderTemplate`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.TreeGridColumn~HeaderTemplate.html) property.

{% aspTab template="tree-grid/column/headertemplate", sourceFiles="index.razor,treegriddata.cs" %}

{% endaspTab %}

The following output is displayed as a result of the above code example.

![Header Template](images/headertemp.png)

> For Templated Tree Grid component, [ModelType](./templates/#template-modeltype) property of Tree Grid should be defined.

## Header text

By default, column header title is displayed from column [`Field`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.TreeGridColumn~Field.html) value. To override the default header title, you have to define the [`HeaderText`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.TreeGridColumn~HeaderText.html) value.

{% aspTab template="tree-grid/column/headertext", sourceFiles="index.razor,treegriddata.cs" %}

{% endaspTab %}

The following output is displayed as a result of the above code example.

![Header Text](images/headertext.png)

> If both the [`Field`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.TreeGridColumn~Field.html) and [`HeaderText`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.TreeGridColumn~HeaderText.html)
are not defined in the column, the column renders with **empty** header text.

## Format

To format cell values based on specific culture, use the [`Format`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.TreeGridColumn~Format.html) property of [`TreeGridColumns`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.TreeGridColumns.html) tag helper. The Tree Grid uses **Internalization** library to format the number values.

{% aspTab template="tree-grid/column/format", sourceFiles="index.razor,treegriddata.cs" %}

{% endaspTab %}

> By default, the number and date values are formatted in **en-US** locale.

### Number formatting

The number or integer values can be formatted using the below format strings.

Format |Description |Remarks
-----|-----|-----
N | Denotes numeric type. | The numeric format is followed by integer value as N2, N3. etc which denotes the number of precision to be allowed.
C | Denotes currency type. | The currency format is followed by integer value as C2, C3. etc which denotes the number of precision to be allowed.
P | Denotes percentage type | The percentage format expects the input value to be in the range of 0 to 100. For example the cell value *0.2* is formatted as *20%*. The percentage format is followed by integer value as P2, P3. etc which denotes the number of precision to be allowed.

<!-- Please refer to the link to know more about [`Number formatting`](../../common/internationalization/#number-formatting). -->

### Date formatting

You can format date values using built-in date format string.

For built-in date format you can specify [`Format`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.TreeGridColumn~Format.html) property as string   (Example: *d*).
<!-- Please refer to the link to know more about [`Date formatting`](../../common/internationalization/#manipulating-datetime). -->

{% aspTab template="tree-grid/column/dateformat", sourceFiles="index.razor,treegriddata.cs" %}

{% endaspTab %}

The following output is displayed as a result of the above code example.

![Date Format](images/dateformat.png)

## AutoFit specific columns

The **AutoFitColumns** method resizes the column to fit the widest cell's content without wrapping. You can autofit a specific column at initial rendering by invoking the [`AutoFitColumns`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.SfTreeGrid~AutoFitColumns.html) method in [`DataBound`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.SfTreeGrid~DataBound.html) event.

{% aspTab template="tree-grid/column/autofitcolumns", sourceFiles="index.razor,treegriddata.cs" %}

{% endaspTab %}

The following output is displayed as a result of the above code example.

![AutoFit Columns](images/autofitcolumn.png)

> You can autofit all the columns by invoking the **AutoFitColumns** method without column names.

## Reorder

Reordering can be done by drag and drop of a particular column header from one index to another index within the treegrid. To enable reordering, set the [`AllowReordering`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.SfTreeGrid~AllowReordering.html) to true.

{% aspTab template="tree-grid/column/reorder", sourceFiles="index.razor,treegriddata.cs" %}

{% endaspTab %}

> You can disable reordering a particular column by setting the [`AllowReordering`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.SfTreeGrid~AllowReordering.html) property of [`TreeGridColumns`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.TreeGridColumns.html) tag helper to false.

### Reorder multiple columns

Multiple columns can be reordered at a time by using the **ReorderColumns** method.

{% aspTab template="tree-grid/column/reordermul", sourceFiles="index.razor,treegriddata.cs" %}

{% endaspTab %}

### Lock columns

You can lock columns by using [`LockColumn`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.TreeGridColumn~LockColumn.html) property. The locked columns will be moved to the first position. Also you can’t reorder its position.

In the below example, Duration column is locked and its reordering functionality is disabled.

{% aspTab template="tree-grid/column/lockcolumn", sourceFiles="index.razor,treegriddata.cs" %}

{% endaspTab %}

The following output is displayed as a result of the above code example.

![Lock Columns](images/lockcolumn.png)

## Column resizing

Column width can be resized by clicking and dragging the right edge of the column header. While dragging, the width of the respective column will be resized immediately. Each column can be auto resized by double-clicking the right edge of the column header to fit the width of that column based on the widest cell content. To enable column resize, set the [`AllowResizing`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.SfTreeGrid~AllowResizing.html) property to true.

{% aspTab template="tree-grid/column/colresize", sourceFiles="index.razor,treegriddata.cs" %}

{% endaspTab %}

> * You can disable resizing for a particular column by setting the [`AllowResizing`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.TreeGridColumn~AllowResizing.html) property of [`TreeGridColumns`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.TreeGridColumns.html) tag helper to false.
> * In RTL mode, you can click and drag the left edge of the header cell to resize the column.

### Min and max width

Column resize can be restricted between minimum and maximum width by defining the [`MinWidth`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.TreeGridColumn~MinWidth.html) and [`MaxWidth`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.TreeGridColumn~MaxWidth.html) properties of [`TreeGridColumns`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.TreeGridColumns.html) tag helper.

In the following sample, minimum and maximum width are defined for **Duration**, and **Task Name** columns.

{% aspTab template="tree-grid/column/minmax", sourceFiles="index.razor,treegriddata.cs" %}

{% endaspTab %}

### Resize stacked column

Stacked columns can be resized by clicking and dragging the right edge of the stacked column header. While dragging, the width of the respective child columns will be resized at the same time. You can disable resize for particular stacked column by setting [`AllowResizing`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.TreeGridColumn~AllowResizing.html) as **false** to its columns.

{% aspTab template="tree-grid/column/resizecol", sourceFiles="index.razor,treegriddata.cs" %}

{% endaspTab %}

### Touch interaction

When the right edge of the header cell is tapped, a floating handler will be visible over the right border of the column. To resize the column, tap and drag the floating handler as needed.

The following screenshot represents the column resizing in touch device.

<!-- markdownlint-disable MD033 -->
<img src="../images/column-resizing.png" alt="Touch interaction" style="width:320px;height: 620px">
<!-- markdownlint-enable MD033 -->

## Column template

The column [`Template`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/Syncfusion.EJ2~Syncfusion.EJ2.TreeGrid.TreeGridColumn~Template.html) has options to display custom element instead of a field value in the column.

{% aspTab template="tree-grid/column/columntemp", sourceFiles="index.razor,treegriddata.cs" %}

{% endaspTab %}

The following output is displayed as a result of the above code example.

![Column Template](images/columntemp.png)

> * Tree Grid actions such as editing, filtering and sorting etc. will depend upon the column [`Field`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/Syncfusion.EJ2~Syncfusion.EJ2.TreeGrid.TreeGridColumn~Field.html). If the [`Field`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/Syncfusion.EJ2~Syncfusion.EJ2.TreeGrid.TreeGridColumn~Field.html) is not specified in the
template column, the tree grid actions cannot be performed.
> * For Templated Tree Grid component, [ModelType](./templates/#template-modeltype) property of Tree Grid should be defined.

### Using condition template

You can render the template elements based on condition.

In the following code, checkbox is rendered based on **Duration** field value.

{% aspTab template="tree-grid/column/concoltemp", sourceFiles="index.razor,treegriddata.cs" %}

{% endaspTab %}

> For Templated Tree Grid component, [ModelType](./templates/#template-modeltype) property of Tree Grid should be defined.

## Column type

Column type can be specified using the [`Type`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.TreeGridColumn~Type.html) property of [`TreeGridColumn`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.TreeGridColumn.html) tag helper. It specifies the type of data the column binds.

If the [`Format`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.TreeGridColumn~Format.html)  is defined for a column, the column uses [`Type`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.TreeGridColumn~Type.html) to select the appropriate format option (**number** or **date**).

Tree Grid column supports the following types:
* string
* number
* boolean
* date
* datetime

> If the [`Type`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.TreeGridColumn~Type.html) is not defined, it will be determined from the first record of the [`DataSource`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/Syncfusion.EJ2~Syncfusion.EJ2.TreeGrid.TreeGridBuilder~DataSource.html).

## Column Chooser

The column chooser has options to show or hide columns dynamically. It can be enabled by defining the [`ShowColumnChooser`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.SfTreeGrid~ShowColumnChooser.html) as true.

{% aspTab template="tree-grid/column/columnchooser", sourceFiles="index.razor,treegriddata.cs" %}

{% endaspTab %}

The following output is displayed as a result of the above code example.

![Column Chooser](images/columnchooser.png)

> You can hide the column names in column chooser by defining the [`ShowInColumnChooser`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.SfTreeGrid~ShowInColumnChooser.html) property as false.

### Open column chooser by external button

The column chooser has options to show or hide columns dynamically. It can be enabled by defining the [`ShowInColumnChooser`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.SfTreeGrid~ShowInColumnChooser.html) as true.

In this below example, we have opened column chooser using external button click.

{% aspTab template="tree-grid/column/opencolumnchooser", sourceFiles="index.razor,treegriddata.cs" %}

{% endaspTab %}

The following output is displayed as a result of the above code example.

![Open Column Chooser](images/opencolumnchooser.png)

> You can hide the column names in column chooser by defining the [`ShowInColumnChooser`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.SfTreeGrid~ShowInColumnChooser.html) property as false.

## Column menu

The column menu has options to integrate features like sorting, filtering, and autofit. It will show a menu with the integrated feature when users click on multiple icon of the column. To enable column menu, you need to define the [`ShowColumnMenu`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.SfTreeGrid~ShowColumnMenu.html) property as true.

The default items are displayed in following table.

| Item | Description |
|-----|-----|
| **SortAscending** | Sort the current column in ascending order. |
| **SortDescending** | Sort the current column in descending order. |
| **AutoFit** | Auto fit the current column. |
| **AutoFitAll** | Auto fit all columns. |
| **Filter** | Show the filter option as given in **FilterSettings.Type** |

{% aspTab template="tree-grid/column/columnmenu", sourceFiles="index.razor,treegriddata.cs" %}

{% endaspTab %}

The following output is displayed as a result of the above code example.

![Column Menu](images/columnmenu.png)

> You can disable column menu for a particular column by defining the [`ShowColumnMenu`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.SfTreeGrid~ShowColumnMenu.html) property of [`TreeGridColumn`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.TreeGridColumn.html) tag helper as false.

## Checkbox column

To render checkboxes in existing column, you need to set [`ShowCheckbox`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.TreeGridColumn~ShowCheckbox.html) property of [`TreeGridColumn`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.TreeGridColumn.html) as **true**.

It is also possible to select the rows hierarchically using checkboxes in Tree Grid by enabling [`AutoCheckHierarchy`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.SfTreeGrid~AutoCheckHierarchy.html) property. When we check on any parent record checkbox then the child record checkboxes will get checked.

{% aspTab template="tree-grid/column/checkboxcolumn", sourceFiles="index.razor,treegriddata.cs" %}

{% endaspTab %}

The following output is displayed as a result of the above code example.

![Checkbox Column](images/checkboxcolumn.png)

## Responsive columns

You can toggle column visibility based on media queries which are defined
at the [`HideAtMedia`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.TreeGridColumn~HideAtMedia.html).
The [`HideAtMedia`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.TreeGridColumn~HideAtMedia.html) accepts valid
[Media Queries]( http://cssmediaqueries.com/what-are-css-media-queries.html).

{% aspTab template="tree-grid/column/responsivecolumn", sourceFiles="index.razor,treegriddata.cs" %}

{% endaspTab %}

The following output is displayed as a result of the above code example.

![Responsive Columns](images/responscolumn.png)

## Controlling Tree Grid actions

You can enable or disable tree grid action for a particular column by setting the [`AllowFiltering`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.TreeGridColumn~AllowFiltering.html), and [`AllowSorting`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.TreeGridColumn~AllowSorting.html) properties of [`TreeGridColumn`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.TreeGridColumn.html) tag helper.

{% aspTab template="tree-grid/column/treegridaction", sourceFiles="index.razor,treegriddata.cs" %}

{% endaspTab %}

## Show/hide columns by external button

You can show or hide tree grid columns dynamically using external buttons by invoking the [`ShowColumns`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.SfTreeGrid~ShowColumns.html) or [`HideColumns`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.SfTreeGrid~HideColumns.html) method.

{% aspTab template="tree-grid/column/showhide", sourceFiles="index.razor,treegriddata.cs" %}

{% endaspTab %}

## How to render boolean values as checkbox

To render boolean values as checkbox in columns, you need to set [`DisplayAsCheckBox`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.TreeGridColumn~DisplayAsCheckBox.html) property as **true**.

{% aspTab template="tree-grid/column/boolcheckbox", sourceFiles="index.razor,treegriddata.cs" %}

{% endaspTab %}

The following output is displayed as a result of the above code example.

![Checkbox](images/boolcheckbox.png)