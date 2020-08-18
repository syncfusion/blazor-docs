---
title: "Blazor Rich Text Editor | Rich Text Editor Form support"
component: "Rich Text Editor"
description: "This section for Blazor Rich Text Editor component demonstrates that how to work with form and it's validation."
---

# Form validation

This following sample demonstrate how to get the Rich Text Editor validation error message in button click.

## Render the editor in a form

Render the Rich Text Editor in form as below.

```csharp

@using Syncfusion.Blazor
@using Syncfusion.Blazor.RichTextEditor
@using System.ComponentModel.DataAnnotations;

<EditForm Model="@MyForm">
    <DataAnnotationsValidator />
    <p>
        <label for="description">Enter Text</label>
        <SfRichTextEditor @bind-Value="@MyForm.Description" ShowCharCount="true" MaxLength="200">
        </SfRichTextEditor>
        <ValidationMessage For="@(() => MyForm.Description)"></ValidationMessage>
    </p>
    <button class="e-btn" type="submit">Submit</button>
</EditForm>


@code {
    private Form MyForm = new Form();
    public class Form
    {
        [Required]
        public string Description { get; set; } = "<div>Rich Text Editor allows to insert images from online source as well as local computer where you want to insert the image in your content.</div>";
    }
}

```

The output will be as follows.

![Form](./images/default-validation.png)

## Validation Rules

The Rich Text Editor is a textarea control. The Rich Text Editor also provides the functionality of character count and its validation. So, you can validate the Rich Text Editor's value on form submission by applying Validation Rules and Validation Message to the Rich Text Editor.

| Rules | Description |
|----------------|---------|
| Required | Requires value for the Rich Text Editor control.|
| MinLength | Requires the value to be of given minimum characters count.|
| MaxLength | Requires the value to be of given maximum characters count.|

This sample is used to validate form using the obtrusive Validation. Type the values in Rich Text Editor and the form enables the validation with the formvalidator rules by clicking on the submit externally. All rules are validated by the formvalidator rules.

```csharp

@using Syncfusion.Blazor
@using Syncfusion.Blazor.RichTextEditor
@using System.ComponentModel.DataAnnotations;

<EditForm Model="@MyForm">
    <DataAnnotationsValidator />
    <p>
        <label for="description">Enter Text</label>
        <SfRichTextEditor @bind-Value="@MyForm.Description" ShowCharCount="true" MaxLength="200" Placeholder="Type something">
            <RichTextEditorToolbarSettings items="@Tools"></RichTextEditorToolbarSettings>
        </SfRichTextEditor>
        <ValidationMessage For="@(() => MyForm.Description)"></ValidationMessage>
    </p>
    <button class="e-btn" type="submit">Submit</button>
</EditForm>

@code {
    public object[] Tools = new object[] {
        "Bold", "Italic", "Underline", "|",
        "Formats", "Alignments", "|", "CreateLink", "Image", "|","SourceCode", "|", "Undo", "Redo"
    };
    private Form MyForm = new Form();
    public class Form
    {
        [Required]
        [MinLength(20, ErrorMessage = "Please enter at least 20 characters.")]
        public string Description { get; set; } = "<div>Rich Text Editor allows to insert images from online source as well as local computer where you want to insert the image in your content.</div>";
    }
}

```

The output will be as follows.

![Form validation](./images/validation-message.png)

## Validation Message

The default error message for a rule can be customizable by defining it along with concern rule object as follows.

```csharp

@using Syncfusion.Blazor
@using Syncfusion.Blazor.RichTextEditor
@using System.ComponentModel.DataAnnotations;

<EditForm Model="@MyForm">
    <DataAnnotationsValidator />
    <p>
        <label for="description">Enter Text</label>
        <SfRichTextEditor @bind-Value="@MyForm.Description" ShowCharCount="true" MaxLength="200" Placeholder="Type something">
        <RichTextEditorToolbarSettings items="@Tools"></RichTextEditorToolbarSettings>
        </SfRichTextEditor>
        <ValidationMessage For="@(() => MyForm.Description)"></ValidationMessage>
    </p>
    <button class="e-btn" type="submit">Submit</button>
</EditForm>

@code {
    public object[] Tools = new object[] {
        "Bold", "Italic", "Underline", "|",
        "Formats", "Alignments", "|", "CreateLink", "Image", "|","SourceCode", "|", "Undo", "Redo"
    };
    private Form MyForm = new Form();
    public class Form
    {
        [Required]
        [MinLength(10, ErrorMessage = "Please enter at least 10 characters.")]
        [MaxLength(100, ErrorMessage = "Maximum 200 characters only")]
        public string Description { get; set; } = "<div>Rich Text Editor allows to insert images from online source as well as local computer where you want to insert the image in your content.</div>";
    }
}

```

## Custom Placement of Validation Message

The FormValidation error message can be placed from default position to desired custom location.

```csharp

@using Syncfusion.Blazor
@using Syncfusion.Blazor.RichTextEditor
@using System.ComponentModel.DataAnnotations;

<EditForm Model="@MyForm">
    <p>
        <ValidationMessage For="@(() => MyForm.Description)"></ValidationMessage>
    </p>
    <DataAnnotationsValidator />
    <p>
        <label for="description">Enter Text</label>
        <SfRichTextEditor @bind-Value="@MyForm.Description" ShowCharCount="true" MaxLength="200" Placeholder="Type something">
            <RichTextEditorToolbarSettings items="@Tools"></RichTextEditorToolbarSettings>
        </SfRichTextEditor>
    </p>
    <button class="e-btn" type="submit">Submit</button>
</EditForm>

@code {
    public object[] Tools = new object[] {
        "Bold", "Italic", "Underline", "|",
        "Formats", "Alignments", "|", "CreateLink", "Image", "|","SourceCode", "|", "Undo", "Redo"
    };
    private Form MyForm = new Form();
    public class Form
    {
        [Required(ErrorMessage = "RTE: value is required")]
        [MinLength(15, ErrorMessage = "RTE: Need atleast 15 character length")]
        [MaxLength(100, ErrorMessage = "RTE: Maximum 200 characters only")]
        public string Description { get; set; } = "<div>Rich Text Editor allows to insert images from online source as well as local computer where you want to insert the image in your content.</div>";
    }
}

```

The output will be as follows.

![Custom placement](./images/custom-placement.png)