---
title: "Blazor Toast Notification | Show different types of toast"
component: "Toast"
description: "This section explains creating different types of Blazor Toast component is displayed on a screen."
---

# Show different types of toast

The Blazor toast has the following predefined styles that can be defined using the `CssClass` property for achieving different types of toast:

| Class | Description |
| -------- | -------- |
| `e-toast-success` | Represents a positive toast |
| `e-toast-info` | Represents an informative toast |
| `e-toast-warning` | Represents a toast with caution |
| `e-toast-danger` | Represents a negative toast |

The following sample demonstrates the different types of toast.

```csharp

@using Syncfusion.Blazor
@using Syncfusion.Blazor.Buttons
@using Syncfusion.Blazor.Notifications

<SfToast @ref="ToastObj" Title="@ToastTitle" Content="@ToastContent" CssClass="@ToastCssClass">
    <ToastPosition X="Right" Y="Bottom"></ToastPosition>
</SfToast>

<div class="col-lg-12 col-sm-12 col-md-12 center">
    <div style="margin: auto; text-align: center">
        <SfButton @onclick="@ShowOnClick"> Show Toast </SfButton>
    </div>
</div>

@code {
    SfToast ToastObj;

    private int ToastFlag = 0;
    private string ToastTitle = "";
    private string ToastContent = "";
    private string ToastCssClass = "";

    private ToastOption[] Toasts = new ToastOption[] {
        new ToastOption { Title = "Warning !", Content = "There was a problem with your network connection.", CssClass = "e-toast-warning" },
        new ToastOption { Title = "Success !", Content = "Your message has been sent successfully.", CssClass = "e-toast-success" },
        new ToastOption { Title = "Error !", Content = "A problem has been occurred while submitting your data.", CssClass = "e-toast-danger" },
        new ToastOption { Title = "Information !", Content = "Please read the comments carefully.", CssClass = "e-toast-info" }
    };

    private async void ShowOnClick()
    {
        this.ToastTitle = this.Toasts[this.ToastFlag].Title;
        this.ToastContent = this.Toasts[this.ToastFlag].Content;
        this.ToastCssClass = this.Toasts[this.ToastFlag].CssClass;

        await Task.Delay(100);
        this.ToastObj.Show();
        this.ToastFlag = ((this.ToastFlag == Toasts.Length - 1) ? 0 : (this.ToastFlag + 1));
    }

    private class ToastOption
    {
        public string Title { get; set; }
        public string Content { get; set; }
        public string CssClass { get; set; }
    }
}

```