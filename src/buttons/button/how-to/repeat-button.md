# Repeat Button

The Repeat button is a type of Button in that the click event is triggered at regular time interval from the pressed state till the released state.

The following example explains about how to achieve Repeat Button in mouse and touch events.

```csharp

@using Syncfusion.Blazor.Buttons

<div id="preview">@EventName Event is triggered</div>
<SfButton Content="Button" @onclick="Click"></SfButton>

@code{
    public string EventName = "No";
    public void Click()
    {
        this.EventName = "Click";
    }
}

<style>
    #preview{
       float: right;
       padding: 0 350px 0 0;
    }
</style>

```

Output be like

![Button Sample](./../images/button-repeat.png)