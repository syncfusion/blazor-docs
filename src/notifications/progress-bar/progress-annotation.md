# Annotation and Label

## Annotation

Annotations are used to mark the track area in the `Progress Bar` area with text, shape or images.

Annotation of the `Progress Bar` to be added by using the [`ProgressBarAnnotations`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.ProgressBarAnnotations.html) collections and can specify elements by using the `ContentTemplate` property in [`ProgressBarAnnotation`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.PogressBarAnnotation.html), that needs to be displayed in the `Progress Bar` area.

```csharp
<SfProgressBar Type="ProgressType.Circular" Value="60" Height="160px" Width="160px" EnableRtl="false"
               TrackColor="#FFD939" Radius="100%" InnerRadius="190%" ProgressColor="white" TrackThickness="80"
               ProgressThickness="10" CornerRadius="CornerType.Round" Minimum="0" Maximum="100">
    <ProgressBarAnnotations>
        <ProgressBarAnnotation>
            <ContentTemplate>
                <div style="font-size:20px;font-weight:bold;color:#ffffff;fill:#ffffff">
                    <span>
                        60%
                    </span>
                </div>
            </ContentTemplate>
        </ProgressBarAnnotation>
    </ProgressBarAnnotations>
</SfProgressBar>
```

![progress bar](images/annotation.png)

## Label

Setting the [`ShowProgressValue`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.SfProgressBar.html#Syncfusion_Blazor_ProgressBar_SfProgressBar_ShowProgressValue) property to **true**, by default progress text will be rendered in  percentage format and customize to different type label formats by using the [`Text`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.TextRenderEventArgs.html#Syncfusion_Blazor_ProgressBar_TextRenderEventArgs_Text) argument in [`TextRender`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.ProgressBar.ProgressBarEvents.html#Syncfusion_Blazor_ProgressBar_ProgressBarEvents_TextRender) event.

```csharp
<SfProgressBar Type="ProgressType.Linear" Value="50" Height="60" Width="90%" TrackColor="#F8C7D8"
               ShowProgressValue="true" ProgressColor="#E3165B" TrackThickness="24" CornerRadius="CornerType.Round"
               ProgressThickness="24" Minimum="0" Maximum="100">
    <ProgressBarEvents TextRender="TextHandler"></ProgressBarEvents>
</SfProgressBar>

@code{
    public void TextHandler(TextRenderEventArgs args)
    {
        args.Text = args.Text; // can customize the text format
    }
}
```

![progress bar](images/label.png)