# Enable ripple for Switch label

By default, label with ripple effect is not available in Switch. You can achieve this using `EnableRipple`
property. The following example illustrates how to enable ripple effect for labels in Switch component.

`Index.razor`

```csharp
@using Syncfusion.EJ2.RazorComponents;
@using Microsoft.JSInterop;

<div ID='container'>
    <table class='size'>
        <tr>
            <td><label for='switch1'>USB Tethering</label></td>
            <td>
                <EjsSwitch ID="switch1"></EjsSwitch>
            </td>
        </tr>
    </table>
</div>

@functions {
     [Inject]
    protected IJSRuntime JSRuntime { get; set; }

    protected override void OnAfterRender()
    {
        this.JSRuntime.Ejs().EnableRipple(true);
    }
}

  ```