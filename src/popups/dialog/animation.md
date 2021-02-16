# Animation

The Dialog can be animated during the open and close actions. Also, users can
customize animation's `Delay`, `Duration` and `Effect` by using the `DialogAnimationSettings` property.

<!-- markdownlint-disable MD033 -->
<table>
<tr>
<td>
delay</td><td>
The Dialog animation will start with the mentioned delay</td></tr>
<tr>
<td>
duration</td><td>
Specifies the animation duration to complete with one animation cycle</td></tr>
<tr>
<td>
effect</td><td>
Specifies the animation effects of Dialog open and close actions effect.
<br /><br />
List of supported animation effects:
<br />
'Fade' | 'FadeZoom' | 'FlipLeftDown' | 'FlipLeftUp' | 'FlipRightDown' | 'FlipRightUp' | 'FlipXDown' |
'FlipXUp' | 'FlipYLeft' | 'FlipYRight' | 'SlideBottom' | 'SlideLeft' | 'SlideRight' | 'SlideTop' |
'Zoom'| 'None'
<br /><br />
If the user sets 'Fade' effect, then the Dialog will open with 'FadeIn' effect and close with 'FadeOut' effect
</td></tr>
</table>

In the following sample, `Zoom` effect is enabled. So, The Dialog will open with `ZoomIn`
and close with `ZoomOut` effects.

```csharp

@using Syncfusion.Blazor.Popups
@using Syncfusion.Blazor.Buttons

<SfButton @onclick="@OpenDialog">Open Dialog</SfButton>

<SfDialog Width="500px" ShowCloseIcon="true" @bind-Visible="@IsVisible">
    <DialogTemplates>
        <Header> Dialog </Header>
        <Content> Dialog enabled with Zoom effect </Content>
    </DialogTemplates>
    <DialogAnimationSettings Effect="@AnimationEffect" Duration=400 />
    <DialogButtons>
        <DialogButton Content="Hide" IsPrimary="true" OnClick="@CloseDialog" />
    </DialogButtons>
</SfDialog>

@code {
    private bool IsVisible { get; set; } = true;
    private DialogEffect AnimationEffect = DialogEffect.Zoom;

    private void OpenDialog()
    {
        this.IsVisible = true;
    }

    private void CloseDialog()
    {
        this.IsVisible = false;
    }
}

```
