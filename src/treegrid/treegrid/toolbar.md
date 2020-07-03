---
title: "Toolbar"
component: "Tree Grid"
description: "Learn how to use the toolbar and add custom toolbar items in the Blazor Tree Grid."
---

# Toolbar

The Tree Grid provides Toolbar support to handle tree grid actions.

## Built-in toolbar items

Built-in toolbar items execute standard actions of the tree grid, and it can be added by defining the [`Toolbar`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.SfTreeGrid~Toolbar.html)
as a collection of built-in items. It renders the button with icon and text.

The following table shows built-in toolbar items and its actions.

| Built-in Toolbar Items | Actions |
|------------------------|---------|
| ExpandAll | Expands all the rows.|
| CollapseAll | Collapses all the rows.|
| Add | Adds a new record.|
| Edit | Edits the selected record.|
| Update | Updates the edited record.|
| Delete | Deletes the selected record.|
| Cancel | Cancels the edit state.|
| Search | Searches the records by the given key.|
| Print | Prints the tree grid.|
| ExcelExport | Exports the tree grid to Excel.|
| PdfExport | Exports the tree grid to PDF.|
| WordExport | Exports the tree grid to Word.|

{% aspTab template="treegrid/toolbar/inbuilttoolbar", sourceFiles="index.razor,treegriddata.cs" %}

{% endaspTab %}

The following output is displayed as a result of the above code example.

![Built-in Toolbar](images/inbuilt.png)

> The [`Toolbar`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.SfTreeGrid~Toolbar.html) has options to define both built-in and custom toolbar items.

<!--
Custom toolbar items

Custom toolbar items can be added by defining the [`Toolbar`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.SfTreeGrid~Toolbar.html) as a collection of
**ItemModels**.
Actions for this customized toolbar items are defined in the [`ToolbarClick`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.SfTreeGrid~ToolbarClick.html) event.

By default, Custom toolbar items are in position **Left**. You can change the position by using the **Align** property. In the below sample, we have applied position **Right** for the **Quick Filter** toolbar item.

> The [`Toolbar`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.TreeGrid.SfTreeGrid~Toolbar.html) has options to define both built-in and custom toolbar items.
> If a toolbar item does not match the built-in items, it will be treated as a custom toolbar item.

 Built-in and custom items in toolbar

Tree Grid have an option to use both built-in and custom toolbar items at same time.

In the below example, **ExpandAll**, **CollapseAll** are built-in toolbar items and **Click** is custom toolbar item.

Enable/disable toolbar items

You can enable/disable toolbar items by using the **enableItems** method.

-->