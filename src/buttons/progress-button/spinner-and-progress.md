---
title: "ProgressButton Spinner and Progress"
component: "ProgressButton"
description: "ProgressButton allows the user to change size & position of the spinner, customize spinner using template and to change the progress."
---

<!-- markdownlint-disable MD002 MD022 -->
## Spinner

### Change spinner position

Spinner position can be changed by modifying the `position` property of [`spinSettings`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.EJ2.RazorComponents~Syncfusion.EJ2.RazorComponents.SplitButtons.EjsProgressButton~SpinSettings.html). By default, the spinner is positioned at the left of the ProgressButton. You can position it at the `left`, `right`, `top`, `bottom`, or `center` of the text content.

### Change spinner size

Spinner size can be changed by modifying the `width` property of [`spinSettings`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.EJ2.RazorComponents~Syncfusion.EJ2.RazorComponents.SplitButtons.EjsProgressButton~SpinSettings.html). In this demo, the `width` is set to `20` to change the spinner size.

### Spinner template

You can use custom spinner by specifying the `template` property of [`spinSettings`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.EJ2.RazorComponents~Syncfusion.EJ2.RazorComponents.SplitButtons.EjsProgressButton~SpinSettings.html) with custom styles.

The following sample demonstrates the above functionalities of the spinner.

`Index.razor`

```csharp

<h2>Button</h2>

<EjsProgressButton ID="submit" Content="Submit" SpinSettings="@spinSettings"></EjsProgressButton>

@functions {

      ProgressButtonSpinSettings spinSettings = new ProgressButtonSpinSettings() { Position = SpinPosition.Right, Width = "20", Template = "<div class='template'></div>" };
}

  ```

  `_Host.cshtml`

   ```html

<style>
    @@keyframes custom-rolling {
        0% {
            -webkit-transform: rotate(0deg);
            transform: rotate(0deg);
        }

        100% {
            -webkit-transform: rotate(360deg);
            transform: rotate(360deg);
        }
    }

    .template {
        border: 2px solid green;
        border-style: dotted;
        border-radius: 50%;
        border-top-color: transparent;
        border-bottom-color: transparent;
        height: 16px;
        width: 16px;
    }

    .template {
        -webkit-animation: custom-rolling 1.3s linear infinite;
        animation: custom-rolling 1.3s linear infinite;
    }
</style>

  ```

<!-- markdownlint-disable MD025 MD022 -->
## Progress

### Content animation

The [`content`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.EJ2.RazorComponents~Syncfusion.EJ2.RazorComponents.SplitButtons.EjsProgressButton~Content.html) of the ProgressButton can be animated during progress using the `effect` property
of [`animationSettings`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.EJ2.RazorComponents~Syncfusion.EJ2.RazorComponents.SplitButtons.EjsProgressButton~AnimationSettings.html). You can also set custom duration and timing function using the `duration` and `easing` properties. The possible `effect` values are `None`, `SlideLeft`, `SlideRight`, `SlideUp`, `SlideDown`, `ZoomIn`, and `ZoomOut`.

`Index.razor`

```csharp

<EjsProgressButton ID="slideleft" Content="Slide Left" EnableProgress="true" AnimationSettings="@animationSettings" SpinSettings="@spinSettings"></EjsProgressButton>

@functions {

      ProgressButtonSpinSettings spinSettings = new ProgressButtonSpinSettings() { Position = SpinPosition.Left };
     ProgressButtonAnimationSettings animationSettings = new ProgressButtonAnimationSettings()
            {
                Effect = AnimationEffect.SlideRight,
                Duration = 500,
                Easing = "linear",
            };

}
  ```

### Start and stop methods

You can pause and resume the progress using the `stop` and `start` methods, respectively. In this demo, clicking the ProgressButton will pause and resume the progress.

`Index.razor`

```csharp

<EjsProgressButton ID="download" ref="progressBtn" Content="Download" EnableProgress="true" IconCss="e-btn-sb-icon e-download" Duration="4000" End="@end" CssClass="e-hide-spinner" onclick="@clickHandler"></EjsProgressButton>

@functions {

    EjsProgressButton progressBtn;
    public string content = "Pause";
    public string iconCss = "e-btn-sb-icon e-pause";
    private void clickHandler(UIMouseEventArgs args)
    {
        if (progressBtn.Content == "Download") {
            progressBtn.Content = this.content;
            progressBtn.IconCss = this.iconCss;
            progressBtn.DataBind();
        }
        // clicking on ProgressButton will stop the progress when the text Content is "Pause"
        else if (progressBtn.Content == "Pause") {
            progressBtn.Content = "Resume";
            progressBtn.IconCss = "e-btn-sb-icon e-play";
            progressBtn.DataBind();
            progressBtn.Stop();
        }
        // clicking on ProgressButton will start the progress when the text Content is "Resume"
        else if (progressBtn.Content == "Resume") {
            progressBtn.Content = "Pause";
            progressBtn.IconCss = "e-btn-sb-icon e-pause";
            progressBtn.DataBind();
            progressBtn.Start();
        }

    }

    private void end(ProgressEventArgs args)
    {
        progressBtn.Content = "Download";
        progressBtn.IconCss = "e-icons e-download";
        progressBtn.DataBind();
    }

}

  ```

  `_Host.cshtml`

   ```html

<style>
    @@font-face {
        font-family: 'btn-icon';
        src: url(data:application/x-font-ttf;charset=utf-8;base64,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) format('truetype');
        font-weight: normal;
        font-style: normal;
    }

    .e-btn-sb-icon {
        font-family: 'btn-icon' !important;
        speak: none;
        font-size: 55px;
        font-style: normal;
        font-weight: normal;
        font-variant: normal;
        text-transform: none;
        line-height: 1;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
    }

    .e-download::before {
        content: '\e706';
    }

    .e-play::before {
        content: '\e700';
    }

    .e-pause::before {
        content: '\e701';
    }
</style>

  ```

## See Also

* [How to hide spinner](./how-to/hide-spinner)
* [Customize ProgressButton using cssClass](how-to/customize-progress-using-cssclass)