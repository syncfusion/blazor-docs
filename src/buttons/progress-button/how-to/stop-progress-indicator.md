---
title: "Stop Progress Indicator"
component: "Progress Button"
description: "This Section explains how to stop progress indicator"
---

# Stop Progress Indicator

You can stop the progress indicator using [`ProgressComplete`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.SplitButtons.SfProgressButton~ProgressComplete.html) method. In the following sample, the progress indicator is stopped by clicking the `Stop` button.

```csharp
@using Syncfusion.Blazor.SplitButtons
@using Syncfusion.Blazor.Buttons

<SfProgressButton Content="Spin Left" IsPrimary="true" @ref="ProgressBtnObj"></SfProgressButton>
<SfButton Onclick="clicked">Stop</SfButton>

@code {
    SfProgressButton ProgressBtnObj;
    private void clicked(){
    ProgressBtnObj.ProgressComplete();
  }
}
```

Output be like

![Progress Button Sample](./../images/pb-stop.png)