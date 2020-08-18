# Position Popup Open

Popup open position can be changed according to the requirement. Popup open position can be changed in [`OnOpen`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.SplitButtons.DropDownButtonEvents~OnOpen.html) event by setting `Top` and `Left` for the popup element.

In the following example, the `Top` position of the popup element is changed in open event.

```csharp

@using Syncfusion.Blazor.SplitButtons

<SfDropDownButton Content="EDIT">
    <DropDownButtonEvents OnOpen="Open"></DropDownButtonEvents>
    <DropDownMenuItems>
        <DropDownMenuItem Text="Cut"></DropDownMenuItem>
        <DropDownMenuItem Text="Copy"></DropDownMenuItem>
        <DropDownMenuItem Text="Paste"></DropDownMenuItem>
    </DropDownMenuItems>
</SfDropDownButton>

@code {
    public void Open(BeforeOpenCloseMenuEventArgs args)
    {
        args.Element.SetAttribute("style", "margin:-155px -27px");
    }
}

```

Output be like

![Button Sample](./../images/ddb-position.png)