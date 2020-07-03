---
title: "Open a dialog on item click"
component: "Context Menu"
description: "This section helps to learn how to open a dialog on context menu item click"
---

# Open a dialog on Context Menu item click

This section explains about how to open a dialog on Context Menu item click. This can be achieved by handling dialog open in [`ItemSelected`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Navigations.SfContextMenu~ItemSelected.html) event of the Context Menu.

In the following sample, Dialog will open while clicking `Save As...` item.

```csharp
@using Syncfusion.Blazor.Navigations
@using Syncfusion.Blazor.Popups
@using Syncfusion.Blazor.Buttons

<div id="target">Right click/Touch hold to open the ContextMenu </div>
<SfContextMenu Target="#target" Items="@MenuItems">
    <ContextMenuEvents ItemSelected="select"></ContextMenuEvents>
</SfContextMenu>
<SfDialog Content="@Value" Visible="false" Target="#target" Width="200px" Height="110px" @ref="DialogObj">
    <DialogButtons>
        <DialogButton ButtonModel="@Button" OnClick="clicked"></DialogButton>
    </DialogButtons>
</SfDialog>

@code {
    SfDialog DialogObj;
    public string Value = "This file can be saved as PDF";
    public List<MenuItem> MenuItems = new List<MenuItem>
    {
        new MenuItem{ Text = "Back" },
        new MenuItem{ Text = "Forward" },
        new MenuItem{ Text = "Reload" },
        new MenuItem{ Separator = true },
        new MenuItem{ Text = "Save As..." },
        new MenuItem{ Text = "Print"},
        new MenuItem{ Text = "Cast"}
    };

    private void clicked(object args)
    {
        DialogObj.Hide();
    }
    public class ButtonModel
    {
        public string Content { get; set; }
        public bool IsPrimary { get; set; }
    }
    public ButtonModel Button = new ButtonModel { Content = "Submit", IsPrimary = true };

    private void select(MenuEventArgs args)
    {
        if (args.Item.Text == "Save As...")
        {
            DialogObj.Show();
        }
    }
}

<style>
    #target{
        border: 1px dashed;
        height: 150px;
        padding: 10px;
        position: relative;
        text-align: justify;
        color: gray;
        user-select: none;
    }
</style>

```

Output be like
![Context Menu Sample](./../images/dialog.png)