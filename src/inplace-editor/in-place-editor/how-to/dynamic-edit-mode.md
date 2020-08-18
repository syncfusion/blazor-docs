---
title: "Blazor In-place Editor | Edit mode on page load"
component: "In-place Editor"
description: "This how-to section explains changing the default mode to edit mode in the Blazor In-place Editor component on the page load itself."
---

# Dynamically move input to edit mode

At component initial load, if you want to open editor state without interacting In-place Editor input element, it can be achieved by configuring the `EnableEditMode` property to `true`.

In the following example, editor opened at initial load and when toggling a checkbox, it will remove or open the editor.

```csharp
@using Syncfusion.Blazor.InPlaceEditor
@using Syncfusion.Blazor.Buttons


<table class="table-section">
    <tr>
        <td> EnableEditMode: </td>
        <td>
            <SfCheckBox Checked="@EditMode" Label="Disable" ValueChange="@onChange" TChecked="bool"></SfCheckBox>
        </td>
    </tr>
    <tr>
        <td class="sample-td"> Enter your name: </td>
        <td class="sample-td">
            <SfInPlaceEditor Mode="RenderMode.Inline" EnableEditMode="EditModeEnable" ActionOnBlur="ActionBlur.Ignore" Type="InputType.Text" Value="TextValue" SubmitOnEnter="true" Model="TModel">
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
    public bool EditModeEnable { get; set; } = true;
    public string TextValue = "Andrew";
    private bool EditMode { get; set; } = false;

     public TextBoxModel TModel = new TextBoxModel()
    {
        Placeholder = "Enter some text"
    };

    private void onChange(Syncfusion.Blazor.Buttons.ChangeEventArgs<bool> args)
    {
        this.EditMode = args.Checked;
        this.EditModeEnable = !args.Checked;
        this.StateHasChanged();
    }
}

```