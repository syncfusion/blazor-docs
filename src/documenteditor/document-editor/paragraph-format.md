---
title: "Working with Paragraph Formatting"
component: "Word processor"
description: "Learn paragraph formatting supported in Blazor Word processor and how to apply it for selected contents."
---

# Working with Paragraph Formatting

Document editor supports various paragraph formatting options such as text alignment, indentation, paragraph spacing, and more.

## Indentation

You can modify the left or right indentation of selected paragraphs using the following sample code.

```javascript
documentEditor.GetSelection().GetParagraphFormat().SetLeftIndent(24);
documentEditor.GetSelection().GetParagraphFormat().SetRightIndent(24);
```

## Special indentation

You can define special indent for first line of the paragraph using the following sample code.

```javascript
documentEditor.GetSelection().GetParagraphFormat().SetFirstLineIndent(24);
```

## Increase indent

You can increase the left indent of selected paragraphs by a factor of 36 points using the following sample code.

```javascript
documentEditor.GetEditor().IncreaseIndent();
```

## Decrease indent

You can decrease the left indent of selected paragraphs by a factor of 36 points using the following sample code.

```javascript
documentEditor.GetEditor().DecreaseIndent();
```

## Text alignment

You can get or set the text alignment of selected paragraphs using the following sample code.

```javascript
documentEditor.GetSelection().GetParagraphFormat().SetTextAlignment(TextAlignment.Center);
```

You can toggle the text alignment of selected paragraphs by specifying a value using the following sample code.

```javascript
documentEditor.GetEditor().ToggleTextAlignment(TextAlignment.Center);
```

## Line spacing and its type

You can define the line spacing and its type for selected paragraphs using the following sample code.

```javascript
documentEditor.GetSelection().GetParagraphFormat().SetLineSpacingType(LineSpacingType.AtLeast);
documentEditor.GetSelection().GetParagraphFormat().SetLineSpacing(6);
```

## Paragraph spacing

You can define the spacing before or after the paragraph by using the following sample code.

```javascript
documentEditor.GetSelection().GetParagraphFormat().SetBeforeSpacing(24);
documentEditor.GetSelection().GetParagraphFormat().SetAfterSpacing(24);
```
