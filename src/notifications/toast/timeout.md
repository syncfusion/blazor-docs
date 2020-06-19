---
title: "Blazor Toast Notification | Static Toast and Timeout"
component: "Toast"
description: "This section explains how to create static toast notification and how to use the timeout functionalities using Blazor Toast component."
---

# Time out

The toast can be expired based on the `TimeOut` property. The toast can live till the time out reaches without user interaction, a time out value is considered as a millisecond.

* The `TimeOut` delay can be visually represented using [Progress Bar](./config/#progress-bar).

* The `ExtendedTimeOut` property determines how long the toast should be displayed after a user hovers over it.

> You can terminate the process by using the `showCloseButton` property for destroying the toast at any time.

```csharp

@using Syncfusion.Blazor
@using Syncfusion.Blazor.Buttons
@using Syncfusion.Blazor.Notifications
@using Syncfusion.Blazor.Inputs
@using Microsoft.AspNetCore.Components.Web

<div class="control-section toast-default-section">
    <SfToast @ref="ToastObj" TimeOut="@ToastTimeOut" Title="Anjolie Stokes" Width="230" Height="250" Content="@ToastContent" >
        <ToastPosition X="Right" Y="Bottom"></ToastPosition>
        <ToastButtonModelProps>
            <ToastButtonModelProp Model="@IgnoreBtnObj" Clicked="@OnIgnore"></ToastButtonModelProp>
            <ToastButtonModelProp Model="@ReplyBtnObj"></ToastButtonModelProp>
        </ToastButtonModelProps>
    </SfToast>
    <div class="col-lg-12 col-sm-12 col-md-12 center">
        <div id="toastBtnDefault" style="margin: auto; text-align: center">
            <div id="textbox-contain" style="text-align: initial; display: inline-block;">
                <SfTextBox @ref="TextBoxObj" FloatLabelType="FloatLabelType.Auto" Value="@TextBoxVal" Placeholder="Enter timeOut" ValueChange="@OnValChange"></SfTextBox>
            </div>
            <SfButton @onclick="@ShowOnClick"> Show Toast </SfButton>
        </div>
    </div>
    <br /><br />
    <div id='result'></div>
</div>

<style>
    #elementToastTime .e-toast-message {
        padding: 10px;
        text-align: center;
    }

    #textbox-contain {
        text-align: initial;
        display: inline-block
    }
</style>

@code {
    SfTextBox TextBoxObj;
    SfToast ToastObj;
    public string ToastContent { get;set; } = "<p><img src='https://blazor.syncfusion.com/demos/images/toast/laura.png'></p>";
    public double ToastTimeOut { get;set; } = 0;
    public string TextBoxVal { get;set; } = "0";

    private void ShowOnClick()
    {
        this.ToastObj.Show();
    }

    private void OnValChange(object args)
    {
        this.ToastTimeOut = int.Parse(this.TextBoxObj.Value);
        this.TextBoxVal = this.TextBoxObj.Value;
        this.StateHasChanged();
    }

    private ButtonModel IgnoreBtnObj = new ButtonModel
    {
        Content = "Ignore"
    };

    private ButtonModel ReplyBtnObj = new ButtonModel
    {
        Content = "reply"
    };

    private void OnIgnore(MouseEventArgs args)
    {
        this.ToastObj.Hide();
    }
}

```

The above code will give following output.

![TimeOut](./images/timeout.png)

## Static toast

You can prevent auto hiding in a toast as visible like static by setting zero (`0`) value in the timeOut Property.

```csharp

@using Syncfusion.Blazor
@using Syncfusion.Blazor.Buttons
@using Syncfusion.Blazor.Notifications
@using Syncfusion.Blazor.Inputs

<SfToast @ref="ToastObj" TimeOut=0 Title="Matt sent you a friend request" Content="@ToastContent">
    <ToastPosition X="Right"></ToastPosition>
</SfToast>
<div class="col-lg-12 col-sm-12 col-md-12 center">
    <div id="toastBtnDefault" style="margin: auto; text-align: center">
        <SfButton @onclick="@ShowOnClick"> Show Toast </SfButton>
    </div>
</div>

<style>
    #elementToastTime .e-toast-message {
        padding: 10px;
        text-align: center;
    }
</style>

@code {
    SfToast ToastObj;
    public string ToastContent = "You have a new friend request yet to accept";
    private void ShowOnClick()
    {
        this.ToastObj.Show();
    }
}

```

The output will be as follows.

![TimeOut](./images/timeout-static.png)