---
title: "Change the text content and styles of the ProgressButton during progress"
component: "ProgressButton"
description: "ProgressButton how to section, change text content and styles, hide spinner, customize progress."
---

# Change the text content and styles of the ProgressButton during progress

You can change the text content and styles of the ProgressButton during progress state by changing the text content and the [`cssClass`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.EJ2.RazorComponents~Syncfusion.EJ2.RazorComponents.SplitButtons.EjsProgressButton~CssClass.html) property at
the [`begin`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.EJ2.RazorComponents~Syncfusion.EJ2.RazorComponents.SplitButtons.EjsProgressButton~Begin.html) and [`end`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.EJ2.RazorComponents~Syncfusion.EJ2.RazorComponents.SplitButtons.EjsProgressButton~End.html) events.

`Index.razor`

```csharp

<EjsProgressButton Id="upload" ref="progressBtn" Content="Upload" EnableProgress="true" CssClass="e-hide-spinner" Duration="4000" Begin="@begin" End="@end"></EjsProgressButton>

@functions {

    EjsProgressButton progressBtn;


    private void begin(Syncfusion.EJ2.RazorComponents.SplitButtons.ProgressEventArgs args)
    {
        progressBtn.Content = "Uploading...";
        progressBtn.CssClass = "e-hide-spinner e-info";
        progressBtn.DataBind();

    }

    private void end(Syncfusion.EJ2.RazorComponents.SplitButtons.ProgressEventArgs args)
    {
        progressBtn.Content = "Success";
        progressBtn.CssClass = "e-hide-spinner e-success";
        progressBtn.DataBind();
        Thread.Sleep(500);
        progressBtn.Content = "Upload";
        progressBtn.CssClass = "e-hide-spinner";
        progressBtn.DataBind();

    }
}

  ```
