# Trace events of Progress Button

The Progress Button component triggers events based on its actions. The events can be used as extension points to perform custom operations.

The events available in Progress Button are [`OnFailure`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.SplitButtons.ProgressButtonEvents~OnFailure.html), [`OnBegin`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.SplitButtons.ProgressButtonEvents~OnBegin.html), [`Progressing`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.SplitButtons.ProgressButtonEvents~Progressing.html), and [`OnEnd`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.SplitButtons.ProgressButtonEvents~OnEnd.html).

```csharp

@using Syncfusion.Blazor.SplitButtons

<div id="preview">@eventName Event Triggered</div>
<SfProgressButton Content="Progress">
    <ProgressButtonEvents OnBegin="Begin" OnEnd="End" Progressing="Progressing"></ProgressButtonEvents>
</SfProgressButton>

@code {
    private string eventName = "No";
    public void Begin(ProgressEventArgs args)
    {
        this.eventName = "Begin";
    }
    public void End(ProgressEventArgs args)
    {
        this.eventName = "End";
    }
    public void Progressing(ProgressEventArgs args)
    {
        this.eventName = "Progressing";
    }
}

<style>
    #preview {
        float: right;
        padding: 0 350px 0 0;
    }
</style>

```

Output be like

![Progress Button Sample](./../images/pb-event.png)