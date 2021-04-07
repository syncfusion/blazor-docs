# States

Visualize progress in different states.

## Determinate

<!-- markdownlint-disable MD033 -->

This is the default state and can use it, when the progress estimation is known.

```csharp
<SfProgressBar Type="ProgressType.Linear" Value="100" Height="60" Minimum="0" Maximum="100">
</SfProgressBar>
```

![progress bar](images/determinate.png)

## Indeterminate

By enabling the [`IsIndeterminate`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.SfProgressBar.html#Syncfusion_Blazor_ProgressBar_SfProgressBar_IsIndeterminate) property to **true**, the state of the progress bar can be changed to indeterminate when the progress cannot be estimated or is not being calculated. It can be combined with determinate mode to know that the application is estimating progress before the actual progress starts.

```csharp
<SfProgressBar Type="ProgressType.Linear" Value="20" Height="60" IsIndeterminate="true" Minimum="0" Maximum="100">
</SfProgressBar>
```

![progress bar](images/indeterminate.png)

## Buffer

<!-- markdownlint-disable MD033 -->
By setting the [`SecondaryProgress`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.SfProgressBar.html#Syncfusion_Blazor_ProgressBar_SfProgressBar_SecondaryProgress) property value, can make to visible the secondary progress indicator, which the primary progress depends on the secondary progress. This will allow users to visualize both primary and secondary progress simultaneously.

```csharp
<SfProgressBar Type="ProgressType.Linear" Value="40" Height="60" SecondaryProgress="60" Minimum="0" Maximum="100">
</SfProgressBar>
```

![progress bar](images/buffer.png)

## Active

Can use a active animate indicator for estimated progress by setting the [`IsActive`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.SfProgressBar.html#Syncfusion_Blazor_ProgressBar_SfProgressBar_IsActive) property to **true** and [`Enable`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.ProgressBarAnimation.html#Syncfusion_Blazor_ProgressBar_ProgressBarAnimation_Enable) the animation to **true** in [`ProgressBarAnimation`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.ProgressBarAnimation.html).

```csharp
<SfProgressBar Type="ProgressType.Linear" IsActive="true" Value="40" Height="60" Minimum="0" Maximum="100">
    <ProgressBarAnimation Enable="true"></ProgressBarAnimation>
</SfProgressBar>
```

![progress bar](images/active.png)

## Striped

Can use a striped visual indicator for estimated progress by setting the [`IsStriped`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.SfProgressBar.html#Syncfusion_Blazor_ProgressBar_SfProgressBar_IsStriped) property to **true**.

>[`IsStriped`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.SfProgressBar.html#Syncfusion_Blazor_ProgressBar_SfProgressBar_IsStriped) property is only applicable for [`Linear`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.ProgressType.html#Syncfusion_Blazor_ProgressBar_ProgressType_Linear) [`Type`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.ProgressType.html) of `Progress Bar`.

```csharp
<SfProgressBar Type="ProgressType.Linear" IsStriped="true" Value="40" Height="60" Minimum="0" Maximum="100">
</SfProgressBar>
```

![progress bar](images/striped.png)