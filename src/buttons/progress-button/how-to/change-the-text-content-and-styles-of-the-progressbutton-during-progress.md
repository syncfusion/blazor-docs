---
title: "Change the text content and styles of the Progress Button during progress"
component: "Progress Button"
description: "Progress Button how to section, change text content and styles, hide spinner, customize progress."
---

# Change the text content and styles of the Progress Button during progress

You can change the text content and styles of the Progress Button during progress state by changing the text content and the [`CssClass`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.SplitButtons.SfProgressButton~CssClass.html) property at
the [`OnBegin`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.SplitButtons.ProgressButtonEvents~OnBegin.html) and [`OnEnd`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.SplitButtons.ProgressButtonEvents~OnEnd.html) events.

```csharp

@using Syncfusion.Blazor.SplitButtons

<SfProgressButton Content="@Content" EnableProgress="true" CssClass="@CssClass" Duration="4000">
    <ProgressButtonEvents OnBegin="Begin" OnEnd="End"></ProgressButtonEvents>
</SfProgressButton>

@code {
    public string Content = "Upload";
    public string CssClass = "e-hide-spinner";
    public void Begin(ProgressEventArgs args)
    {
        this.Content = "Uploading...";
        this.CssClass = "e-hide-spinner e-info";
    }
    public void End(ProgressEventArgs args)
    {
        this.Content = "Success";
        this.CssClass = "e-hide-spinner e-success";
    }
}

```

Output be like

![Progress Button Sample](./../images/pb-text.png)