---
title: "Set the disabled state"
component: "Split Button"
description: "Split Button how to section, group popup items using list view component, dialog open on popup item click."
---

# Set the disabled state

Split Button component can be enabled or disabled by disabled property. To disable Split Button component, set the [`Disabled`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.SplitButtons.SfSplitButton~Disabled.html) property as true.

The following example illustrates how to set the disable state in Split Button component.

```csharp
@using Syncfusion.Blazor.SplitButtons

<SfSplitButton Content="Paste" Disabled="true">
    <SplitButtonItems>
        <SplitButtonItem Text="Cut" ></SplitButtonItem>
        <SplitButtonItem Text="Copy" ></SplitButtonItem>
        <SplitButtonItem Text="Paste"></SplitButtonItem>
    </SplitButtonItems>
</SfSplitButton>
  
```

Output be like

![Split Button Sample](./../images/sb-disabled.png)