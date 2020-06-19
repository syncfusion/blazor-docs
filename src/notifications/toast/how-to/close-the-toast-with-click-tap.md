---
title: "Blazor Toast Notification | Toast with a click or tap operation"
component: "Toast"
description: "This section explains Toaster component with a click or tap operation."
---

# Close the toast with click/tap

By default, the toasts are expired based on the `TimeOut` value. You can customize the toast hiding process with click/tap action by setting the `ToastClickEventArgs` in the clicked callback function with static Toast.

The following sample demonstrates the click/tap action in toast.

```csharp

@using Syncfusion.Blazor
@using Syncfusion.Blazor.Buttons
@using Syncfusion.Blazor.Notifications

<SfToast @ref="ToastObj" TimeOut=0 Title="Matt sent you a friend request" Content="@ToastContent">
    <ToastPosition X="Right" Y="Bottom"></ToastPosition>
    <ToastEvents OnClick="@ToastClick"></ToastEvents>
</SfToast>

<div class="col-lg-12 col-sm-12 col-md-12 center">
    <div style="margin: auto; text-align: center">
        <SfButton @onclick="@ShowOnClick"> Show Toast </SfButton>
    </div>
</div>

@code {
    SfToast ToastObj;

    public string ToastContent { get; set;} = "You have a new friend request yet to accept";

    private void ToastClick(ToastClickEventArgs args)
    {
        args.ClickToClose = true;
    }
    private void ShowOnClick()
    {
        this.ToastObj.Show();
    }
}

```