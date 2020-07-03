---
title: "Create right-to-left Split Button"
component: "Split Button"
description: "Split Button how to section, group popup items using list view component, dialog open on popup item click."
---

# Create right-to-left Split Button

Split Button component has RTL support. This can be achieved by setting [`EnableRtl`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.SplitButtons.SfSplitButton~EnableRtl.html) as `true`.

The following example illustrates how to enable right-to-left support in Split Button component.

```csharp
@using Syncfusion.Blazor.SplitButtons

<SfSplitButton Content="Paste" IconCss="e-icons e-paste" EnableRtl="true">
    <SplitButtonItems>
        <SplitButtonItem Text="Cut" ></SplitButtonItem>
        <SplitButtonItem Text="Copy" ></SplitButtonItem>
        <SplitButtonItem Text="Paste"></SplitButtonItem>
    </SplitButtonItems>
</SfSplitButton>

<style>
    .e-paste::before {
        content: '\e501';
    }

    .e-cut::before {
        content: '\e604';
    }

    .e-copy::before {
        content: '\e60d';
    }
</style>
  
```

Output be like

![Split Button Sample](./../images/sb-rtl.png)