---
title: "Working with Table Formatting"
component: "Word processor"
description: "Learn table, cell, and row formatting supported in Blazor Word processor and how to apply it for selected contents."
---

# Working with Table Formatting

Document editor customizes the formatting of table, or table cells such as table width, cell margins, cell spacing, background color, and table alignment. This section describes how to customize these formatting for selected cells, rows, or table in detail.

## Cell margins

You can customize the cell margins by using the following sample code.

```javascript
//To change the left margin
documentEditor.GetSelection().GetCellFormat().SetLeftMargin(5);
//To change the right margin
documentEditor.GetSelection().GetCellFormat().SetRightMargin(5);
//To change the top margin
documentEditor.GetSelection().GetCellFormat().SetTopMargin(5);
//To change the bottom margin
documentEditor.GetSelection().GetCellFormat().SetBottomMargin(5);
```

You can also define the default cell margins for a table. If the specific cell margin value is not defined explicitly in the cell formatting, the corresponding value will be retrieved from default cells margin of the table. Refer to the following sample code.

```javascript
//To change the left margin
documentEditor.GetSelection().GetTableFormat().SetLeftMargin(5);
//To change the right margin
documentEditor.GetSelection().GetTableFormat().SetRightMargin(5);
//To change the top margin
documentEditor.GetSelection().GetTableFormat().SetTopMargin(5);
//To change the bottom margin
documentEditor.GetSelection().GetTableFormat().SetBottomMargin(5);
```

## Background color

You can explicitly set the background color of selected cells using the following sample code.

```javascript
documentEditor.GetSelection().GetCellFormat().SetBackground("#E0E0E0");
```

Refer to the following sample code to customize the background color of the table.

```javascript
documentEditor.GetSelection().GetTableFormat().SetBackground("#E0E0E0");
```

## Cell spacing

Refer to the following sample code to customize the spacing between each cell in a table.

```javascript
documentEditor.GetSelection().GetTableFormat().SetCellSpacing(2);
```

## Cell vertical alignment

The content is aligned within a table cell to `Top`, `Center`, or `Bottom`. You can customize this property of selected cells. Refer to the following sample code.

```javascript
documentEditor.GetSelection().GetCellFormat().SetVerticalAlignment(CellVerticalAlignment.Bottom);
```

## Table alignment

The tables are aligned in document editor to `Left`, `Right`, or `Center`. Refer to the following sample code.

```javascript
documentEditor.GetSelection().GetTableFormat().SetTableAlignment(TableAlignment.Center);
```

## Cell width

Set the desired width of table cells that will be considered when the table is layouted. Refer to the following sample code.

```csharp
@using Syncfusion.Blazor.DocumentEditor;
<SfDocumentEditor @ref="documentEditor" IsReadOnly=false EnableEditor=true EnableSelection=true>
    <DocumentEditorContainerEvents Created="OnLoad"></DocumentEditorContainerEvents>
</SfDocumentEditor>

@code {
    SfDocumentEditor documentEditor;
    protected void OnLoad(object args)
    {
        documentEditor.GetEditor().InsertTable(2, 2);
        documentEditor.GetSelection().GetCellFormat().SetPreferredWidth(100);
        documentEditor.GetSelection().GetCellFormat().SetPreferredWidthType(WidthType.Point);
    }
}
```

## Table width

You can set the desired width of a table in `Point` or `Percent` type. Refer to the following sample code.

```csharp
@using Syncfusion.Blazor.DocumentEditor
<SfDocumentEditor @ref="documentEditor" IsReadOnly=false EnableEditor=true EnableSelection=true>
    <DocumentEditorContainerEvents Created="OnLoad"></DocumentEditorContainerEvents>
</SfDocumentEditor>

@code {
    SfDocumentEditor documentEditor;
    protected void OnLoad(object args)
    {
        documentEditor.GetEditor().InsertTable(2, 2);
        documentEditor.GetSelection().GetTableFormat().SetPreferredWidth(300);
        documentEditor.GetSelection().GetTableFormat().SetPreferredWidthType(WidthType.Point);
    }
}
```

# Working with row formatting

Document editor allows various row formatting such as height and repeat header.

## Row height

You can customize the height of a table row as `Auto`, `AtLeast`, or `Exactly`. Refer to the following sample code.

```csharp
@using Syncfusion.Blazor.DocumentEditor
<SfDocumentEditor @ref="documentEditor" IsReadOnly=false EnableEditorHistory=true EnableEditor=true EnableSelection=true>
    <DocumentEditorContainerEvents Created="OnLoad"></DocumentEditorContainerEvents>
</SfDocumentEditor>

@code {
    SfDocumentEditor documentEditor;
    protected void OnLoad(object args)
    {
        documentEditor.GetEditor().InsertTable(2, 2);
        documentEditor.GetSelection().GetRowFormat().SetHeight(20);
        documentEditor.GetSelection().GetRowFormat().SetHeightType(HeightType.Exactly);
    }
}
```

## Header row

The header row describes the content of a table. A table can optionally have a header row. Only the first row of a table can be the header row. If the cursor position is at first row of the table, then you can define whether it as header row or not, using the following sample code.

```javascript
documentEditor.GetSelection().GetRowFormat().SetIsHeader(true);
```

## Allow row break across pages

This property is valid if a table row does not fit in the current page during table layout. It defines whether a table row can be allowed to break. If the value is false, the entire row will be moved to the start of next page. You can modify this property for selected rows using the following sample code.

```javascript
documentEditor.GetSelection().GetRowFormat().SetAllowBreakAcrossPages(false);
```
