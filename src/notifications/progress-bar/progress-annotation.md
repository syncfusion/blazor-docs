---
title: "Annotation and Label | ASP.NET Core Blazor "
component: "ProgressBar"
description: "The Blazor ProgressBar component  supports the annotation and label."
---

# Annotation and Label

## Annotation

Annotations are used to mark the track area in the ProgressBar area with texts, shapes or images.

You can add annotations to the ProgressBar by using the annotations option. By using the content option of annotation object, you can specify either the id of the element or directly specify the element in the content that needs to be displayed in the ProgressBar area.

```csharp
<SfProgressBar Type="ProgressType.Circular" Value="60" Height="160px" Width="160px" EnableRtl="false"
                   TrackColor="#FFD939" Radius="100%" InnerRadius="190%" ProgressColor="white" TrackThickness="80"
                   ProgressThickness="10" CornerRadius="CornerType.Round" Minimum="0" Maximum="100">
        <ProgressBarAnnotations>
            <ProgressBarAnnotation Content="<div style='font-size:20px;font-weight:bold;color:#ffffff;fill:#ffffff'><span>60%</span></div>" />
        </ProgressBarAnnotations>
    </SfProgressBar>
```

![progress bar](images/annotation.png)

## Label

Progress Bar control shows the linear progress bar with different labels format by using  `textRender` event.

```csharp
<SfProgressBar Type="ProgressType.Linear" Value="50" Height="60" Width="90%" TrackColor="#F8C7D8"
               ShowProgressValue="true" ProgressColor="#E3165B" TrackThickness="24" CornerRadius="CornerType.Round"
               ProgressThickness="24" Minimum="0" Maximum="100">
</SfProgressBar>
```

![progress bar](images/label.png)