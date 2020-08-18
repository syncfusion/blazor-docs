---
title: "Blazor Rich Text Editor | how to | Change the default font family"
component: "Rich Text Editor"
description: "This section explains on how to change the default `fontFamily`."
---

# Change default font-family

By using `Default` property, you can change the default font-family of the Rich Text Editor. To change the font-family of the Rich Text Editor content while loading, we need to give the `RichTextEditorFontFamily` in the style section with the help of `CssClass` property.

```csharp

@using Syncfusion.Blazor.RichTextEditor

<SfRichTextEditor CssClass="customClass">
    <RichTextEditorToolbarSettings Items="@Tools"></RichTextEditorToolbarSettings>
    <RichTextEditorFontFamily Default="Noto Sans" Items="@FontItems"></RichTextEditorFontFamily>
    <p>The Rich Text Editor component is WYSIWYG ('what you see is what you get') editor that provides the best user experience to create and update the content. Users can format their content using standard toolbar commands.</p>
    <p><b> Key features:</b></p>
    <ul>
        <li><p> Provides <b>IFRAME</b> and <b>DIV</b> modes </p></li>
        <li><p> Capable of handling markdown editing.</p></li>
        <li><p> Contains a modular library to load the necessary functionality on demand.</p></li>
        <li><p> Provides a fully customizable toolbar.</p></li>
        <li><p> Provides HTML view to edit the source directly for developers.</p></li>
        <li><p> Supports third - party library integration.</p></li>
        <li><p> Allows preview of modified content before saving it.</p></li>
    </ul>
</SfRichTextEditor>

<style>
    .customClass .e-rte-content .e-content {
        /* to get the desired font on intially*/
        font-family: "Noto Sans";
    }
</style>

@code {
    public List<IDropDownItemModel> FontItems = new List<IDropDownItemModel>() {
        new IDropDownItemModel() { text = "Segoe UI", value = "Segoe UI" },
        new IDropDownItemModel() { text = "Roboto", value = "Roboto" },
        // here font is added
        new IDropDownItemModel() { text = "Great vibes", value = "Great Vibes,cursive"},
        new IDropDownItemModel() { text = "Noto Sans", value = "Noto Sans" },
        new IDropDownItemModel() { text = "Impact", value = "Impact,Charcoal,sans-serif" },
        new IDropDownItemModel() { text = "Tahoma", value = "Tahoma,Geneva,sans-serif" }
    };
    public object[] Tools = new object[]{
        "Bold", "Italic", "Underline", "|", "FontName", "FontSize", "FontColor",
        "Formats", "Alignments", "|", "CreateLink", "Image", "|", "SourceCode", "|", "Undo", "Redo"
    };
    public class IDropDownItemModel
    {
        public string text { get; set; }
        public string value { get; set; }
    }
}

```

The output will be as follows.

![Default Font](../images/default-font.png)