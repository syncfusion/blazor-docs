---
title: "Customize progress using cssClass"
component: "ProgressButton"
description: "ProgressButton how to section, change text content and styles, hide spinner, customize progress."
---

# Customize progress using cssClass

You can customize the background filler UI using the [`cssClass`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.EJ2.RazorComponents~Syncfusion.EJ2.RazorComponents.SplitButtons.EjsProgressButton~CssClass.html) property.

* Adding `e-vertical` to `cssClass` shows vertical progress.
* Adding `e-progress-top` to `cssClass` shows progress at the top.

You can also show reverse progress by adding custom class to the [`cssClass`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.EJ2.RazorComponents~Syncfusion.EJ2.RazorComponents.SplitButtons.EjsProgressButton~CssClass.html) property.

`Index.razor`

```csharp


<ejs-progressbutton id="progress" content="Progress" enableProgress="true" cssClass="e-hide-spinner"></ejs-progressbutton>

<style>
    .e-reverse-progress .e-progress {
        right: 0;
        left: auto;
    }

    button {
        margin: 25px;
    }
</style>

  ```
