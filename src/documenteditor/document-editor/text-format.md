---
title: "Working with Text Formatting"
component: "Word processor"
description: "Learn text formatting supported in Blazor Word processor and how to apply it for selected contents."
---

# Working with Text Formatting

Document editor supports several formatting options for text like bold, italic, font color, highlight color, and more. This section describes how to modify the formatting for selected text in detail.

## Bold

The bold formatting for selected text can be get or set by using the following sample code.

```javascript

//Gets the value for bold formatting of selected text.
bool bold = await documentEditor.GetSelection().GetCharacterFormat().GetBold();
//Sets bold formatting for selected text.
documentEditor.GetSelection().GetCharacterFormat().SetBold(true);

```

You can toggle the bold formatting based on existing value at selection. Refer to the following sample code.

```javascript
documentEditor.GetEditor().ToggleBold();
```

## Italic

The Italic formatting for selected text can be get or set by using the following sample code.

```javascript
documentEditor.GetSelection().GetCharacterFormat().SetItalic(true);
```

You can toggle the Italic formatting based on existing value at selection. Refer to the following sample code.

```javascript
documentEditor.GetEditor().ToggleItalic();
```

## Underline property

The underline style for selected text can be get or set by using the following sample code.

```javascript
documentEditor.GetEditor().ToggleUnderline(Underline.Single);
```

You can toggle the underline style of selected text based on existing value at selection by specifying a value. Refer to the following sample code.

```javascript
documenteditor.editor.toggleUnderline('Single');
```

## Strikethrough property

The strikethrough style for selected text can be get or set by using the following sample code.

```javascript
documentEditor.GetEditor().ToggleStrikethrough(Strikethrough.SingleStrike);
```

You can toggle the strikethrough style of selected text based on existing value at selection by specifying a value. Refer to the following sample code.

```javascript
documentEditor.GetEditor().ToggleStrikethrough(Strikethrough.SingleStrike);
```

## Superscript property

The selected text can be made superscript by using the following sample code.

```javascript
documentEditor.GetSelection().GetCharacterFormat().SetBaselineAlignment(BaselineAlignment.Superscript);
```

Toggle the selected text as superscript or normal using the following sample code.

```javascript
documentEditor.GetEditor().ToggleSuperscript();
```

## Subscript property

The selected text can be made subscript by using the following sample code.

```javascript
documentEditor.GetSelection().GetCharacterFormat().SetBaselineAlignment(BaselineAlignment.Subscript);
```

Toggle the selected text as subscript or normal using the following sample code.

```javascript
documentEditor.GetEditor().ToggleSubscript();
```

You can make a subscript or superscript text as normal using the following code.

```javascript
documentEditor.GetSelection().GetCharacterFormat().SetBaselineAlignment(BaselineAlignment.Normal);
```

## Size

The size of selected text can be get or set using the following code.

```javascript
documentEditor.GetSelection().GetCharacterFormat().SetFontSize(32);
```

## Color

The color of selected text can be get or set using the following code.

```javascript
documentEditor.GetSelection().GetCharacterFormat().SetFontColor("Pink");
documentEditor.GetSelection().GetCharacterFormat().SetFontColor("FFC0CB");
```

## Font

The font style of selected text can be get or set using the following sample code.

```javascript
documentEditor.GetSelection().GetCharacterFormat().SetFontFamily("Arial");
```

## Highlight color

The highlight color of the selected text can be get or set using the following sample code.

```javascript
documentEditor.GetSelection().GetCharacterFormat().SetHighlightColor(HighlightColor.Pink);
```
