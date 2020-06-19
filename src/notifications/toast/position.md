---
title: "Blazor Toast Notification | Predefined and custom position"
component: "Toast"
description: "This section explains how to position the Blazor toast notification popup in various built-in position and custom position (X, Y)."
---

# Positions

The toast position can be updated based on predefined positions or customizable positions. The predefined position combinations are updated in the `X` and `Y` position properties.

## Predefined

`X` Positions

* Left
* Center
* Right

`Y` Positions

* Top
* Bottom

> In multiple toast display, the new toast position will not be updated on dynamic change of property values until the old toast messages removed.
> The toast occupies full width when you set the width to '100%', so the X positions will not affect the changes when the width is '100%'.

## Custom

Custom `X` and `Y` positions can be given as pixels/numbers/percentage. The number value is considered as pixels based on the top and left values updated in the toast.

```csharp

@using Syncfusion.Blazor
@using Syncfusion.Blazor.Buttons
@using Syncfusion.Blazor.Notifications
@using Syncfusion.Blazor.DropDowns
@using Syncfusion.Blazor.Inputs
@using System.Threading

<SfToast @ref="ToastObj" Target="@ToastTarget" Title="Matt sent you a friend request" Height="@Height" Width="@Width" Content="@ToastContent">
    <ToastPosition X="@PositionX" Y="@PositionY"></ToastPosition>
</SfToast>
<div class="col-lg-12 col-sm-12 col-md-12 center">
    <div id="toastBtnDefault" style="margin: auto; text-align: center">
        <SfButton @onclick="ShowOnClick"> Show Toast </SfButton>
        <SfButton @onclick="HideOnClick"> Hide All </SfButton>
    </div>
</div>
<div class='row' style="padding-top: 20px" id="toast_pos_target">
    <div id="toast_pos"> </div>
    <div id="toast_pos_property">
        <table style="width: 100%">
            <tr>
                <td>
                    <div style='padding:25px 0 0 0;'>
                        <SfRadioButton Label="Position" Name="toastPos" Value="Position" Checked="true" ValueChange="CheckboxChange2"></SfRadioButton>
                    </div>
                </td>
                <td>
                    <div style='padding:25px 0 0 0;'>
                        <SfRadioButton Label="Custom" Name="toastPos" Value="Custom" ValueChange="CheckboxChange3"></SfRadioButton>
                    </div>
                </td>
            </tr>
            <tr>
                <td id="dropdownChoose" colspan="2" style="display:@DispVal2;">
                    <SfDropDownList @ref="ListObj" Index="5" Placeholder="Select a position" PopupHeight="200PX" DataSource="@DdlData" TValue="string">
                        <DropDownListEvents ValueChange="DDLvalueChange" TValue="string"></DropDownListEvents>
                        <DropDownListFieldSettings text="id" value="text"></DropDownListFieldSettings>
                    </SfDropDownList>
                </td>
            </tr>

            <tr>
                <td colspan="2" id="customChoose" style="display:@DispVal1">
                    <form id="formId" class="form-horizontal">
                        <div class='e-row'>
                            <SfTextBox @ref="TextXpos" Value="50" Placeholder="X Position" FloatLabelType="@FloatLabelType.Auto"></SfTextBox>
                        </div>
                        <div class='e-row'>
                            <SfTextBox @ref="TextYpos" Value="50" Placeholder="Y Position" FloatLabelType="@FloatLabelType.Auto"></SfTextBox>
                        </div>
                    </form>
                </td>
            </tr>
            <tr>
                <td>
                    <div style='padding:25px 0 0 0;'>
                        <SfRadioButton Label="Target" Name="toast" Value="Target" ValueChange="@CheckboxChange"></SfRadioButton>
                    </div>
                </td>
                <td>
                    <div style='padding:25px 0 0 0;'>
                        <SfRadioButton Label="Global" Name="toast" Value="Global" Checked="true" ValueChange="@CheckboxChange1"></SfRadioButton>
                    </div>
                </td>
            </tr>
        </table>
    </div>
</div>

<style>
    #toast_default .e-meeting::before {
        content: "\e705";
        font-size: 17px;
    }

    #toast_pos_property {
        width: 250px;
    }

    #toast_pos_property td {
        width: 50%;
    }

    #toast_pos_target {
        margin: 50px 200px;
    }
</style>

@code {
    SfToast ToastObj;
    SfDropDownList<string> ListObj;
    SfTextBox TextXpos;
    SfTextBox TextYpos;

    public class DDLfields
    {
        public string id { get; set; }
        public string text { get; set; }
    }

    List<DDLfields> DdlData = new List<DDLfields>()
{
        new DDLfields(){ id= "topleft", text= "Top Left" },
        new DDLfields(){ id= "topright", text= "Top Right" },
        new DDLfields(){ id= "topcenter", text= "Top Center" },
        new DDLfields(){ id= "bottomleft", text= "Bottom Left" },
        new DDLfields(){ id= "bottomright", text= "Bottom Right" },
        new DDLfields(){ id= "bottomcenter", text= "Bottom Center" }
    };

    // default values for component initialization.
    public string ToastContent = "You have a new friend request yet to accept";
    public string PositionX = "Center";
    public string PositionY = "Bottom";
    public string ToastTarget = null;
    public string Width = "300";
    public string Height = "auto";
    public bool CustomFlag;
    public string DispVal1 { get; set; } = "none";
    public string DispVal2 { get; set; } = "";
    private void DDLvalueChange(ChangeEventArgs<string> e)
    {
        ToastObj.Hide("All");
        setToastPosValue(e.Value.ToString());
    }

    private void setToastPosValue(string value)
    {
        switch (value)
        {

            case "Top Left":
                PositionX = "Left";
                PositionY = "Top";
                break;

            case "Top Right":
                PositionX = "Right";
                PositionY = "Top";
                break;

            case "Top Center":
                PositionX = "Center";
                PositionY = "Top";
                break;

            case "Bottom Left":
                PositionX = "Left";
                PositionY = "Bottom";
                break;

            case "Bottom Right":
                PositionX = "Right";
                PositionY = "Bottom";
                break;

            case "Bottom Center":
                PositionX = "Center";
                PositionY = "Bottom";
                break;
        }
    }

    private void CheckboxChange(Syncfusion.Blazor.Buttons.ChangeArgs e)
    {
        if (e.Value == "Target")
        {
            ToastObj.Hide("All");
            ToastTarget = "#toast_pos_target";
            StateHasChanged();
        }
    }

    private void CheckboxChange1(Syncfusion.Blazor.Buttons.ChangeArgs e)
    {
        if (e.Value == "Global")
        {
            ToastObj.Hide("All");
            ToastTarget = null;
            StateHasChanged();
        }
    }

    private void CheckboxChange2(Syncfusion.Blazor.Buttons.ChangeArgs e)
    {
        if (e.Value == "Position")
        {
            ToastObj.Hide("All");
            DispVal2 = "table-cell";
            DispVal1 = "none";
            setToastPosValue(ListObj.Value.ToString());
            CustomFlag = false;
        }
    }

    private void CheckboxChange3(Syncfusion.Blazor.Buttons.ChangeArgs e)
    {
        if (e.Value == "Custom")
        {
            ToastObj.Hide("All");
            DispVal1 = "table-cell";
            DispVal2 = "none";
            SetcustomPosValue();
            CustomFlag = true;
        }
    }

    //Setting Toast Custom Position
    private void SetcustomPosValue()
    {
        PositionX = TextXpos.Value;
        PositionY = TextYpos.Value;
    }

    private void toastShow(int timeDelay)
    {
        Thread.Sleep(timeDelay);
        ToastObj.Show();
    }

    private void ShowOnClick()
    {
        if (CustomFlag)
        {
            SetcustomPosValue();
        }
        ToastObj.Show();
    }

    private void HideOnClick()
    {
        ToastObj.Hide("All");
    }

}

```
