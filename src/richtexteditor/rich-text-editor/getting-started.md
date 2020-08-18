---
title: "Blazor Rich Text Editor | Get started with use case example"
component: "Rich Text Editor"
description: "This section describes the step-by-step process to get started with the Blazor Rich Text Editor based on real-time use case application in Visual Studio 2019."
---

<!-- markdownlint-disable MD024 -->

# Getting Started

This section briefly explains how to include a Rich Text Editor component in your Blazor Server-side application. You can refer [Getting Started with Syncfusion Blazor for Server-Side in Visual Studio 2019 page](../getting-started/server-side-blazor/) for the introduction and configuring the common specifications.

To get start quickly with Blazor Rich Text Editor components, you can check on this video:
`youtube:NvauE3z7W0k`

## Importing Syncfusion Blazor component in the application

* Install `Syncfusion.Blazor` NuGet package to the application by using the `NuGet Package Manager`.

> Please ensure to check the `Include prerelease` option for our Beta release.

* You can add the client-side resources through CDN or from NuGet package in the `<head>` element of the **~/Pages/_Host.cshtml** page.

```html

<head>
    <link href="_content/Syncfusion.Blazor/styles/bootstrap4.css" rel="stylesheet" />
    @*<link href="https://cdn.syncfusion.com/blazor/{:version:}/styles/bootstrap4.css" rel="stylesheet" />*@
</head>

```

> For Internet Explorer 11 kindly refer the polyfills. Refer the [documentation](../../common/how-to/render-blazor-server-app-in-ie/) for more information.

```html

<head>
    <link href="_content/Syncfusion.Blazor/styles/bootstrap4.css" rel="stylesheet" />
    <script src="https://github.com/Daddoon/Blazor.Polyfill/releases/download/3.0.1/blazor.polyfill.min.js"></script>
</head>

```

## Adding component package to the application

Open **~/_Imports.razor** file and import the `Syncfusion.Blazor.RichTextEditor` package.

```csharp

@using Syncfusion.Blazor.RichTextEditor

```

## Add SyncfusionBlazor service in Startup.cs

Open the **Startup.cs** file and add services required by Syncfusion components using `services.AddSyncfusionBlazor()` method. Add this method in the ConfigureServices function as follows.

```csharp

using Syncfusion.Blazor;
namespace BlazorApplication
{
    public class Startup
    {
        ....
        ....
        public void ConfigureServices(IServiceCollection services)
        {
            ....
            ....
            services.AddSyncfusionBlazor();
        }
    }
}

```

## Add Rich Text Editor component

To initialize the Rich Text Editor component, add the below code to your **Index.razor** view page which is present under **~/Pages** folder.

The following code explains how to initialize a simple Rich Text Editor in Razor page.

```csharp

@using Syncfusion.Blazor.RichTextEditor

<SfRichTextEditor>
    <p>Rich Text Editor allows to insert images from online source as well as local computer where you want to insert the image in your content.</p>
    <p><b>Get started Quick Toolbar to click on the image</b></p>
    <p>It is possible to add custom style on the selected image inside the Rich Text Editor through quick toolbar.</p>
</SfRichTextEditor>

```

## Run the application

After successful compilation of your application, run the application.

The output will be as follows.

![output](./images/rte-output.png)

## Configure the Toolbar

Configure the toolbar with the tools using `Items` field of the `RichTextEditorToolbarSettings` property as your application requires.

```csharp

@using Syncfusion.Blazor.RichTextEditor

<SfRichTextEditor>
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
        <li><p> Allows preview of modified content before saving it.</p></li>
    </ul>
</SfRichTextEditor>

@code {
    public object[] Tools = new object[]{
        "Bold", "Italic", "Underline", "SubScript", "SuperScript", "StrikeThrough",
        "FontName", "FontSize", "FontColor", "BackgroundColor",
        "LowerCase", "UpperCase", "|",
        "Formats", "Alignments", "OrderedList", "UnorderedList",
        "Outdent", "Indent", "|", "CreateTable",
        "CreateLink", "Image", "|", "ClearFormat", "Print",
        "SourceCode", "FullScreen", "|", "Undo", "Redo"
    };
}

```

The output will be as follows.

![Toolbar](./images/configure-toolbar.png)

## Insert images and links

The `Image` module inserts an image into Rich Text Editor's content area, and the `Link` module links external resources such as website URLs to the selected text in the Rich Text Editor's content respectively.

The link inject module adds a link icon to the toolbar and the image inject module adds an image icon to the toolbar.

Specifies the items to be rendered in quick toolbar based on the target elements such as image, link and text element. The quick toolbar opens to customize the element by clicking the target element.

```csharp

@using Syncfusion.Blazor.RichTextEditor

<SfRichTextEditor>
    <RichTextEditorQuickToolbarSettings Image="@Image" Link="@Link"></RichTextEditorQuickToolbarSettings>
    <RichTextEditorToolbarSettings Items="@Tools"></RichTextEditorToolbarSettings>
    <p>Rich Text Editor allows to insert images from online source as well as local computer where you want to insert the image in your content.</p>
    <p><b>Get started Quick Toolbar to click on the image</b></p>
    <p>It is possible to add custom style on the selected image inside the Rich Text Editor through quick toolbar.</p>
    <img alt='Logo' style='width: 300px; height: 300px; transform: rotate(0deg);' src='https://blazor.syncfusion.com/demos/images/RichTextEditor/RTEImage-Feather.png' />
</SfRichTextEditor>

@code {
    public object[] Tools = new object[] {
        "Bold", "Italic", "Underline", "|",
        "Formats", "Alignments", "|", "CreateLink", "Image", "|","SourceCode", "|", "Undo", "Redo"
    };

    public object[] Image = new object[] {
        "Replace", "Align", "Caption", "Remove", "InsertLink", "OpenImageLink", "-",
        "EditImageLink", "RemoveImageLink", "Display", "AltText", "Dimension"
    };

    public object[] Link = new object[] {
        "Open", "Edit", "UnLink"
    };
}

```

The output will be as follows.

![Image](./images/rte-image.png)

## Retrieve the formatted content

To retrieve the editor contents, use the `Value` property of Rich Text Editor. Or, you can use the public method, `GetHtml` to retrieve the Rich Text Editor content. To fetch the Rich Text Editor's text content, use `GetText` method of Rich Text Editor.

```csharp

@using Syncfusion.Blazor.RichTextEditor
@using Syncfusion.Blazor.Buttons

<SfButton @onclick="@GetValue">Get Value</SfButton>
<SfButton @onclick="@GetHtml">Get Html</SfButton>
<SfButton @onclick="@GetText">Get Text</SfButton>

<SfRichTextEditor @ref="RteObj" Value="@RteValue">
    <RichTextEditorToolbarSettings Items="@Tools"></RichTextEditorToolbarSettings>
</SfRichTextEditor>

@code {
    SfRichTextEditor RteObj;

    public string RteValue = @"<p>Rich Text Editor allows to insert images from online source as well as local computer where you want to insert the image in your content.</p><p><b>Get started Quick Toolbar to click on the image</b></p><p>It is possible to add custom style on the selected image inside the Rich Text Editor through quick toolbar.</p><img alt='Logo' style='width: 300px; height: 300px; transform: rotate(0deg);' src='https://blazor.syncfusion.com/demos/images/RichTextEditor/RTEImage-Feather.png' />";
    public object[] Tools = new object[] {
        "Bold", "Italic", "Underline", "|",
        "Formats", "Alignments", "|", "CreateLink", "Image", "|","SourceCode", "|", "Undo", "Redo"
    };
    public void GetValue()
    {
        string Value = this.RteValue;
    }
    public async void GetHtml()
    {
        string GetHtml = await this.RteObj.GetHtml();
    }
    public async void GetText()
    {
        string GetText = await this.RteObj.GetText();
    }
}

```

## See Also

* [Getting Started with Syncfusion Blazor for client-side in .NET Core CLI](../getting-started/blazor-webassembly-dotnet-cli/)

* [Getting Started with Syncfusion Blazor for server-side in Visual Studio 2019](../getting-started/server-side-blazor/)

* [Getting Started with Syncfusion Blazor for server-side in .NET Core CLI](../getting-started/server-side-blazor-dotnet-cli/)