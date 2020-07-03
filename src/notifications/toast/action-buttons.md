---
title: "Blazor Toast Notification | Integrate action buttons"
component: "Toast"
description: "This section describes how to integrate the action buttons such as ignore, reply, and more with Blazor toast notification component."
---

# Action Buttons

You can include action buttons to the toast control by adding the `ToastButtonModelProp` property. The collection of Blazor button models can be bound to the `Model` property inside the ToastButtonModelProps property. You can also include the click event callback function for each button.

```csharp

@using Syncfusion.Blazor
@using Syncfusion.Blazor.Buttons
@using Syncfusion.Blazor.Notifications
@using Microsoft.AspNetCore.Components.Web

<SfToast @ref="ToastObj" Title="Anjolie Stokes" Width="280" Height="120" Content="@ToastContent" Icon="e-laura">
    <ToastPosition X="Right" Y="Bottom"></ToastPosition>
    <ToastButtonModelProps>
        <ToastButtonModelProp Model="@IgnoreBtnObj" Clicked="@OnIgnore"></ToastButtonModelProp>
        <ToastButtonModelProp Model="@ReplyBtnObj" Clicked="@OnIgnore"></ToastButtonModelProp>
    </ToastButtonModelProps>
</SfToast>
<div class="col-lg-12 col-sm-12 col-md-12 center">
    <div id="toastBtnDefault" style="margin: auto; text-align: center">
        <SfButton @onclick="@ShowOnClick"> Show Toast </SfButton>
    </div>
</div>

<style>
    .e-toast-icon.e-laura.e-icons {
        border-radius: 50%;
        background-repeat: no-repeat;
        background-size: cover;
        background-image: url(https://blazor.syncfusion.com/demos/images/toast/laura.png);
        height: 44px !important;
        margin: 0;
        width: 60px;
    }
    #elementToastTime .e-toast-message {
        padding: 10px;
    }
</style>

@code {
    SfToast ToastObj;
    public string ToastContent { get;set; } = "Thanks for the update!";
    private void ShowOnClick(object args)
    {
        this.ToastObj.Show();
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

The output will be as follows.

![Action button](./images/action-button.png)

## See Also

* [Configuring options](./config/)