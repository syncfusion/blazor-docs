---
title: "Blazor In-place Editor | featured components list"
component: "In-place Editor"
description: "This section provides the list of Blazor components supported by Blazor In-place Editor as a built-in and injectable module."
---

# List of components

In-place Editor renders various components based on the `Type` property and it have built-in and injectable components. To use injectable components, inject the required modules into `InPlaceEditor`. By default, the `Type` property set to `Text` and render the `TextBox`.

The following table explains Injectable components module name and built-in components and their types.

| **Injectable Components** | **Built in Components** |
|-----------------------|---------------------|
| [AutoComplete](../autocomplete/getting-started/)  (`AutoComplete`)        | [TextBox](../textbox/getting-started/)  (`Text`)             |
| [ComboBox](../combobox/getting-started/)  (`ComboBox`)              | [DatePicker](../datepicker/getting-started/)  (`Date`)        |
| [MultiSelect](../multiselect/getting-started/)   (`MultiSelect`)        | [DateTimePicker](../datetimepicker/getting-started/)   (`DateTime`)     |
| [TimePicker](../timepicker/getting-started/)   (`Time`)         | [DropDownList](../dropdownlist/getting-started/)  (`DropDownList`)      |
| [DateRangePicker](../daterangepicker/getting-started/)   (`DateRange`)       | [MaskedTextBox](../maskedtextbox/getting-started/)   (`Mask`)      |
| [Slider](../slider/getting-started/)   (`Slider`)             | [NumericTextBox](../numerictextbox/getting-started/)   (`Numeric`)    |
| [Rte](../rich-text-editor/getting-started/)     (`RTE`)  |   [ColorPicker](../color-picker/getting-started/)    (`Color`)    |

In the following example, built-in and injectable based In-place Editor components are rendered as follows.

```csharp

@using Syncfusion.Blazor.InPlaceEditor
@using Syncfusion.Blazor.RichTextEditor

<h3> Built-in Controls </h3>
<table class="table-section">
    <tr>
        <td class="col-lg-6 col-md-6 col-sm-6 col-xs-6 control-title"> DatePicker </td>
        <td class="col-lg-6 col-md-6 col-sm-6 col-xs-6">
            <SfInPlaceEditor Mode="RenderMode.Inline" Type="InputType.Date" Value="@DateValue" Model="@DateModel">
            </SfInPlaceEditor>
        </td>
    </tr>
    <tr>
        <td class="col-lg-6 col-md-6 col-sm-6 col-xs-6 control-title"> DateTimePicker </td>
        <td class="col-lg-6 col-md-6 col-sm-6 col-xs-6">
            <SfInPlaceEditor Mode="RenderMode.Inline" Type="InputType.DateTime" Value="@DateTimeValue" Model="@DateTimeModel">
            </SfInPlaceEditor>
        </td>
    </tr>
    <tr>
        <td class="col-lg-6 col-md-6 col-sm-6 col-xs-6 control-title"> DropDownList </td>
        <td class="col-lg-6 col-md-6 col-sm-6 col-xs-6">
            <SfInPlaceEditor Mode="RenderMode.Inline" Type="InputType.DropDownList" Value="@DropValue" Model="@DropModel">
            </SfInPlaceEditor>
        </td>
    </tr>
    <tr>
        <td class="col-lg-6 col-md-6 col-sm-6 col-xs-6 control-title"> MaskedTextBox </td>
        <td class="col-lg-6 col-md-6 col-sm-6 col-xs-6">
            <SfInPlaceEditor Mode="RenderMode.Inline" Type="InputType.Mask" Value="@MaskValue" Model="@MaskedModel">
            </SfInPlaceEditor>
        </td>
    </tr>
    <tr>
        <td class="col-lg-6 col-md-6 col-sm-6 col-xs-6 control-title"> NumericTextBox </td>
        <td class="col-lg-6 col-md-6 col-sm-6 col-xs-6">
            <SfInPlaceEditor Mode="RenderMode.Inline" Type="InputType.Numeric" Value="@NumericValue" Model="@NumericModel">
            </SfInPlaceEditor>
        </td>
    </tr>
    <tr>
        <td class="col-lg-6 col-md-6 col-sm-6 col-xs-6 control-title"> TextBox </td>
        <td class="col-lg-6 col-md-6 col-sm-6 col-xs-6">
            <SfInPlaceEditor Mode="RenderMode.Inline" Type="InputType.Text" Value="@TextValue" SubmitOnEnter="true" Model="@TextModel">
            </SfInPlaceEditor>
        </td>
    </tr>
</table>
<h3> Injectable Controls </h3>
<table class="table-section">
    <tr>
        <td class="col-lg-6 col-md-6 col-sm-6 col-xs-6 control-title"> AutoComplete </td>
        <td class="col-lg-6 col-md-6 col-sm-6 col-xs-6">
            <SfInPlaceEditor Mode="RenderMode.Inline" Type="InputType.AutoComplete" Value="@AutocompValue" SubmitOnEnter="true" Model="@AutocompModel">
            </SfInPlaceEditor>
        </td>
    </tr>
    <tr>
        <td class="col-lg-6 col-md-6 col-sm-6 col-xs-6 control-title"> ColorPicker </td>
        <td class="col-lg-6 col-md-6 col-sm-6 col-xs-6">
            <SfInPlaceEditor Mode="RenderMode.Inline" Type="InputType.Color" Value="@ColorValue" SubmitOnEnter="true">
            </SfInPlaceEditor>
        </td>
    </tr>
    <tr>
        <td class="col-lg-6 col-md-6 col-sm-6 col-xs-6 control-title"> ComboBox </td>
        <td class="col-lg-6 col-md-6 col-sm-6 col-xs-6">
            <SfInPlaceEditor Mode="RenderMode.Inline" Type="InputType.ComboBox" Value="@ComboBoxValue" SubmitOnEnter="true" Model="@ComboBoxModel">
            </SfInPlaceEditor>
        </td>
    </tr>
    <tr>
        <td class="col-lg-6 col-md-6 col-sm-6 col-xs-6 control-title"> DateRangePicker </td>
        <td class="col-lg-6 col-md-6 col-sm-6 col-xs-6">
            <SfInPlaceEditor Mode="RenderMode.Inline" Type="InputType.DateRange" Value="@DateRangeValue" SubmitOnEnter="true" Model="@DateRangeModel">
            </SfInPlaceEditor>
        </td>
    </tr>
    <tr>
        <td class="col-lg-6 col-md-6 col-sm-6 col-xs-6 control-title"> MultiSelect </td>
        <td class="col-lg-6 col-md-6 col-sm-6 col-xs-6">
            <SfInPlaceEditor Mode="RenderMode.Inline" Type="InputType.MultiSelect" Value="@MultiValue" SubmitOnEnter="true" Model="@MultiModel">
            </SfInPlaceEditor>
        </td>
    </tr>
    <tr>
        <td class="col-lg-6 col-md-6 col-sm-6 col-xs-6 control-title"> RTE </td>
        <td class="col-lg-6 col-md-6 col-sm-6 col-xs-6">
            <SfInPlaceEditor Mode="RenderMode.Inline" Type="InputType.RTE" Value="@RteValue" SubmitOnEnter="true" Model="@RteModel">
            </SfInPlaceEditor>
        </td>
    </tr>
    <tr>
        <td class="col-lg-6 col-md-6 col-sm-6 col-xs-6 control-title"> Slider </td>
        <td class="col-lg-6 col-md-6 col-sm-6 col-xs-6">
            <SfInPlaceEditor Mode="RenderMode.Inline" Type="InputType.Slider" Value="@SliderValue" SubmitOnEnter="true">
            </SfInPlaceEditor>
        </td>
    </tr>
    <tr>
        <td class="col-lg-6 col-md-6 col-sm-6 col-xs-6 control-title"> TimePicker </td>
        <td class="col-lg-6 col-md-6 col-sm-6 col-xs-6">
            <SfInPlaceEditor Mode="RenderMode.Inline" Type="InputType.Time" Value="@TimeValue" SubmitOnEnter="true" Model="@TimeModel">
            </SfInPlaceEditor>
        </td>
    </tr>
</table>

<style>
    body {
        padding: 20px 0
    }

    .control-title {
        font-weight: 600;
        padding-right: 20px;
    }

    .control-title {
        width: 50%;
    }

    td {
        height: 80px;
    }

    tr td:first-child {
        text-align: right;
    }

    tr td:last-child {
        text-align: left;
    }

    .table-section {
        margin: 0 auto;
    }

    h3 {
        text-align: center;
    }
</style>

@code {
    public DateTime DateValue { get; set; } = new DateTime(DateTime.Now.Year, DateTime.Now.Month, DateTime.Now.Day);
    public DateTime DateTimeValue { get; set; } = DateTime.Now;
    public DateTime[] DateRangeValue { get; set; } = new DateTime[] { DateTime.Now, DateTime.Now.AddDays(20) };
    public DateTime TimeValue { get; set; } = DateTime.Now;

    public string MaskValue = "123-345-678";
    public string NumericValue = "10";
    public string TextValue = "Andrew";
    public string DropValue = "Android";
    public string AutocompValue = "Android";
    public string ColorValue = "#81aefd";
    public string ComboBoxValue = "Android";
    public string[] MultiValue = new string[] { "Android" };
    public string RteValue = "<p>Enter your content here</p>";
    public double SliderValue = 20;

    public DatePickerModel DateModel = new DatePickerModel()
    {
        Placeholder = "Select date"
    };
    public DateTimePickerModel<DateTime> DateTimeModel = new DateTimePickerModel<DateTime>()
    {
        Placeholder = "Select date"
    };
    public DropDownListModel<string> DropModel = new DropDownListModel<string>()
    {
        Placeholder = "Android",
        DataSource = new string[] { "Android", "JavaScript", "jQuery", "TypeScript", "Angular", "React", "Vue", "Ionic" }
    };
    public MaskedTextBoxModel MaskedModel = new MaskedTextBoxModel()
    {
        Mask = "000-000-000"
    };
    public NumericTextBoxModel<string> NumericModel = new NumericTextBoxModel<string>()
    {
        Placeholder = "Enter number"
    };
    public TextBoxModel TextModel = new TextBoxModel()
    {
        Placeholder = "Enter some text"
    };
    public AutoCompleteModel<string> AutocompModel = new AutoCompleteModel<string>()
    {
        Placeholder = "Select frameworks",
        DataSource = new string[] { "Android", "JavaScript", "jQuery", "TypeScript", "Angular", "React", "Vue", "Ionic" }
    };
    public ComboBoxModel<string> ComboBoxModel = new ComboBoxModel<string>()
    {
        Placeholder = "Select frameworks",
        DataSource = new string[] { "Android", "JavaScript", "jQuery", "TypeScript", "Angular", "React", "Vue", "Ionic" }
    };
    public DateRangePickerModel DateRangeModel = new DateRangePickerModel()
    {
        Placeholder = "Select date"
    };
    public MultiSelectModel<string> MultiModel = new MultiSelectModel<string>()
    {
        Placeholder = "Select frameworks",
        DataSource = new string[] { "Android", "JavaScript", "jQuery", "TypeScript", "Angular", "React", "Vue", "Ionic" }
    };
    public RichTextEditorModel RteModel = new RichTextEditorModel()
    {
        Placeholder = "Enter your content here"
    };
    public TimePickerModel<string> TimeModel = new TimePickerModel<string>()
    {
        Placeholder = "Select date"
    };
}

```

The output will be as follows.

![controls](./images/controls.png)

## Model configuration

Component properties and events can be customized using the In-place Editor `Model` property.

In the following code, the `Type` defined as the `Date` and `DatePicker` properties are configured using the `Model` property to customize the `DatePicker` component at In-place Editor.

```csharp

    private DatePickerModel DateData = new DatePickerModel
    {
        Placeholder = "Select date",
        ShowTodayButton = true
    };

```

`Index.razor`

```csharp

@using Syncfusion.Blazor.InPlaceEditor

<div>
    <SfInPlaceEditor Mode="@RenderMode.Inline" Type="@InputType.Date" Value="@DateValue" Model="@DateModel"> </SfInPlaceEditor>
</div>

@code {
    public DateTime DateValue { get; set; } = new DateTime(DateTime.Now.Year, DateTime.Now.Month, 11);

    public DatePickerModel DateModel = new DatePickerModel
    {
        Placeholder = "Select date",
        ShowTodayButton = true
    };
}


```

## See Also

* [HTML5 components](./integration/)