---
title: "Blazor In-place Editor | Custom Animation for a popup"
component: "In-place Editor"
description: "This how-to section explains applying animation to the popup by customizing it dynamically in the Blazor In-place Editor component."
---

# Set custom animation for popup mode

In popup mode, the In-place Editor rendered with the Blazor `Tooltip` component. You can use tooltip properties and events to customize the popup by configure properties into the `Model` property inside the `PopupSettings` API.

In the following example, popup animation can be customized by passing animation effect using the `Model` property and the dynamic animation effect changes configured from the Blazor `DropDownList` component `ValueChange` event.

```csharp

@using Syncfusion.Blazor.InPlaceEditor
@using Syncfusion.Blazor.DropDowns

<div id='container'>
    <table class="table-section">
        <tr>
            <td> Open Animation: </td>
            <td>
                <SfDropDownList PopupHeight="150px" Value="DropdownValue" Placeholder="Select a animate type" DataSource="OpenAnimateData">
                    <DropDownListEvents ValueChange="OnChange" TValue="string"></DropDownListEvents>
                    <DropDownListFieldSettings Text="Text"></DropDownListFieldSettings>
                </SfDropDownList>
            </td>
        </tr>
        <tr>
            <td class="sample-td"> Enter your name: </td>
            <td class="sample-td">
                <SfInPlaceEditor Mode="RenderMode.Popup" Type="InputType.Text" PopupSettings="InplacePopup" Value="TextValue" Model="TModel">
                </SfInPlaceEditor>
            </td>
        </tr>
    </table>
</div>

<style>
    #container {
        display: flex;
        justify-content: center;
    }

    .table-section {
        margin: 0 auto;
    }

    tr td:first-child {
        text-align: right;
        padding-right: 20px;
    }

    .sample-td {
        padding-top: 10px;
        min-width: 230px;
        height: 100px;
    }
</style>

@code {
    public class DropDownFields
    {
        public string Text { get; set; }
    }
    public List<DropDownFields> OpenAnimateData = new List<DropDownFields>()
{
        new DropDownFields(){ Text= "None" },
        new DropDownFields(){ Text= "FadeIn" },
        new DropDownFields(){ Text= "FadeZoomIn" },
        new DropDownFields() { Text= "ZoomIn" }
    };

    public string TextValue = "Andrew";
    public string DropdownValue = "ZoomIn";

    public TextBoxModel TModel = new TextBoxModel()
    {
        Placeholder = "Enter some text"
    };

    public void OnChange(ChangeEventArgs<string> args)
    {
        InplacePopup = new InPlaceEditorPopupSettings()
        {
            Model = new
            {
                animation = new
                {
                    open = new
                    {
                        effect = args.Value,
                        duration = 1000,
                        delay = 0
                    }
                }
            }
        };
    }

    public InPlaceEditorPopupSettings InplacePopup = new InPlaceEditorPopupSettings()
    {
        Model = new
        {
            animation = new
            {
                open = new
                {
                    effect = "ZoomIn",
                    duration = 1000,
                    delay = 0
                }
            }
        }
    };
}

```
