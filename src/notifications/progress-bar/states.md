---
title: "States in Blazor Progress Bar component | Syncfusion"

component: "Progress Bar"

description: "Learn here all about States of Syncfusion Progress Bar (SfProgressBar) component and more."
---

# States in Blazor Progress Bar (SfProgressBar)

Visualize the progress in different states.

## Determinate

This is the default progress state, which can be used when the estimated progress is known.

```csharp
@using Syncfusion.Blazor.ProgressBar

<SfProgressBar Type="ProgressType.Linear" Value="100" Height="60" Minimum="0" Maximum="100">
</SfProgressBar>
```

![progress bar](images/determinate.png)

## Indeterminate

The state of the progress bar can be used to indeterminate mode by setting the [`IsIndeterminate`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.SfProgressBar.html#Syncfusion_Blazor_ProgressBar_SfProgressBar_IsIndeterminate) property to **true** when the progress cannot be estimated or calculated. It can be combined with determinate mode to know the estimating progress before the actual progress starts.

```csharp
@using Syncfusion.Blazor.ProgressBar

<SfProgressBar Type="ProgressType.Linear" Value="20" Height="60" IsIndeterminate="true" Minimum="0" Maximum="100">
</SfProgressBar>
```

![progress bar](images/indeterminate.png)

## Buffer

Setting the [`SecondaryProgress`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.SfProgressBar.html#Syncfusion_Blazor_ProgressBar_SfProgressBar_SecondaryProgress) property value to **true** will make the secondary progress indicator visible, and the primary progress will be dependent on it. Users will be able to see both primary and secondary progress at the same time.

```csharp
@using Syncfusion.Blazor.ProgressBar

<SfProgressBar Type="ProgressType.Linear" Value="40" Height="60" SecondaryProgress="60" Minimum="0" Maximum="100">
</SfProgressBar>
```

![progress bar](images/buffer.png)

## Active

The active animate indicator for estimated progress can be enabled by setting the [`IsActive`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.SfProgressBar.html#Syncfusion_Blazor_ProgressBar_SfProgressBar_IsActive) property to **true** and [`Enable`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.ProgressBarAnimation.html#Syncfusion_Blazor_ProgressBar_ProgressBarAnimation_Enable) the animation to **true** in [`ProgressBarAnimation`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.ProgressBarAnimation.html).

```csharp
@using Syncfusion.Blazor.ProgressBar

<SfProgressBar Type="ProgressType.Linear" IsActive="true" Value="40" Height="60" Minimum="0" Maximum="100">
    <ProgressBarAnimation Enable="true"></ProgressBarAnimation>
</SfProgressBar>
```

![progress bar](images/active.png)

## Striped

Striped visual indicator for estimated progress can be enabled by setting the [`IsStriped`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.SfProgressBar.html#Syncfusion_Blazor_ProgressBar_SfProgressBar_IsStriped) property to **true**.

>[`IsStriped`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.SfProgressBar.html#Syncfusion_Blazor_ProgressBar_SfProgressBar_IsStriped) property is only applicable for [`Linear`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.ProgressType.html#Syncfusion_Blazor_ProgressBar_ProgressType_Linear) [`Type`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.ProgressType.html) of `Progress Bar`.

```csharp
@using Syncfusion.Blazor.ProgressBar

<SfProgressBar Type="ProgressType.Linear" IsStriped="true" Value="40" Height="60" Minimum="0" Maximum="100">
</SfProgressBar>
```

![progress bar](images/striped.png)
