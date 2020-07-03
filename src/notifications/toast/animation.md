---
title: "Blazor Toast Notification | Custom show/hide animations"
component: "Toast"
description: "This section explains the list of animation effects that can be applied to show or hide the Blazor toast notification popup by customize them."
---

# Animations

The toast component supports custom animations for both show and hide actions from the provided `ToastAnimationSettingsHide` and  `ToastAnimationSettingsShow` option of the `Animation` library.

The default animation is given as `FadeIn` for showing the toast and `FadeOut` for hiding the toast.

The following sample demonstrates some types of animations that suit toast. You can check all the animation effects here.

```csharp

@using Syncfusion.Blazor
@using Syncfusion.Blazor.Buttons
@using Syncfusion.Blazor.Notifications
@using Syncfusion.Blazor.DropDowns

<SfToast @ref="ToastObj" Title="Matt sent you a friend request" Content="@ToastContent">
    <ToastPosition X="Right" Y="Bottom"></ToastPosition>
    <ToastAnimationSettings>
        <ToastAnimationSettingsHide Effect="@HideAnimation"></ToastAnimationSettingsHide>
        <ToastAnimationSettingsShow Effect="@ShowAnimation"></ToastAnimationSettingsShow>
    </ToastAnimationSettings>
</SfToast>
<div class="col-lg-12 col-sm-12 col-md-12 center">
    <div id="toastBtnDefault" style="margin: auto; text-align: center">
        <div id="textbox-contain">
            <div class="col-xs-6 col-sm-6 col-lg-6 col-md-6">
                <label> Show Animation </label>
            </div>
            <SfDropDownList Placeholder="Select a animate type" DataSource="@ddlData1" TValue="string">
                <DropDownListEvents ValueChange="DDLvalueChange" TValue="string"></DropDownListEvents>
                <DropDownListFieldSettings Text="text" Value="id"></DropDownListFieldSettings>
            </SfDropDownList>
            <div class="col-xs-6 col-sm-6 col-lg-6 col-md-6">
                <label> Hide Animation </label>
            </div>
            <SfDropDownList Placeholder="Select a animate type" DataSource="@ddlData2" TValue="string">
                <DropDownListEvents ValueChange="DDLvalueChange1" TValue="string"></DropDownListEvents>
                <DropDownListFieldSettings Text="text" Value="id"></DropDownListFieldSettings>
            </SfDropDownList>
        </div>
        <SfButton @onclick="@ShowOnClick"> Show Toast </SfButton>
    </div>
</div>

<style>
    #elementToastTime .e-toast-message {
        padding: 10px;
        text-align: center;
    }

    #textbox-contain {
        text-align: initial;
        display: inline-block;
        width: 20%;
        margin: 0 auto;
    }

    .top-row.px-4 {
        display: none;
    }

    .content.px-4 {
        margin-top: 103px;
        margin-left: -12%;
    }
</style>

@code {
    SfToast ToastObj;

    public string ShowAnimation = "FadeIn";
    public string HideAnimation = "FadeOut";
    public string ToastContent = "You have a new friend request yet to accept";
    public class DDLfields
    {
        public string id { get; set; }
        public string text { get; set; }
    }

    public List<DDLfields> ddlData1 = new List<DDLfields>()
{
        new DDLfields(){ id= "FadeIn", text= "Fade In" },
        new DDLfields(){ id= "FadeZoomIn", text= "Fade Zoom In" },
        new DDLfields(){ id= "FadeZoomOut", text= "Fade Zoom Out" },
        new DDLfields(){ id= "FlipLeftDownIn", text= "Flip Left Down In" },
        new DDLfields(){ id= "FlipLeftDownOut", text= "Flip Left Down Out" },
        new DDLfields(){ id= "FlipLeftUpIn", text= "Flip Left Up In" },
        new DDLfields(){ id= "FlipRightDownIn", text= "Flip Right Up In" },
        new DDLfields(){ id= "FlipRightDownOut", text= "Flip Right Down Out" },
        new DDLfields(){ id= "FlipRightUpIn", text= "Flip Right Up In" },
        new DDLfields(){ id= "FlipRightUpOut", text= "Flip Right Up Out" },
        new DDLfields(){ id= "SlideBottomIn", text= "Slide Bottom In" },
        new DDLfields(){ id= "SlideBottomOut", text= "Slide Bottom Out" },
        new DDLfields(){ id= "SlideLeftIn", text= "Slide Left In" },
        new DDLfields(){ id= "SlideLeftOut", text= "Slide Left Out" },
        new DDLfields(){ id= "SlideRightIn", text= "Slide Right In" },
        new DDLfields(){ id= "SlideRightOut", text= "Slide Right Out" },
        new DDLfields(){ id= "SlideTopIn", text= "Slide Top In" },
        new DDLfields(){ id= "ZoomIn", text= "Zoom In" },
        new DDLfields(){ id= "ZoomOut", text= "Zoom Out" }
    };
    public List<DDLfields> ddlData2 = new List<DDLfields>()
{
        new DDLfields(){ id= "FadeIn", text= "Fade In" },
        new DDLfields(){ id= "FadeZoomIn", text= "Fade Zoom In" },
        new DDLfields(){ id= "FadeZoomOut", text= "Fade Zoom Out" },
        new DDLfields(){ id= "FlipLeftDownIn", text= "Flip Left Down In" },
        new DDLfields(){ id= "FlipLeftDownOut", text= "Flip Left Down Out" },
        new DDLfields(){ id= "FlipLeftUpIn", text= "Flip Left Up In" },
        new DDLfields(){ id= "FlipRightDownIn", text= "Flip Right Up In" },
        new DDLfields(){ id= "FlipRightDownOut", text= "Flip Right Down Out" },
        new DDLfields(){ id= "FlipRightUpIn", text= "Flip Right Up In" },
        new DDLfields(){ id= "FlipRightUpOut", text= "Flip Right Up Out" },
        new DDLfields(){ id= "SlideBottomIn", text= "Slide Bottom In" },
        new DDLfields(){ id= "SlideBottomOut", text= "Slide Bottom Out" },
        new DDLfields(){ id= "SlideLeftIn", text= "Slide Left In" },
        new DDLfields(){ id= "SlideLeftOut", text= "Slide Left Out" },
        new DDLfields(){ id= "SlideRightIn", text= "Slide Right In" },
        new DDLfields(){ id= "SlideRightOut", text= "Slide Right Out" },
        new DDLfields(){ id= "SlideTopIn", text= "Slide Top In" },
        new DDLfields(){ id= "ZoomIn", text= "Zoom In" },
        new DDLfields(){ id= "ZoomOut", text= "Zoom Out" }
    };

    private void ShowOnClick()
    {
        ToastObj.Show();
    }
    private void DDLvalueChange(ChangeEventArgs<string> args)
    {
        ShowAnimation = args.Value as string;
        StateHasChanged();
    }
    private void DDLvalueChange1(ChangeEventArgs<string> args)
    {
        HideAnimation = args.Value as string;
        StateHasChanged();
    }
}

```