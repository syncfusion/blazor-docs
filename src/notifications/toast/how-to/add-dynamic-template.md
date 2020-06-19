---
title: "Blazor Toast Notification | Add dynamic template"
component: "Toast"
description: "This section explains how to dynamically change a template for display in multiple Blazor Toaster component."
---

# Add dynamic template

Toast supports to change templates dynamically with displaying in multiple toasts. You can change the toast properties while calling in the `Show` method.

```csharp

@using Syncfusion.Blazor
@using Syncfusion.Blazor.Buttons
@using Syncfusion.Blazor.Notifications

<SfToast @ref="ToastObj">
    <ToastPosition X="Right" Y="Bottom"></ToastPosition>
</SfToast>

<div class="col-lg-12 col-sm-12 col-md-12 center">
    <div style="margin: auto; text-align: center">
        <SfButton @onclick="@ShowOnClick"> Show Toast </SfButton>
    </div>
</div>

@code {
    SfToast ToastObj;

    public int ToastFlag = 0;

    public ToastModel[] Messages = new ToastModel[] {
        new ToastModel() { Template = "2 Mail has received"},
        new ToastModel() { Template = "User Guest Logged in"},
        new ToastModel() { Template = "Logging in as Guest"},
        new ToastModel() { Template = "Ticket has reserved"}
    };

    private async void ShowOnClick()
    {
        await Task.Delay(100);
        this.ToastObj.Show(Messages[this.ToastFlag]);
        this.ToastFlag = ((this.ToastFlag == Messages.Length - 1) ? 0 : (this.ToastFlag + 1));
    }
}

```
