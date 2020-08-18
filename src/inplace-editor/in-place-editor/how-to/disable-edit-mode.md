---
title: "Blazor In-place Editor | Disable edit mode"
component: "In-place Editor"
description: "This how-to section explains disabling or enabling the edit mode of the Blazor In-place Editor component dynamically."
---

# Disable the edit mode specifically

The edit mode of In-place Editor can be disabled by setting the `Disabled` property value to `true`. In the following example, when check or uncheck the checkbox, In-place Editor component will disable or enable the edit mode.

```csharp

@using Syncfusion.Blazor.InPlaceEditor
@using Syncfusion.Blazor.Buttons

<table class="table-section">
    <tr>
        <td> Disabled: </td>
        <td>
            <SfCheckBox @bind-Checked="Checked" Label="Disable"></SfCheckBox>
        </td>
    </tr>
    <tr>
        <td class="sample-td"> Enter your name: </td>
        <td class="sample-td">
            <SfInPlaceEditor Mode="RenderMode.Inline" Disabled="Checked" Type="InputType.Text" Value="TextValue" SubmitOnEnter="true" Model="TModel">
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
    public string TextValue { get; set; } = "Andrew";
    public bool Checked { get; set; } = true;

    public TextBoxModel TModel = new TextBoxModel()
    {
        Placeholder = "Enter some text"
    };

}
```
