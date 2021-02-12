---
component: "Rich Text Editor"
---

# ExecCommand in Rich Text Editor

In Rich Text Editor, the ExecuteCommand is used to perform commands for the modification of content in editable area.
The `ExecuteCommand` will perform the following commands.

| Commands | Description | Code snippets |
|----------------|---------| -----------|
| Bold | Bold the selected content in the Rich Text Editor. |`await this.RteObj.ExecuteCommand(CommandName.Bold);`|
| Italic | The selected text will be italics. |`await this.RteObj.ExecuteCommand(CommandName.Italic);`|
| Underline | Underline the selected text in the Rich Text Editor. |`await this.RteObj.ExecuteCommand(CommandName.Underline);`|
| StrikeThrough | Apply single line strike through formatting for the selected text. |`await this.RteObj.ExecuteCommand(CommandName.StrikeThrough);`|
| Superscript | Makes the selected text as superscript (higher). |`await this.RteObj.ExecuteCommand(CommandName.Superscript);`|
| Subscript | Makes the selected text as subscript (lower). |`await this.RteObj.ExecuteCommand(CommandName.Subscript);`|
| Uppercase | Change the case of selected text to upper  in the content. |`await this.RteObj.ExecuteCommand(CommandName.Uppercase);`|
| Lowercase | Change the case of selected text to lower in the content. |`await this.RteObj.ExecuteCommand(CommandName.Lowercase);`|
| FontColor | Apply the specified font color for the selected text. |`await this.RteObj.ExecuteCommand(CommandName.FontColor, "Red");`|
| FontName | Apply the specified font name for the selected text. |`await this.RteObj.ExecuteCommand(CommandName.FontName, "Impact");`|
| FontSize | Apply the specified font size for the selected text. |`await this.RteObj.ExecuteCommand(CommandName.FontSize, "10pt");`|
| BackgroundColor | Apply the specified background color the selected text. | `await this.RteObj.ExecuteCommand(CommandName.BackgroundColor, "red");`|
| JustifyCenter | Align the content with center margin. | `await this.RteObj.ExecuteCommand(CommandName.JustifyCenter);`|
| JustifyFull | Align the content with justify margin. |`await this.RteObj.ExecuteCommand(CommandName.JustifyFull);`|
| JustifyLeft | Align the content with left margin. | `await this.RteObj.ExecuteCommand(CommandName.JustifyLeft);`|
| JustifyRight | Align the content with right margin. | `await this.RteObj.ExecuteCommand(CommandName.JustifyRight);`|
| CreateLink | Creates a hyperlink to a text or image to a specific location in the content. |`await this.RteObj.ExecuteCommand(CommandName.CreateLink, new LinkCommandsArgs() { Text = "Links", Url= "http://", Title = "Link"});}` |
| Indent | Allows to increase the indent level of the content. | `await this.RteObj.ExecuteCommand(CommandName.Indent);`|
| InsertHTML | Insert the html content to the current cursor position. |`await this.RteObj.ExecuteCommand(CommandName.InsertHTML,"<div>Syncfusion Rich Text Editor`|
| InsertOrderedList | Create a new list item(numbered). | `await this.RteObj.ExecuteCommand(CommandName.InsertOrderedList);`|
| InsertUnorderedList | Create a new list item(bulleted). |`await this.RteObj.ExecuteCommand(CommandName.InsertUnorderedList);`|
| Outdent | Allows to decrease the indent level of the content. | `await this.RteObj.ExecuteCommand(CommandName.Outdent);`|
| Redo | Allows to redo the actions | `await this.RteObj.ExecuteCommand(CommandName.Redo);`|
| RemoveFormat | remove all formatting styles (such as bold, italic, underline, color, superscript, subscript, and more) from currently selected text. |`await this.RteObj.ExecuteCommand(CommandName.RemoveFormat);`|
| InsertText | Insert text to the current cursor position. | `await this.RteObj.ExecuteCommand(CommandName.InsertText, "Inserted text");`|
| InsertImage | Insert an image to the current cursor position. | `await this.RteObj.ExecuteCommand(CommandName.InsertImage, new ImageCommandsArgs() { Url = "https://ej2.syncfusion.com/javascript/demos/src/rich-text-editor/images/RTEImage-Feather.png", CssClass = "rte-img" });`|

> Provided support to apply execute commands which do not require direct DOM access.

The following code block demonstrates the usage of the ExecuteCommand in Rich Text Editor.

```csharp

@using Syncfusion.Blazor.Buttons
@using Syncfusion.Blazor.RichTextEditor

<SfRichTextEditor @ref="@RteObj">
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
<SfButton Content="Bold" @onclick="@OnBoldCommand" />
<SfButton Content="InsertHTML" @onclick="@OnInsertHtmlCommand" />

@code {
    SfRichTextEditor RteObj;

    private async Task OnBoldCommand()
    {
        await this.RteObj.ExecuteCommand(CommandName.Bold);
    }

    private async Task OnInsertHtmlCommand()
    {
        await this.RteObj.ExecuteCommand(CommandName.InsertHTML, "<div>Syncfusion Rich Text Editor component</div>");
    }
}

```

The output will be as follows.

![Execute Command](./images/exec-command.png)
