# Customize Color Picker

## Custom Palette

By default, the Palette will be rendered with default colors. To load custom colors in the palette, specify the colors in the [`PresetColors`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Inputs.SfColorPicker~PresetColors.html) property. To customize the color palette, add a custom class to palette tiles using [`OnTileRender`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Inputs.SfColorPicker~OnTileRender.html) event.

```csharp

@using Syncfusion.Blazor.Inputs
@using Newtonsoft.Json.Linq;

<div id="preview" style="@StyleValue"></div>
<h4>Select a color</h4>
<SfColorPicker Mode="Syncfusion.Blazor.Inputs.ColorPickerMode.Palette" CssClass="circle-palette" ModeSwitcher="false" Inline="true" ShowButtons="false" Columns="4" PresetColors="@CustomValues[0]" OnTileRender="BeforeCircleTileRender" ValueChange="OnChange"></SfColorPicker>

@code{
    public string StyleValue = "background-color:#008000";
    public GetCurrentValue ColorValue { get; set; }
    public void OnChange(ColorPickerEventArgs args)
    {
        this.ColorValue = ((JObject)args.CurrentValue).ToObject<GetCurrentValue>();
        this.StyleValue = "background-color:" + this.ColorValue.hex;
        this.StateHasChanged();
    }
    public class GetCurrentValue
    {
        public string hex { get; set; }
        public string rgba { get; set; }
    }
    public void BeforeCircleTileRender(PaletteTileEventArgs args)
    {
        args.Element.AddClass(new string[] { "e-circle-palette" });
    }
    public List<object> CustomValues = new List<object> {
    new{
        Custom = new string[] {"#ef9a9a", "#e57373", "#ef5350", "#f44336", "#f48fb1", "#f06292",
                    "#ec407a", "#e91e63", "#ce93d8", "#ba68c8", "#ab47bc", "#9c27b0", "#b39ddb","#9575cd",
                    "#7e57c2", "#673AB7", "#9FA8DA", "#7986CB", "#5C6BC0", "#3F51B5", "#90CAF9", "#64B5F6",
                    "#42A5F5","#2196F3", "#81D4FA", "#4FC3F7", "#29B6F6", "#03A9F4", "#80DEEA", "#4DD0E1",
                    "#26C6DA", "#00BCD4", "#80CBC4", "#4DB6AC", "#26A69A", "#009688","#A5D6A7", "#81C784",
                    "#66BB6A", "#4CAF50", "#C5E1A5", "#AED581", "#9CCC65", "#8BC34A", "#E6EE9C","#DCE775",
                    "#D4E157", "#CDDC39" }
        }
   };
}

<style>
     #preview {
        height: 50px;
        width: 50%;
     }

    .e-container .e-palette .e-circle-palette {
        border: 0;
        height: 32px;
        width: 32px;
        border-radius: 20px;
        margin: 4px;
    }

    .circle-palette .e-container {
        background-color: transparent;
        border-color: transparent;
        box-shadow: none;
    }

    .e-container .e-palette .e-circle-palette.e-selected {
        outline: none;
    }
</style>

```

Output be like
![color-picker](./../images/cp-custom.png)

## Hide input area from picker

By default, the input area will be rendered in Color Picker. To hide the input area from it, add `e-hide-value` class to Color Picker using the [`CssClass`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Inputs.SfColorPicker~CssClass.html) property.

In the following sample, the Color Picker is rendered without input area.

```csharp
@using Syncfusion.Blazor.Inputs

<h4>Choose a color</h4>
<SfColorPicker ModeSwitcher="false" CssClass="e-hide-value"></SfColorPicker>
```

Output be like
![color-picker](./../images/hide-input.png)

## Custom Handle

Color Picker handle shape and UI can be customized. Here, we have customized the handle as svg icon. The same way you can customize the handle based on your requirement.

The following sample show the customized Color Picker handle.

```csharp

@using Syncfusion.Blazor.Inputs

<SfColorPicker Value="#344aae" CssClass="e-custom-picker" ModeSwitcher="false"></SfColorPicker>

<style>
    .e-color-picker-tooltip.e-popup.e-popup-open {
    display: none;
    }
    .e-custom-picker .e-container .e-handler {
    background: transparent url('data:image/svg+xml;base64,PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0idXRmLTgiPz4KPCEtLSBHZW5lcmF0b3I6IEFkb2JlIElsbHVzdHJhdG9yIDIyLjEuMCwgU1ZHIEV4cG9ydCBQbHVnLUluIC4gU1ZHIFZlcnNpb246IDYuMDAgQnVpbGQgMCkgIC0tPgo8c3ZnIHZlcnNpb249IjEuMSIgaWQ9IkxheWVyXzEiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyIgeG1sbnM6eGxpbms9Imh0dHA6Ly93d3cudzMub3JnLzE5OTkveGxpbmsiIHg9IjBweCIgeT0iMHB4IgoJIHZpZXdCb3g9IjAgMCAxNiAxNiIgc3R5bGU9ImVuYWJsZS1iYWNrZ3JvdW5kOm5ldyAwIDAgMTYgMTY7IiB4bWw6c3BhY2U9InByZXNlcnZlIj4KPHN0eWxlIHR5cGU9InRleHQvY3NzIj4KCS5zdDB7ZmlsbDojRkZGRkZGO30KPC9zdHlsZT4KPGc+Cgk8cG9seWdvbiBjbGFzcz0ic3QwIiBwb2ludHM9IjE2LDYgMTAsNiAxMCwwIDYsMCA2LDYgMCw2IDAsMTAgNiwxMCA2LDE2IDEwLDE2IDEwLDEwIDE2LDEwIAkiLz4KPC9nPgo8cGF0aCBkPSJNMTAsNlYwSDZ2NkgwdjRoNnY2aDR2LTZoNlY2SDEweiBNMTUsOUg5djZIN1Y5SDFWN2g2VjFoMnY2aDZWOXoiLz4KPC9zdmc+Cg==');
    font-size: 16px;
    height: 16px;
    line-height: 16px;
    margin-left: -8px;
    margin-top: -8px;
    border: none;
    box-shadow: none;
    width: 16px;
    }
</style>

```

Output be like
![color-picker](./../images/cp-custom-handle.png)