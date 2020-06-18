---
title: "Customize RadioButton Appearance"
component: "RadioButton"
description: "RadioButton how to section, name and value in form submit, customize RadioButton appearance."
---

# Customize RadioButton Appearance

You can customize the appearance of the RadioButton component by using the CSS rules.
Define own CSS rules according to your requirement and assign the class name to the [`cssClass`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.EJ2.RazorComponents~Syncfusion.EJ2.RazorComponents.Buttons.EjsRadioButton~CssClass.html) property.

The background and border color of the RadioButton is customized through the custom classes to create the primary, success, info, warning, and danger type of RadioButton.

`Index.razor`

```csharp

<ul>
    <li>
        <EjsRadioButton ID="radio1" Label="Primary" Name="custom" CssClass="e-primary"></EjsRadioButton>
    </li>
    <li>
        <EjsRadioButton ID="radio2" Label="Success" Name="custom" CssClass="e-success"></EjsRadioButton>
    </li>
    <li>
        <EjsRadioButton ID="radio3" Label="Info" Name="custom" checked="true" CssClass="e-info"></EjsRadioButton>
    </li>
    <li>
        <EjsRadioButton ID="radio4" Label="Warning" Name="custom" CssClass="e-warning"></EjsRadioButton>
    </li>
    <li>
        <EjsRadioButton ID="radio5" Label="Danger" Name="custom" CssClass="e-danger"></EjsRadioButton>
    </li>
</ul>

  ```

  `_Host.cshtml`

   ```html

   style>

    .e-radio-wrapper {
        margin-top: 18px;
    }

    li {
        list-style: none;
    }

    .e-radio:checked + .e-success::after { /* csslint allow: adjoining-classes */
        background-color: #689f38;
    }

    .e-radio:checked:focus + .e-success::after, .e-radio:checked + .e-success:hover::after { /* csslint allow: adjoining-classes */
        background-color: #449d44;
    }

    .e-radio:checked + .e-success::before {
        border-color: #689f38;
    }

    .e-radio:checked:focus + .e-success::before, .e-radio:checked + .e-success:hover::before { /* csslint allow: adjoining-classes */
        border-color: #449d44;
    }

    .e-radio + .e-success:hover::before {
        border-color: #b1afaf
    }

    .e-radio:checked + .e-info::after { /* csslint allow: adjoining-classes */
        background-color: #2196f3;
    }

    .e-radio:checked:focus + .e-info::after, .e-radio:checked + .e-info:hover::after { /* csslint allow: adjoining-classes */
        background-color: #0b7dda;
    }

    .e-radio:checked + .e-info::before {
        border-color: #2196f3;
    }

    .e-radio:checked:focus + .e-info::before, .e-radio:checked + .e-info:hover::before {
        border-color: #0b7dda;
    }

    .e-radio + .e-info:hover::before {
        border-color: #b1afaf
    }

    .e-radio:checked + .e-warning::after { /* csslint allow: adjoining-classes */
        background-color: #ef6c00;
    }

    .e-radio:checked:focus + .e-warning::after, .e-radio:checked + .e-warning:hover::after { /* csslint allow: adjoining-classes */
        background-color: #cc5c00;
    }

    .e-radio:checked + .e-warning::before {
        border-color: #ef6c00;
    }

    .e-radio:checked:focus + .e-warning::before, .e-radio:checked + .e-warning:hover::before {
        border-color: #cc5c00;
    }

    .e-radio + .e-warning:hover::before {
        border-color: #b1afaf
    }

    .e-radio:checked + .e-danger::after { /* csslint allow: adjoining-classes */
        background-color: #d84315;
    }

    .e-radio:checked:focus + .e-danger::after, .e-radio:checked + .e-danger:hover::after { /* csslint allow: adjoining-classes */
        background-color: #ba330a;
    }

    .e-radio:checked + .e-danger::before {
        border-color: #d84315;
    }

    .e-radio:checked:focus + .e-danger::before, .e-radio:checked + .e-danger:hover::before {
        border-color: #ba330a;
    }

    .e-radio + .e-danger:hover::before {
        border-color: #b1afaf
    }
</style>

  ```