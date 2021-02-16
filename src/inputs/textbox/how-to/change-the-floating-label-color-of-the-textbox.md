# Change the floating label color of the TextBox

You can change the floating label color of the TextBox for both `success` and `warning` validation states by applying the following CSS styles.

```csharp
@using Syncfusion.Blazor.Inputs

    <div class="e-float-input @(TextClass) e-success">
        <input type="text" @onfocus="@Focus" @onblur="@Blur" required />
        <span class="e-float-line"></span>
        <label class="e-float-text">Success</label>
    </div>
    <div class="e-float-input @(FloatTextClass) e-warning">
        <input type="text" @onfocus="@FlaotFocus" @onblur="@FloatBlur" required />
        <span class="e-float-line"></span>
        <label class="e-float-text">Warning</label>
    </div>

@code {
    public string FocusClass { get; set; } = " e-input-focus";
    public string TextClass { get; set; } = "e-input-group";
    public string FloatTextClass { get; set; } = "e-input-group";
    public void Focus(FocusEventArgs args)
    {
        this.TextClass = this.TextClass + FocusClass;
        StateHasChanged();
    }

    public void FlaotFocus(FocusEventArgs args)
    {
        this.FloatTextClass = this.FloatTextClass + FocusClass;
        StateHasChanged();
    }

    public void Blur(FocusEventArgs args)
    {
        if (this.TextClass.Contains(FocusClass))
        {
            this.TextClass = this.TextClass.Replace(FocusClass, "");
        }
        StateHasChanged();
    }

    public void FloatBlur(FocusEventArgs args)
    {
        if (this.FloatTextClass.Contains(FocusClass))
        {
            this.FloatTextClass = this.FloatTextClass.Replace(FocusClass, "");
        }
        StateHasChanged();
    }
}

<style>
    .e-float-input.e-success label.e-float-text,
    .e-float-input.e-success input:focus ~ label.e-float-text,
    .e-float-input.e-success input:valid ~ label.e-float-text {
        color: #22b24b;
    }

    /* For Warning state */
    .e-float-input.e-warning label.e-float-text,
    .e-float-input.e-warning input:focus ~ label.e-float-text,
    .e-float-input.e-warning input:valid ~ label.e-float-text {
        color: #ffca1c;
    }
</style>
```

The output will be as follows.

![textbox](../images/custom_floatlabel.png)