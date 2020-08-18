---
title: "Blazor In-place Editor | Configure the basic properties"
component: "In-place Editor"
description: "This section explains how to configure various render modes, display modes, and actions on editing and focus out in the Blazor In-place Editor."
---

# Configuration

## Rendering modes

This section explains the supported rendering modes of the In-place Editor. The possible Rendering modes are:

    * Popup
    * Inline

> By default, `Popup` mode will be rendered when opening an editor.

* For `Popup` mode, the editable container displays as like tooltip or popover above the element.

* For `Inline` mode, the editable container displays as instead of the element. To render `Inline` mode while opening the editor, specify `Mode` as `Inline`.

In the following code block, the In-place Editor renders with `Inline` mode. You can dynamically switch into another mode by changing the drop-down item value.

```csharp

@using Syncfusion.Blazor.InPlaceEditor
@using Syncfusion.Blazor.DropDowns

<table class="table-section">
    <tr>
        <td> Mode: </td>
        <td>
            <SfDropDownList Value="DropdownValue" Width="auto" Placeholder="Select Mode" DataSource="Modes">
                <DropDownListEvents ValueChange="OnChange" TValue="string"></DropDownListEvents>
                <DropDownListFieldSettings Text="Text"></DropDownListFieldSettings>
            </SfDropDownList>
        </td>
    </tr>
    <tr>
        <td class="sample-td">Enter your name: </td>
        <td class="sample-td">
            <SfInPlaceEditor Mode="InplaceMode" Type="InputType.Text" Value="TextValue" SubmitOnEnter="true" Model="TModel">
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
    public RenderMode InplaceMode = RenderMode.Inline;
    public string TextValue = "Andrew";
    public string DropdownValue = "Inline";

    public class DropDownFields
    {
        public string Text { get; set; }
    }
    public List<DropDownFields> Modes = new List<DropDownFields>()
{
        new DropDownFields(){ Text= "Inline" },
        new DropDownFields(){ Text= "Popup" },

    };

    public TextBoxModel TModel = new TextBoxModel()
    {
        Placeholder = "Enter some text"
    };

    private void OnChange(ChangeEventArgs<string> args)
    {
        this.InplaceMode = (args.Value.ToString() == "Popup" ? RenderMode.Popup : RenderMode.Inline);
        this.StateHasChanged();
    }
}

```

### Pop-up customization

In-place Editor popup mode can be customized by using the `Title` and `Model` properties in `PopupSettings` API.

Popup mode rendered by using the Blazor Tooltip component, so you can use tooltip properties and events to customize the behavior of popup via the `Model` property of `PopupSettings` API.

> For more details, refer to the tooltip documentation [section](../tooltip/).

In the following sample, popup `Title` and `Position` customized using the `PopupSettings` property. All possible tooltip position data is configured in the drop-down, if we change drop down item, selected value bound to `Model` property and applied it to [Tooltip](../tooltip/) component. `Tooltip` have following position options.

* TopLeft
* TopCenter
* TopRight
* BottomLeft
* BottomCenter
* BottomRight
* LeftTop
* LeftCenter
* LeftBottom
* RightTop
* RightCenter
* RightBottom

## Event actions for editing

The event action of the editor enable in the edit mode based on the `EditableOn` property, by default `Click` is assigned, the following options are also supported.

* **Click**:  The editor will be opened as single click actions.
* **DblClick**: The editor will be opened as double-click actions and it is not applicable for edit icon.
* **EditIconClick**: Disables the editing of event action of input and allows users to edit only through edit icon.

> In-place Editor get focus by pressing the `tab` key from previous focusable DOM element and then by pressing `enter` key, the editor will be opened.

In the following code block, when switching drop-down item, the selected value assigned to the `EditableOn` property. If you changed to `DblClick`, the editor will open when making a double click on the input.

```csharp


@using Syncfusion.Blazor.InPlaceEditor
@using Syncfusion.Blazor.DropDowns

<table class="table-section">
    <tr>
        <td>Choose Editable Type: </td>
        <td>
            <SfDropDownList Value="DropDownValue" Width="auto" Placeholder="Select edit type" DataSource="Modes">
                <DropDownListFieldSettings Text="Text"></DropDownListFieldSettings>
                <DropDownListEvents ValueChange="OnChange" TValue="string"></DropDownListEvents>
            </SfDropDownList>
        </td>
    </tr>
    <tr>
        <td class="sample-td">Enter your name: </td>
        <td class="sample-td">
            <SfInPlaceEditor EditableOn="EditableOn" Mode="RenderMode.Inline" Type="InputType.Text" Value="TextValue" SubmitOnEnter="true" Model="TModel">
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
    public string TextValue = "Andrew";
    public string DropDownValue = "Click";
    public EditableType EditableOn = EditableType.Click;

    public class DropDownFields
    {
        public string Text { get; set; }
    }

    public List<DropDownFields> Modes = new List<DropDownFields>
{
        new DropDownFields() { Text= "Click" },
        new DropDownFields() { Text= "DblClick" },
        new DropDownFields() { Text= "EditIconClick" }
    };

    public TextBoxModel TModel = new TextBoxModel()
    {
        Placeholder = "Enter some text"
    };


    private void OnChange(ChangeEventArgs<string> args)
    {
        if (args.Value.ToString() == "Click")
        {
            this.EditableOn = EditableType.Click;
        }
        else if (args.Value.ToString() == "DblClick")
        {
            this.EditableOn = EditableType.DblClick;
        }
        else
        {
            this.EditableOn = EditableType.EditIconClick;
        }
        this.StateHasChanged();
    }
}

```

## Action on focus out

Action to be performed when the user clicks outside the container, that means focusing out of editable content and it can be handled by the `ActionOnBlur` property, by default `Submit` assigned. It also has the following options.

* **Cancel**: Cancels the editing and resets the old content.
* **Submit**: Submits the edited content to the server.
* **Ignore**: No action is performed with this type and allows to edit multiple editors.

In the following code block, when switching drop-down item, the selected value assigned to the `ActionOnBlur` property.

```csharp


@using Syncfusion.Blazor.InPlaceEditor
@using Syncfusion.Blazor.DropDowns

<table class="table-section">
    <tr>
        <td> ActionOnBlur: </td>
        <td>
            <SfDropDownList Value="DropdownValue" Width="auto" Placeholder="Select blur action" DataSource="Modes">
                <DropDownListFieldSettings Text="Text"></DropDownListFieldSettings>
                <DropDownListEvents ValueChange="Onchange" TValue="string"></DropDownListEvents>
            </SfDropDownList>
        </td>
    </tr>
    <tr>
        <td class="sample-td">Enter your name: </td>
        <td class="sample-td">
            <SfInPlaceEditor ActionOnBlur="OnBlur" Mode="RenderMode.Inline" Type="InputType.Text" Value="TextValue" SubmitOnEnter="true" Model="TModel">
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
    public string TextValue = "Andrew";
    public string DropdownValue = "Submit";
    public ActionBlur OnBlur = ActionBlur.Ignore;


    public class DropDownFields
    {
        public string Text { get; set; }
    }

    public List<DropDownFields> Modes = new List<DropDownFields>
{
        new DropDownFields() { Text= "Submit" },
        new DropDownFields() { Text= "Cancel" },
        new DropDownFields() { Text= "Ignore" }
    };

    public TextBoxModel TModel = new TextBoxModel()
    {
        Placeholder = "Enter some text"
    };


    private void Onchange(ChangeEventArgs<string> args)
    {
        if (args.Value.ToString() == "Submit")
        {
            this.OnBlur = ActionBlur.Submit;
        }
        else if (args.Value.ToString() == "Cancel")
        {
            this.OnBlur = ActionBlur.Cancel;
        }
        else
        {
            this.OnBlur = ActionBlur.Ignore;
        }
        this.StateHasChanged();
    }
}

```

## Display modes

By default, In-place Editor input element highlighted with a dotted underline. To remove dotted underline from input element, add `{"data-underline", "false" }` attribute at In-place Editor root element.

In the following code block, indicates the intractable and normal display modes with different examples.

```csharp


@using Syncfusion.Blazor.InPlaceEditor

<h4>Example of data-underline attribute</h4>
<table class="table-section">
    <tr>
        <td class="col-lg-6 col-md-6 col-sm-6 col-xs-6 control-title"> Intractable UI </td>
        <td class="col-lg-6 col-md-6 col-sm-6 col-xs-6">
            <SfInPlaceEditor Mode="RenderMode.Inline" Type="InputType.Text" Value="TextValue" SubmitOnEnter="true" Model="TModel">
            </SfInPlaceEditor>
        </td>
    </tr>
    <tr>
        <td class="col-lg-6 col-md-6 col-sm-6 col-xs-6 control-title"> Normal UI </td>
        <td class="col-lg-6 col-md-6 col-sm-6 col-xs-6">
            <SfInPlaceEditor Mode="RenderMode.Inline" HtmlAttributes="htmlAttribute" Type="InputType.Text" Value="TextValue" SubmitOnEnter="true" Model="TModel">
            </SfInPlaceEditor>
        </td>
    </tr>
</table>

<style>
    .table-section {
        margin: 0 auto;
    }

    td {
        padding: 20px 0;
        min-width: 230px;
        height: 100px;
    }

    .control-title {
        font-weight: 600;
        padding-right: 20px;
        text-align: right;
        width: 50%;
    }

    h4 {
        text-align: center;
    }
</style>

@code {
    public string TextValue = "Andrew";

    public TextBoxModel TModel = new TextBoxModel()
    {
        Placeholder = "Enter some text"
    };

    Dictionary<string, object> htmlAttribute = new Dictionary<string, object>() {
        {"data-underline", "false" }
    };
}
```

The output will be as follows.

![Underline](./images/under-line.png)

## See Also

* [Disable the editor](./how-to/disable-edit-mode)
* [Animate the editor during popup mode](./how-to/custom-animation)