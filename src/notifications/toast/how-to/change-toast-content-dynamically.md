---
component: "Toast"
---

# Change toast content dynamically

The Toast component supports to change its content dynamically while displaying in newest toasts. You can change the toast content by updating property value, before calling in the `show` method.

```csharp

@using Syncfusion.Blazor.Buttons
@using Syncfusion.Blazor.Notifications

<SfToast @ref="ToastObj" Title="Alert" Content="@ToastContent">
    <ToastPosition X="Right" Y="Bottom"></ToastPosition>
</SfToast>

<div class="col-lg-12 col-sm-12 col-md-12 center">
    <div style="margin: auto; text-align: center">
        <SfButton @onclick="@ShowToast"> Show Toast </SfButton>
    </div>
</div>

@code {
    SfToast ToastObj;

    private int ToastFlag = 0;
    private string ToastContent = "";
    private string[] Contents = new string[] {
        "Welcome User",
        "Upload in progress",
        "Upload success",
        "Profile updated",
        "Profile picture changed",
        "Password changed"
    };

    private async Task ShowToast()
    {
        this.ToastContent = this.Contents[this.ToastFlag];
        await Task.Delay(100);
        await this.ToastObj.Show();
        this.ToastFlag = ((this.ToastFlag != 5) ? (this.ToastFlag + 1) : 0);
    }
}

```