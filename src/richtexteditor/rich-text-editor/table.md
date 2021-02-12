---
component: "Rich Text Editor"
---

# Table

Rich Text Editor allows you to insert table of content in edit panel and provide options to add, edit, and remove the table as well as perform other table related action. For inserting the table to the Rich Text Editor, the following list of options have been provided in the `RichTextEditorTableSettings`

| Options | Description | Default Value |
|----------------|---------|-----------------------------|
| MinWidth | Sets the default minWidth of the table. | 0 |
| MaxWidth | Sets the default maxWidth of the table. | null |
| EnableResize | Enables resize feature in table.| true |
| Styles | This is an array of key value pair, on each pair, key should be name of styling and value is class name. this list will be shown on quick toolbar options to change the styles of table on designing like dashed, double bordered. | `List<DropDownItemModel>` |
| Width | Sets the default width of the table. | 100% |

## Insert table

Using the `CreateTable` toolbar option, select a number of rows and columns to be inserted over the table
grid and insert table into Rich Text Editor content using the mouse.

Tables can also be inserted through the `Insert Table` option in the pop-up where the number of rows
and columns can be provided manually and this is the default way in devices.

In the following sample, the table has been inserted using `CreateTable` toolbar item.

```csharp

@using Syncfusion.Blazor.RichTextEditor

<SfRichTextEditor ShowCharCount="true">
    <RichTextEditorToolbarSettings Items="@Tools" />
    <p>The Rich Text Editor component is WYSIWYG ('what you see is what you get') editor that provides the best user experience to create and update the content. Users can format their content using standard toolbar commands.</p>
    <p><b> Key features:</b></p>
    <ul>
    <li><p> Provides <b>IFRAME</b> and <b>DIV</b> modes </p></li>
    <li><p> Capable of handling markdown editing.</p></li>
    <li><p> Contains a modular library to load the necessary functionality on demand.</p></li>
    <li><p> Provides a fully customizable toolbar.</p></li>
    <li><p> Provides HTML view to edit the source directly for developers.</p></li>
    <li><p> Supports third - party library integration.</p></li>
    </ul>
</SfRichTextEditor>

@code{
    private List<ToolbarItemModel> Tools = new List<ToolbarItemModel>()
    {
        new ToolbarItemModel() { Command = ToolbarCommand.CreateTable }
    };
}

```

The output will be as follows.

![Table](./images/table-tool.png)

## Quick Toolbar

Quick toolbar is opened by clicking the table. It has different sets of commands to be performed on
the table which increases the feasibility to edit the table easily.

## Table Header

`Table Header` command is available with quick toolbar option through which the header row can be
added or removed from the inserted table. The following image illustrates the table header.

![RTE table header](./images/table_header.png)

## Insert Rows

`Rows` can be inserted above or below the required table cell through the quick toolbar. Also,
focused row can be deleted. The following screenshot shows the available options of the row item.

![RTE table row](./images/table_rows.png)

## Insert Columns

`Columns` can be inserted to the left or right side of the required table cell through the quick
toolbar. Also, the focused column can be deleted. The following screenshot shows the available
options of the column item.

![RTE table column](./images/table_column.png)

## Set Color

The Background Color can be set for each table cell through the `BackgroundColor` command available
with quick toolbar.

![RTE table background color](./images/table_bg_color.png)

## Delete Table

Using the delete item in the quick toolbar, users can delete the entire table.

## Vertical Align

Text inside the table can be aligned to top, middle, or bottom using the `TableCellVerticalAlign`
command of the quick toolbar.

![RTE table vertical alignment](./images/table_vertical.png)

## Horizontal Align

Text inside the table can be aligned left, right, or center using the `TableCellHorizontalAlign` command
of the quick toolbar.

![RTE table horizontal alignment](./images/table_horizontal.png)

## Table Styles

Table styles provided for class name should be appended to a table element. It helps to design the
table in specific CSS styles when inserting in the editor.

By default, provides `Dashed border` and `Alternate rows`.

**Dashed border**: Applies the dashed border to the table.

**Alternate border**: Applies the alternative background to the table.

![RTE table styles](./images/table_style.png)

### Custom Styles

Rich Text Editor provides support to custom styles for tables. If you want to add additional styles, pass the styles information as `List<DropDownItemModel>` data to the `Styles` field of `RichTextEditorTableSettings` tag.

```csharp

<SfRichTextEditor>
    <RichTextEditorTableSettings Styles="@StyleItems" />
    <RichTextEditorToolbarSettings Items="@Tools" />
</SfRichTextEditor>

@code{
    private List<ToolbarItemModel> Tools = new List<ToolbarItemModel>()
    {
        new ToolbarItemModel() { Command = ToolbarCommand.CreateTable }
    };

    private List<DropDownItemModel> StyleItems = new List<DropDownItemModel>()
    {
        new DropDownItemModel() { Text = "Alternate Rows" }
    };
}

```

The output will be as follows.

![Custom Table Styles](./images/custom-table-styles.png)

## Table Properties

Sets the default width of the table when it is inserted in the Rich Text Editor using the width of
`RichTextEditorTableSettings`.

Using the quick toolbar, users can change the width, cell padding, and cell spacing in the selected
table using the `TableEditProperties` command dialog action.

![RTE table settings](./images/table_properties.png)