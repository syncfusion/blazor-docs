---
title: "Animation | ASP.NET Core Blazor "
component: "ProgressBar"
description: "ProgressBar support to animate the track."
---

# Animation

<!-- markdownlint-disable MD033 -->

Progress Bar support to animate the progress by using `Animation` property. Enable the animation by setting **Enable** property and also you can control the speed by using **Duration** property.

```csharp
<SfProgressBar Type="ProgressType.Linear" Value="90" Height="60" Width="90%" TrackColor="#FFFFFF"
               ShowProgressValue="true" ProgressColor="#2BB20E" TrackThickness="24" CornerRadius="CornerType.Round"
               ProgressThickness="24" Minimum="0" Maximum="100">
    <ProgressBarAnimation Enable="true" Duration="2000" Delay="0"></ProgressBarAnimation>
</SfProgressBar>
```

![progress bar](images/animation.png)