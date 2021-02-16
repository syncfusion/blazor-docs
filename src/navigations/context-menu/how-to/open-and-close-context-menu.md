# Open and close Context Menu

Open and close the Context Menu manually whenever required by using the Open and Close methods. In the following sample, the Context Menu manually open while clicking the button using [`Open`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Navigations.SfContextMenu-1.html#Syncfusion_Blazor_Navigations_SfContextMenu_1_Open_System_Nullable_System_Double__System_Nullable_System_Double__) method with `ClientX` and `ClientY` coordinates.
To manually close the Context Menu, [`Close`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Navigations.SfContextMenu-1.html#Syncfusion_Blazor_Navigations_SfContextMenu_1_Close) method can be used.

```csharp
@using Syncfusion.Blazor.Navigations
@using Syncfusion.Blazor.Buttons

<div id="target">
    <SfContextMenu @ref="contextMenuObj" TValue="MenuItem">
        <MenuItems>
            <MenuItem Text="Cut"></MenuItem>
            <MenuItem Text="Copy"></MenuItem>
            <MenuItem Text="Paste"></MenuItem>
        </MenuItems>
    </SfContextMenu>
    <SfButton @onclick="OpenContextMenu">Open ContextMenu</SfButton>
</div>

@code {
    SfContextMenu<MenuItem> contextMenuObj;
    private void OpenContextMenu(MouseEventArgs e)
    {
        contextMenuObj.Open(e.ClientX, e.ClientY);
    }
}

```

Output be like

![Context Menu Sample](./../images/open-close.png)