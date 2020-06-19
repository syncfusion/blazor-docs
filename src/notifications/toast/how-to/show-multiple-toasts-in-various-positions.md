---
title: "Blazor Toast Notification | Show toast in various positions"
component: "Toast"
description: "This section explains the Blazor Toast component at various positions."
---

# Show multiple toasts in various positions

By default, the positions of the new toasts are only updated after the visible toasts have been destroyed. If You need to display multiple toasts with different positions, initiate another toast.

The following sample demonstrates adding multiple toasts in different positions.

```csharp

@using Syncfusion.Blazor
@using Syncfusion.Blazor.Buttons
@using Syncfusion.Blazor.Notifications

<SfToast @ref="WarningToastObj" Title="Warning !" Content="@WarningContent">
    <ToastPosition X="Right" Y="Bottom"></ToastPosition>
    <ToastEvents OnClick="@ToastClick"></ToastEvents>
</SfToast>

<SfToast @ref="SuccessToastObj" Title="Success !" Content="@SuccessContent">
    <ToastPosition X="Left" Y="Bottom"></ToastPosition>
    <ToastEvents OnClick="@ToastClick"></ToastEvents>
</SfToast>

<div class="col-lg-12 col-sm-12 col-md-12 center">
    <div style="margin: auto; text-align: center">
        <SfButton @onclick="@ShowWarningToast"> Show Warning Toast </SfButton>
        <SfButton @onclick="@ShowSuccessToast"> Show Success Toast </SfButton>
    </div>
</div>

@code {
    SfToast WarningToastObj;
    SfToast SuccessToastObj;

    public string WarningContent { get; set;} = "There was a problem with your network connection.";
    public string SuccessContent { get; set;} = "Your message has been sent successfully.";

    private void ToastClick(ToastClickEventArgs args)
    {
        args.ClickToClose = true;
    }
    private void ShowWarningToast()
    {
        this.WarningToastObj.Show();
    }

    private void ShowSuccessToast()
    {
        this.SuccessToastObj.Show();
    }
}

```