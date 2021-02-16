# Change caret icon

Dropdown arrow can be customized on popup open and close. It can be handled in
[`OnOpen`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.SplitButtons.SfDropDownButton.html) and
[`OnClose`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.SplitButtons.SfDropDownButton.html) event.

In the following example, the up arrow is updated on popup close and down arrow is updated on popup open using `OnOpen` and `OnClose` event by adding and removing `e-caret-up` class.

```csharp
@using Syncfusion.Blazor.SplitButtons

<SfDropDownButton CssClass="@IconCss" Content="Clipboard">
    <DropDownButtonEvents OnOpen="beforeOpen" OnClose="beforeClose"></DropDownButtonEvents>
    <DropDownMenuItems>
        <DropDownMenuItem Text="Edit"></DropDownMenuItem>
        <DropDownMenuItem Text="Copy"></DropDownMenuItem>
        <DropDownMenuItem Text="Paste"></DropDownMenuItem>
    </DropDownMenuItems>
</SfDropDownButton>

@code {
    public string IconCss = "";
    private void beforeOpen(BeforeOpenCloseMenuEventArgs args)
    {
        this.IconCss = "e-caret-up";
        this.StateHasChanged();
    }
    private void beforeClose(BeforeOpenCloseMenuEventArgs args)
    {
        this.IconCss = "";
        this.StateHasChanged();
    }
}

<style>
    .e-caret {
        transform: rotate(0deg);
        transition: transform 200ms ease-in-out;
    }

    .e-caret-up .e-caret {
        transform: rotate(180deg);
    }
</style>

```

Output be like

![Change caret icon](./../images/ddb-caret.png)