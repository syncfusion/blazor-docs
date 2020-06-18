---
title: "Right-To-Left"
component: "Button"
description: "Button how to section, block button, repeat button, tooltip for Button, customization of button appearance, input and anchor elements."
---

# Right-To-Left

Button component has RTL support. This can be achieved by setting [`enableRtl`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.EJ2.RazorComponents~Syncfusion.EJ2.RazorComponents.Buttons.EjsCheckBox~EnableRtl.html) as true.

The following example illustrates how to enable right-to-left support in Button component.

`Index.razor`

```csharp

  <EjsButton ID="rtl" Content="Settings" IconCss="e-btn-icons e-setting-icon" EnableRtl="true"></EjsButton>

  ```

  `_Host.cshtml`

  ```html

    <style>
        @@font-face {
            font-family: 'settings';
            src: url(data:application/x-font-ttf;charset=utf-8;base64,AAEAAAAKAIAAAwAgT1MvMj0gSRsAAAEoAAAAVmNtYXDnEOdVAAABiAAAADZnbHlm7/npHAAAAcgAAAEwaGVhZBKtDIMAAADQAAAANmhoZWEHmQNrAAAArAAAACRobXR4B+gAAAAAAYAAAAAIbG9jYQCYAAAAAAHAAAAABm1heHABDgB0AAABCAAAACBuYW1lxmFdywAAAvgAAAIxcG9zdDwSCicAAAUsAAAANwABAAADUv9qAFoEAAAA//4D6gABAAAAAAAAAAAAAAAAAAAAAgABAAAAAQAAMLNyX18PPPUACwPoAAAAANfSY9oAAAAA19Jj2gAAAAAD6gPqAAAACAACAAAAAAAAAAEAAAACAGgAAgAAAAAAAgAAAAoACgAAAP8AAAAAAAAAAQP0AZAABQAAAnoCvAAAAIwCegK8AAAB4AAxAQIAAAIABQMAAAAAAAAAAAAAAAAAAAAAAAAAAAAAUGZFZABA5wDnAANS/2oAWgPqAJYAAAABAAAAAAAABAAAAAPoAAAAAAACAAAAAwAAABQAAwABAAAAFAAEACIAAAAEAAQAAQAA5wD//wAA5wD//wAAAAEABAAAAAEAAAAAAAAAmAAAAAIAAAAAA+oD6gALAGcAAAEOAQcuASc+ATceAQEVBgcnJiIPAQYUHwEOAQcjIgYdAR4BOwEWFwcGFB8BFjI/AR4BFxUeATsBPgE9ATY3FxYyPwE2NC8BPgE3MzI2PQE0JisBJic3NjQvASYiDwEuASc1LgEnIw4BAr4CcVVUcQMDcVRVcf7pOTRbBRQGUQYGWhAYB30LDgEPCX0OIVoHB1EFFQVbGTYeAQ4KcQsOOTRbBRQGUQYGWhAXB34LDQ8Jfg4gWgcHUQUVBVsZNh4BDgpxCQ8B9lRxAwNxVFVxAgJxAYd+DiBaBgZRBRUFWBk2Hg8KcQsOOTRbBxQHUQYGWhAYB30LDgEPCX0OIVoGBk4FFQVbGTYeDwpxCw06NFoIEwhRBgZaEBgHfQsNAQENAAAAABIA3gABAAAAAAAAAAEAAAABAAAAAAABAAgAAQABAAAAAAACAAcACQABAAAAAAADAAgAEAABAAAAAAAEAAgAGAABAAAAAAAFAAsAIAABAAAAAAAGAAgAKwABAAAAAAAKACwAMwABAAAAAAALABIAXwADAAEECQAAAAIAcQADAAEECQABABAAcwADAAEECQACAA4AgwADAAEECQADABAAkQADAAEECQAEABAAoQADAAEECQAFABYAsQADAAEECQAGABAAxwADAAEECQAKAFgA1wADAAEECQALACQBLyBzZXR0aW5nc1JlZ3VsYXJzZXR0aW5nc3NldHRpbmdzVmVyc2lvbiAxLjBzZXR0aW5nc0ZvbnQgZ2VuZXJhdGVkIHVzaW5nIFN5bmNmdXNpb24gTWV0cm8gU3R1ZGlvd3d3LnN5bmNmdXNpb24uY29tACAAcwBlAHQAdABpAG4AZwBzAFIAZQBnAHUAbABhAHIAcwBlAHQAdABpAG4AZwBzAHMAZQB0AHQAaQBuAGcAcwBWAGUAcgBzAGkAbwBuACAAMQAuADAAcwBlAHQAdABpAG4AZwBzAEYAbwBuAHQAIABnAGUAbgBlAHIAYQB0AGUAZAAgAHUAcwBpAG4AZwAgAFMAeQBuAGMAZgB1AHMAaQBvAG4AIABNAGUAdAByAG8AIABTAHQAdQBkAGkAbwB3AHcAdwAuAHMAeQBuAGMAZgB1AHMAaQBvAG4ALgBjAG8AbQAAAAACAAAAAAAAAAoAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAIBAgEDAA1zZXR0aW5ncy0tLTExAAAA) format('truetype');
            font-weight: normal;
            font-style: normal;
        }

        .e-btn-icons {
            font-family: 'settings' !important;
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

        button {
            margin: 25px 5px 20px 20px;
        }

        .e-setting-icon::before {
            content: '\e700';
        }
    </style>

  ```  