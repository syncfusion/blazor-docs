---
component: "Tree Grid"
---

# Clipboard

The clipboard provides an option to copy selected rows or cells data into the clipboard.

The following list of keyboard shortcuts is supported in the Tree Grid to copy selected rows or cells data into the clipboard.

Interaction keys |Description
-----|-----
<kbd>Ctrl + C</kbd> |Copy selected rows or cells data into clipboard.
<kbd>Ctrl + Shift + H</kbd> |Copy selected rows or cells data with header into clipboard.

{% aspTab template="tree-grid/clip-board/copy", sourceFiles="index.razor,treegriddata.cs" %}

{% endaspTab %}

## Copy to clipboard by external buttons

To copy selected rows or cells data into the clipboard with help of external buttons, you need to invoke the `copy` method.

{% aspTab template="tree-grid/clip-board/copyButtons", sourceFiles="index.razor,treegriddata.cs" %}

{% endaspTab %}

## Copy Hierarchy Modes

Tree Grid provides support for a set of copy modes with `CopyHierarchyMode` property.
The below are the type of filter mode available in Tree Grid.

* **Parent** : This is the default copy hierarchy mode in Tree Grid. Clipboard value will have the selected records with its parent records, if the selected records not have any parent record then the selected record will be in clipboard.

* **Child** : Clipboard value will have the selected records with its child record. If the selected records do not have any child record then the selected records will be in clipboard.

* **Both** : Clipboard value will have the selected records with its both parent and child record. If the selected records do not have any parent and child record then the selected records alone are copied to clipboard.

* **None** : Only the Selected records will be in clipboard.

{% aspTab template="tree-grid/clip-board/hierarchy", sourceFiles="index.razor,treegriddata.cs" %}

{% endaspTab %}

## AutoFill

AutoFill Feature allows you to copy the data of selected cells and paste it to another cells by just dragging the autofill icon of the selected cells up to required cells. This feature is enabled by defining `EnableAutoFill` property as true.

{% aspTab template="tree-grid/clip-board/autofill", sourceFiles="index.razor,treegriddata.cs" %}

{% endaspTab %}

> * If `EnableAutoFill` is set to true, then the autofill icon will be displayed on cell selection to copy cells.
> * It requires the selection `Mode` to be `Cell`,  `CellSelectionMode` to be `Box` and also Batch Editing should be enabled.

### Limitations of AutoFill

* Since the string values are not parsed to number and date type, so when the selected string type cells are dragged to number type cells then it will display as **NaN**. For date type cells, when the selected string type cells are dragged to date type cells then it will display as an **empty cell**.
* Linear series and the sequential data generations are not supported in this autofill feature.

## Paste

You can able to copy the content of a cell or a group of cells by selecting the cells and pressing <kbd>Ctrl + C</kbd> shortcut key and paste it to another set of cells by selecting the cells and pressing <kbd>Ctrl + V</kbd> shortcut key.

{% aspTab template="tree-grid/clip-board/paste", sourceFiles="index.razor,treegriddata.cs" %}

{% endaspTab %}

> To perform paste functionality, it requires the selection `Mode` to be `Cell`,  `cellSelectionMode` to be `Box` and also Batch Editing should be enabled.

### Limitations of Paste Functionality

* Since the string values are not parsed to number and date type, so when the copied string type cells are pasted to number type cells then it will display as **NaN**. For date type cells, when the copied string format cells are pasted to date type cells then it will display as an **empty cell**.