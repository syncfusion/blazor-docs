# Events

In this section, will illustrate the list of events in `Progress Bar` component, which will be
triggered for appropriate `Progress Bar` actions.

The events should be provided in the [`ProgressBarEvents`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.ProgressBarEvents.html).

## ValueChanged

[ValueChanged](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.ProgressBarEvents.html#Syncfusion_Blazor_ProgressBar_ProgressBarEvents_ValueChanged) event triggers, when the progress [`Value`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.SfProgressBar.html#Syncfusion_Blazor_ProgressBar_SfProgressBar_Value) is changed.

```csharp
<SfProgressBar Type="ProgressType.Linear" Value="100" Height="60" Minimum="0" Maximum="100">
    <ProgressBarEvents ValueChanged="@ValueHandler"></ProgressBarEvents>
</SfProgressBar>

@code{
    public void ValueHandler(ProgressValueEventArgs args)
    {
        // Here can customize the code
    }
}
```

## ProgressCompleted

[ProgressCompleted](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.ProgressBarEvents.html#Syncfusion_Blazor_ProgressBar_ProgressBarEvents_ProgressCompleted) event triggers, when the progress attains the [`Maximum`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.SfProgressBar.html#Syncfusion_Blazor_ProgressBar_SfProgressBar_Maximum) value property.

```csharp
<SfProgressBar Type="ProgressType.Linear" Value="100" Height="60" Minimum="0" Maximum="100">
    <ProgressBarEvents ProgressCompleted="@ProgressHandler"></ProgressBarEvents>
</SfProgressBar>

@code{
    public void ProgressHandler(ProgressValueEventArgs args)
    {
        // Here can customize the code
    }
}
```

## AnimationComplete

[AnimationComplete](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.ProgressBarEvents.html#Syncfusion_Blazor_ProgressBar_ProgressBarEvents_AnimationComplete) event triggers when animation of the progress [`Value`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.SfProgressBar.html#Syncfusion_Blazor_ProgressBar_SfProgressBar_Value) get completed.

```csharp
<SfProgressBar Type="ProgressType.Linear" Value="100" Height="60" Minimum="0" Maximum="100">
    <ProgressBarEvents AnimationComplete="@AnimationHandler"></ProgressBarEvents>
</SfProgressBar>

@code{
    public void AnimationHandler(ProgressValueEventArgs args)
    {
        // Here can customize the code
    }
}
```

## AnnotationRender

[AnnotationRender](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.ProgressBarEvents.html#Syncfusion_Blazor_ProgressBar_ProgressBarEvents_AnnotationRender) event triggers, before the `Progress Bar` annotaion rendered.

```csharp
<SfProgressBar Type="ProgressType.Linear" Value="100" Height="60" Minimum="0" Maximum="100">
    <ProgressBarEvents AnnotationRender="@AnnotationHandler"></ProgressBarEvents>
</SfProgressBar>

@code{
    public void AnnotationHandler(AnnotationRenderEventArgs args)
    {
        // Here can customize the code
    }
}
```

## TextRender

[TextRender](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.ProgressBarEvents.html#Syncfusion_Blazor_ProgressBar_ProgressBarEvents_TextRender) event triggers, before the `Progress Bar` text rendered.

```csharp
<SfProgressBar Type="ProgressType.Linear" Value="100" Height="60" Minimum="0" Maximum="100">
    <ProgressBarEvents TextRender="@TextRenderHandler"></ProgressBarEvents>
</SfProgressBar>

@code{
    public void TextRenderHandler(TextRenderEventArgs args)
    {
        // Here can customize the code
    }
}
```

## Loaded

`Loaded` event triggers, after the `Progress Bar` component rendered.

```csharp
<SfProgressBar Type="ProgressType.Linear" Value="100" Height="60" Minimum="0" Maximum="100">
    <ProgressBarEvents Loaded="@LoadedHandler"></ProgressBarEvents>
</SfProgressBar>

@code{
    public void LoadedHandler(System.EventArgs args)
    {
        // Here you can customize your code
    }
}
```