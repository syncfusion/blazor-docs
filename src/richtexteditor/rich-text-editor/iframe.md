---
title: "Blazor Rich Text Editor | Iframe mode rendering (classic)"
component: "Rich Text Editor"
description: "This section explains how to render the Blazor Rich Text Editor using iframe element that helps classic customers use the HTML editor."
---

# Iframe

When the `RichTextEditorIframeSettings` option is enabled, the Rich Text Editor creates the iframe element as the content area on component initialization; it is used to display and edit the content. In content area, the editor displays only the body tag of a `<iframe>` document.

```csharp

@using Syncfusion.Blazor.RichTextEditor

<SfRichTextEditor>
    <RichTextEditorIFrameSettings Enable="true" Attributes="@IframeAttributes"></RichTextEditorIFrameSettings>
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
    public object IframeAttributes = new
    {
       style = "background: lightgray;"
    };
}

```

The output will be as follows.

![Iframe](./images/iframe-default.png)

## IFrame attributes

The editor allows you to pass an additional attribute to body tag of a `<iframe>` element using attributes fields of the `Attributes` fields of `RichTextEditorIframeSettings` property. This property contains name/value pairs in string format. It is used to override the default appearance of the content area.

```csharp

@using Syncfusion.Blazor.RichTextEditor

<SfRichTextEditor>
    <RichTextEditorIFrameSettings Enable="true" Attributes="@IframeAttributes"></RichTextEditorIFrameSettings>
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
    public object IframeAttributes = new
    {
       style = "background: lightgray;"
    };
}

```

## Adding external CSS/Script File

The editor offers you to add external CSS file to style the `<iframe>` element. Easily change the appearance of editor’s content using an external CSS file using `styles` field in the `RichTextEditorIframeSettings` property.

Likewise, add the external script file to the `<iframe>` element using `scripts` field of `RichTextEditorIframeSettings` to provide the additional functionalities to the Rich Text Editor.

```csharp

@using Syncfusion.Blazor.RichTextEditor

<SfRichTextEditor>
    <RichTextEditorIFrameSettings Enable="true" Resources="@Resources"></RichTextEditorIFrameSettings>
    <RichTextEditorToolbarSettings Items="@Tools"></RichTextEditorToolbarSettings>
    <p>Rich Text Editor allows to insert images from online source as well as local computer where you want to insert the image in your content.</p>
    <p><b>Get started Quick Toolbar to click on the image</b></p>
    <p>It is possible to add custom style on the selected image inside the Rich Text Editor through quick toolbar.</p>
    <img alt='Logo' style='width: 300px; height: 300px; transform: rotate(0deg);' src='https://blazor.syncfusion.com/demos/images/RichTextEditor/RTEImage-Feather.png' />
</SfRichTextEditor>

@code {
    public object[] Tools = new object[] {
        "Bold", "Italic", "Underline", "|",
        "Formats", "Alignments", "|", "CreateLink", "Image", "|","SourceCode", "|", "Undo", "Redo", new ToolsCollection { TooltipText= "Preview",
        Template= @"<button id='preview-code' class='e-tbar-btn e-control e-btn e-icon-btn'><span class='e-btn-icon e-md-preview e-icon'></span></button>"}
    };
    public ResourcesModel Resources = new ResourcesModel
    {
        Scripts = new string[] {"/style.js" },
        Styles = new string[] { "/style.css" }
    };
    public class ToolsCollection
    {
        public string TooltipText { get; set; }
        public string Template { get; set; }
    }
}

```

## See Also

* [How to change the editor mode](./editor-modes/#markdown-editor)