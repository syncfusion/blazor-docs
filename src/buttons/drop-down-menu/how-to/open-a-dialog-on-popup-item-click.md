---
component: "Dropdown Menu"
---

# Open a dialog on popup item click

This section explains about how to open a dialog on Dropdown Menu popup item click. This can be achieved by
handling dialog open in [`ItemSelected`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.SplitButtons.DropDownButtonEvents.html#Syncfusion_Blazor_SplitButtons_DropDownButtonEvents_ItemSelected) event of the Dropdown Menu.

In the following example, Dialog will open while selecting `Other Folder...` item.

```csharp

@using Syncfusion.Blazor.SplitButtons
@using Syncfusion.Blazor.Popups
@using Syncfusion.Blazor.Buttons

<SfDropDownButton Content="Settings" IconCss="e-icons e-setting-icon" CssClass="e-vertical" IconPosition="SplitButtonIconPosition.Top">
    <DropDownButtonEvents ItemSelected="select"></DropDownButtonEvents>
    <DropDownMenuItems>
        <DropDownMenuItem Text="Help"></DropDownMenuItem>
        <DropDownMenuItem Text="About"></DropDownMenuItem>
        <DropDownMenuItem Text="Update"></DropDownMenuItem>
    </DropDownMenuItems>
</SfDropDownButton>
<SfDialog Content="@Content" Header="@Header" Width="250px" Height="150px" Visible="false" @ref="DialogObj" >
    <DialogPositionData X="300" Y="200"></DialogPositionData>
    <DialogButtons>
       <DialogButton OnClick="@click">
            <DialogButtonModel Content="OK" IsPrimary="true"></DialogButtonModel>
        </DialogButton>
        <DialogButton OnClick="@click">
            <DialogButtonModel Content="Cancel"></DialogButtonModel>
        </DialogButton>
    </DialogButtons>
</SfDialog>

@code  {
    SfDialog DialogObj;
    public string Content = "Are you sure want to update?";
    public string Header = "Software Update";

    private void click(object args)
    {
        DialogObj.Hide();
    }

    private void select(MenuEventArgs args)
    {
        if (args.Item.Text == "Update")
        {
            DialogObj.Show();
        }
    }
}

<style>
    .e-setting-icon::before {
        content: '\e679';
    }
</style>

```

Output be like

![Button Sample](./../images/ddb-dialog.png)