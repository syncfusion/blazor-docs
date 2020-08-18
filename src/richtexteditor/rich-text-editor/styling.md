---
title: "Blazor Rich Text Editor | Custom Font name, size, and color"
component: "Rich Text Editor"
description: "This section describes the list of default font names and sizes supported by default and how to customize them in the Blazor Rich Text editor."
---

# Styling

## Font name and size

By default, the editor is initialized with font name and font size as `null`. To change it, select a different font name and font size from the drop-down in the editor’s toolbar.

To apply different font style for section of the content, select the text that you would like to change, and select a required font style from the drop-down to apply the changes to the selected text.

### Font name

The following table lists the default font name and width of the `FontName` dropdown and available list of font names.

| Default Key | Default Value |
|----------------|--------------------------------------|
| Font name | null |
| Width | 65px|
| Items | { Text: 'Segoe UI', Value: 'Segoe UI' },{ Text: 'Arial', Value: 'Arial,Helvetica,sans-serif' },{ Text: 'Courier New', Value: 'Courier New,Courier,monospace' },{ Text: 'Georgia', Value: 'Georgia,serif' },{ Text: 'Impact', Value: 'Impact,Charcoal,sans-serif' },{ Text: 'Lucida Console', Value: 'Lucida Console,Monaco,monospace' },{ Text: 'Tahoma', Value: 'Tahoma,Geneva,sans-serif' },{ Text: 'Times New Roman', Value: 'Times New Roman,Times,serif' },{ Text: 'Trebuchet MS', Value: 'Trebuchet MS,Helvetica,sans-serif' },{ Text: 'Verdana', Value: 'Verdana,Geneva,sans-serif' }|

### Font size

The following table list the default font size and width of the `FontSize` dropdown and available list of font size.

| Default Key | Default Value |
|----------------|---------|
| Font size | null |
| Width | 35px.|
| Items |{ Text: '8 pt', Value: '8pt' },{ Text: '10 pt', Value: '10pt' },{ Text: '12 pt', Value: '12pt' },{ Text: '14 pt', Value: '14pt' },{ Text: '18 pt', Value: '18pt' },{ Text: '24 pt, Value: '24pt' },{ Text: '36 pt', Value: '36pt' }.|

The following sample demonstrates the option to add the font name and font size tools to the toolbar as well as modify the default `Width` of the tools.

```csharp

@using Syncfusion.Blazor.RichTextEditor

<SfRichTextEditor FontSize="@FontSize" FontFamily="@FontFamily">
    <RichTextEditorToolbarSettings Items="@Tools"></RichTextEditorToolbarSettings>
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

@code {
    public object[] Tools = new object[] {
        "Bold", "Italic", "Underline", "FontName", "FontSize", "FontColor", "BackgroundColor", "|",
        "Formats", "Alignments", "|", "CreateLink", "Image", "|","SourceCode", "|", "Undo", "Redo"
    };
    public RichTextEditorFontFamily FontFamily = new RichTextEditorFontFamily { Width = "50px" };
    public RichTextEditorFontSize FontSize = new RichTextEditorFontSize{ Width = "50px" };
}

```

The output will be as follows.

![Font Size](./images/font-size.png)

## Custom font and size

Rich Text Editor provides support to custom fonts and size with existing list.
If you want to add additional font names and font sizes to font drop-down, pass the font information as JSON data to the items field of `FontSize` and `FontFamily` property.

```csharp

@using Syncfusion.Blazor.RichTextEditor

<SfRichTextEditor>
        <RichTextEditorToolbarSettings Items="@Tools"></RichTextEditorToolbarSettings>
        <RichTextEditorFontFamily Width="50px" Items="@FontItems"></RichTextEditorFontFamily>
        <RichTextEditorFontSize Width="50px" Items="@FontSizeItems" ></RichTextEditorFontSize>
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

@code {
    public object[] Tools = new object[] {
        "Bold", "Italic", "Underline", "FontName", "FontSize", "FontColor", "BackgroundColor", "|",
        "Formats", "Alignments", "|", "CreateLink", "Image", "|","SourceCode", "|", "Undo", "Redo"
    };
    public List<IDropDownItemModel> FontItems = new List<IDropDownItemModel>() {
        new IDropDownItemModel() { text = "Segoe UI", value = "Arial,Helvetica,sans-serif" },
        new IDropDownItemModel() { text = "Arial", value = "Roboto" },
        new IDropDownItemModel() { text = "Courier New", value = "Courier New,Courier,monospace"},
        new IDropDownItemModel() { text = "Georgia", value = "Georgia,serif" },
        new IDropDownItemModel() { text = "Impact", value = "Impact,Charcoal,sans-serif" },
        new IDropDownItemModel() { text = "Calibri Light", value = "CalibriLight" }
    };
    public List<IDropDownItemModel> FontSizeItems = new List<IDropDownItemModel>() {
        new IDropDownItemModel() { text = "8 pt", value = "8pt" },
        new IDropDownItemModel() { text = "10 pt", value = "10pt" },
        new IDropDownItemModel() { text = "12 pt", value = "12pt"},
        new IDropDownItemModel() { text = "14 pt", value = "14pt" },
        new IDropDownItemModel() { text = "42 pt", value = "42pt" }
    };
    public class IDropDownItemModel
    {
        public string text { get; set; }
        public string value { get; set; }
    }
}

```

The output will be as follows.

![Custom Fonts](./images/custom-font.png)

![Custom Font size](./images/custom-font-size.png)

## Font and Background color

To apply font color or background color for a selected content of RTE, use the font color and background color tools.

Rich Text Editor support to provide customs font color and background color with existing list through the `ColorCode` field of `FontColor` and `BackgroundColor`.

The FontColor and BackgroundColor property has two `Mode` Picker and Palette. Palette mode has predefined set of `ColorCode` and in the picker mode, more colors has been provided. Through `ModeSwitcher`, you can able to switch between these two options.

```csharp

@using Syncfusion.Blazor.RichTextEditor

<SfRichTextEditor BackgroundColor="@BackgroundColor" FontColor="@FontColor">
    <RichTextEditorToolbarSettings Items="@Tools"></RichTextEditorToolbarSettings>
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

@code {
    public object[] Tools = new object[] {
        "Bold", "Italic", "Underline", "FontName", "FontSize", "FontColor", "BackgroundColor", "|",
        "Formats", "Alignments", "|", "CreateLink", "Image", "|","SourceCode", "|", "Undo", "Redo"
    };
    public RichTextEditorBackgroundColor BackgroundColor = new RichTextEditorBackgroundColor { ModeSwitcher = true };
    public RichTextEditorFontColor FontColor = new RichTextEditorFontColor { ModeSwitcher = true };
}

```

The output will be as follows.

![Font Color](./images/font-color.png)

![Background Color](./images/background-color.png)

## Editor content styles

By default, The content styles of Rich Text Editor are not returned while retrieving HTML value from the editor. So, the styles are not applied when using the HTML value outside of the editor. To get the styles to Rich Text Editor’s content for your application, You can copy and use the below styles directly in your application. The styles listed below which used in the UI elements of the Rich Text Editor.  

> Make sure to add a CSS class ‘e-rte-content’ to the content container.

```css

.e-rte-content p {
  margin: 0 0 10px;
  margin-bottom: 10px;
}

.e-rte-content li {
  margin-bottom: 10px;
}

.e-rte-content h1 {
  font-size: 2.17em;
  font-weight: 400;
  line-height: 1;
  margin: 10px 0;
}

.e-rte-content h2 {
  font-size: 1.74em;
  font-weight: 400;
  margin: 10px 0;
}

.e-rte-content h3 {
  font-size: 1.31em;
  font-weight: 400;
  margin: 10px 0;
}

.e-rte-content h4 {
  font-size: 1em;
  font-weight: 400;
  margin: 0;
}

.e-rte-content h5 {
  font-size: 00.8em;
  font-weight: 400;
  margin: 0;
}

.e-rte-content h6 {
  font-size: 00.65em;
  font-weight: 400;
  margin: 0;
}

.e-rte-content blockquote {
  margin: 10px 0;
  margin-left: 0;
  padding-left: 5px;
}

.e-rte-content pre {
  background-color: inherit;
  border: 0;
  border-radius: 0;
  color: #333;
  font-size: inherit;
  line-height: inherit;
  margin: 0 0 10px;
  overflow: visible;
  padding: 0;
  white-space: pre-wrap;
  word-break: inherit;
  word-wrap: break-word;
}

.e-rte-content strong, .e-rte-content b {
  font-weight: 700;
}

.e-rte-content a {
  text-decoration: none;
  -webkit-user-select: auto;
  -ms-user-select: auto;
  user-select: auto;
}

.e-rte-content a:hover {
  text-decoration: underline;
}

.e-rte-content h3 + h4,
.e-rte-content h4 + h5,
.e-rte-content h5 + h6 {
  margin-top: 00.6em;
}

.e-rte-content .e-rte-image.e-imgbreak {
  border: 0;
  cursor: pointer;
  display: block;
  float: none;
  margin: 5px auto;
  max-width: 100%;
  position: relative;
}

.e-rte-content .e-rte-image {
  border: 0;
  cursor: pointer;
  display: block;
  float: none;
  margin: auto;
  max-width: 100%;
  position: relative;
}

.e-rte-content .e-rte-image.e-imginline {
  display: inline-block;
  float: none;
  margin-left: 5px;
  margin-right: 5px;
  max-width: calc(100% - (2 * 5px));
  vertical-align: bottom;
}

.e-rte-content .e-rte-image.e-imgcenter {
  cursor: pointer;
  display: block;
  float: none;
  margin: 5px auto;
  max-width: 100%;
  position: relative;
}

.e-rte-content .e-rte-image.e-imgleft {
  float: left;
  margin: 0 5px 0 0;
  text-align: left;
}

.e-rte-content .e-rte-image.e-imgright {
  float: right;
  margin: 0 0 0 5px;
  text-align: right;
}

.e-rte-content .e-rte-img-caption {
  display: inline-block;
  margin: 5px auto;
  max-width: 100%;
  position: relative;
}

.e-rte-content .e-rte-img-caption.e-caption-inline {
  display: inline-block;
  margin: 5px auto;
  margin-left: 5px;
  margin-right: 5px;
  max-width: calc(100% - (2 * 5px));
  position: relative;
  text-align: center;
  vertical-align: bottom;
}

.e-rte-content .e-rte-img-caption.e-imgcenter {
  display: block;
}

.e-rte-content .e-rte-img-caption .e-rte-image.e-imgright,
.e-rte-content .e-rte-img-caption .e-rte-image.e-imgleft {
  float: none;
  margin: 0;
}

.e-rte-content .e-rte-table {
  border-collapse: collapse;
  empty-cells: show;
}

.e-rte-content .e-rte-table td,
.e-rte-content .e-rte-table th {
  border: 1px solid #bdbdbd;
  height: 20px;
  min-width: 20px;
  padding: 2px 5px;
  vertical-align: middle;
}

.e-rte-content .e-rte-table.e-dashed-border td,
.e-rte-content .e-rte-table.e-dashed-border th {
  border-style: dashed;
}

.e-rte-content .e-rte-img-caption .e-img-inner {
  box-sizing: border-box;
  display: block;
  font-size: 16px;
  font-weight: initial;
  margin: auto;
  opacity: .9;
  position: relative;
  text-align: center;
  width: 100%;
}

.e-rte-content .e-rte-img-caption .e-img-wrap {
  display: inline-block;
  margin: auto;
  padding: 0;
  width: 100%;
}

.e-rte-content blockquote {
  border-left: solid 2px #333;
}

.e-rte-content a {
  color: #2e2ef1;
}

.e-rte-content .e-rte-table th {
  background-color: #e0e0e0;
}

```

## See Also

* [How to add google fonts to the font family](./how-to/add-google-fonts/)
* [How to customize the placeholder](./how-to/placeholder/)