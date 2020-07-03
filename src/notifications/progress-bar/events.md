---
title: "Events"
component: "ProgressBar"
description: "Visualize progress events"
---

# Events

In this section, we have provided the list of events of Progress bar component which will be
triggered for appropriate progress bar actions.

The events should be provided to the Progress bar using `ProgressBarEvents` component.

The following are the number of events supported for Progress bar component.

* [ValueChanged](events/#valuechanged)
* [ProgressCompleted](events/#progresscompleted)

## ValueChanged

`ValueChanged` event is triggered when the progress value is changed.

```csharp
@using Syncfusion.Blazor.ProgressBar

<SfProgressBar Type="ProgressType.Linear" Value="100" Height="60" Minimum="0" Maximum="100">
    <ProgressBarEvents ValueChanged="@ValueHandler"></ProgressBarEvents>
</SfProgressBar>
@code{
    public void ValueHandler(IProgressValueEventArgs args)
    {
        // Here you can customize your code
    }
}
```

## ProgressCompleted

`ProgressCompleted` is triggered when the progress attains the Maximum value.

```csharp
@using Syncfusion.Blazor.ProgressBar

<SfProgressBar Type="ProgressType.Linear" Value="100" Height="60" Minimum="0" Maximum="100">
    <ProgressBarEvents ProgressCompleted="@ProgressHandler"></ProgressBarEvents>
</SfProgressBar>
@code{
    public void ProgressHandler(IProgressValueEventArgs args)
    {
        // Here you can customize your code
    }
}
```