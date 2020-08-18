---
title: "Blazor In-place Editor | Save and remove button config"
component: "In-place Editor"
description: "This section explains how to configure, save, and remove button with its properties, template, and customize its behavior for Blazor In-place Editor."
---

# Buttons

The In-place Editor had an action for save and cancel using buttons. The `SaveButton` and `CancelButton` properties accept the `ButtonModel` objects for customizing the save and cancel button properties.

Buttons can be shown or hidden by setting a Boolean value to the `ShowButtons` property.

> Without buttons, value will be processed via the following ways.

* **actionOnBlur**: By clicking outside, the editor component get focus out and do action based on this property value.
* **submitOnEnter**: Pressing `Enter` key it performs the submit action, if this property set to `true`.

In the following sample, the `Content` and `CssClass` properties of `Button` value assigned to the `SaveButton` and `CancelButton` properties to customize its appearance. Also check or uncheck the checkbox buttons rendered or removed from the editor.

To restrict, either save or cancel button rendering into a DOM, simply pass empty object `{}` in the  `SaveButton` or `CancelButton` properties.

> For more details about buttons, refer this documentation [section](../button/).

```csharp

@using Syncfusion.Blazor.InPlaceEditor
@using Syncfusion.Blazor.Buttons

<table class="table-section">
    <tr>
        <td> Submit on Enter: </td>
        <td>
            <SfCheckBox Checked="@SubmitOnEnter" Label="Show" ValueChange="OnChange" TChecked="bool"></SfCheckBox>
        </td>
    </tr>
    <tr>
        <td class="sample-td">Enter your name: </td>
        <td class="sample-td">
            <SfInPlaceEditor Mode="RenderMode.Inline" Type="InputType.Text" Value="TextValue" SubmitOnEnter="SubmitOnEnter" SaveButton="SaveBtn" CancelButton="CancelBtn" Model="TModel">
            </SfInPlaceEditor>
        </td>
    </tr>
</table>

<style>
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
    public bool SubmitOnEnter { get; set; } = true;
    public string TextValue = "Andrew";

    public TextBoxModel TModel = new TextBoxModel()
    {
        Placeholder = "Enter some text"
    };
    private void OnChange(Syncfusion.Blazor.Buttons.ChangeEventArgs<bool> args)
    {
        this.SubmitOnEnter = args.Checked;
        this.StateHasChanged();
    }

    public ButtonModel SaveBtn = new ButtonModel()
    {
        Content = "OK",
        CssClass = "e-outline"
    };

    public ButtonModel CancelBtn = new ButtonModel()
    {
        Content = "Cancel",
        CssClass = "e-outline"
    };
}

```

The output will be as follows.

![showButton](./images/show-buttons.png)

## See Also

* [In-place editor buttons](./how-to/dynamic-edit-mode)