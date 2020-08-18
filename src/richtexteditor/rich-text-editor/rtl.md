---
title: " Rich Text Editor Globalization"
component: "Rich Text Editor"
description: "This section explains the rtl support of Syncfusion Blazor Rich Text Editor component."
---

# RTL support

## RTL

Specifies the direction of the Rich Text Editor component using the `enableRtl` property. For writing systems that require it like Arabic, Hebrew, etc., the direction can be switched to right-to-left.

> `enableRtl` property will not change based on `locale` property.

```csharp

@using Syncfusion.Blazor.RichTextEditor

<SfRichTextEditor ID="defalt_RTE" EnableRtl="@EnableRtl">
    <RichTextEditorToolbarSettings Items="@tools"></RichTextEditorToolbarSettings>
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

@functions {
    private bool EnableRtl { get; set; } = true;

    public static object[] tools = new object[]{
        "Bold", "Italic", "Underline", "StrikeThrough",
        "FontName", "FontSize", "FontColor", "BackgroundColor",
        "LowerCase", "UpperCase", "|",
        "Formats", "Alignments", "OrderedList", "UnorderedList",
        "Outdent", "Indent", "|", "CreateTable",
        "CreateLink", "Image", "|", "ClearFormat", "Print",
        "SourceCode", "FullScreen", "|", "Undo", "Redo"
    };
}

```