---
title: "Animation in Blazor Progress Bar component | Syncfusion"

component: "Progress Bar"

description: "Learn here all about Animation of Syncfusion Progress Bar (SfProgressBar) component and more."
---

# Animation in Blazor Progress Bar (SfProgressBar)

Progress Bar supports to animate the progress. It can be enabled by setting the [`Enable`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.ProgressBarAnimation.html#Syncfusion_Blazor_ProgressBar_ProgressBarAnimation_Enable) property to **true** in [`ProgressBarAnimation`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.ProgressBarAnimation.html) and speed and delay can be controlled using [`Duration`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.ProgressBarAnimation.html#Syncfusion_Blazor_ProgressBar_ProgressBarAnimation_Duration) and [`Delay`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.ProgressBarAnimation.html#Syncfusion_Blazor_ProgressBar_ProgressBarAnimation_Delay) properties.

```csharp
@using Syncfusion.Blazor.ProgressBar

<SfProgressBar Type="ProgressType.Linear" Value="90" Height="60" Width="90%" TrackColor="#FFFFFF"
               ShowProgressValue="true" ProgressColor="#2BB20E" TrackThickness="24" CornerRadius="CornerType.Round"
               ProgressThickness="24" Minimum="0" Maximum="100">
    <ProgressBarAnimation Enable="true" Duration="2000" Delay="0"></ProgressBarAnimation>
</SfProgressBar>
```

![Progress Bar with animation](images/animation.png)
