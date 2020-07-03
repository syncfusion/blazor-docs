---
title: "Customize Radio Button Appearance"
component: "Radio Button"
description: "Radio Button how to section, name and value in form submit, customize Radio Button appearance."
---

# Customize Radio Button Appearance

You can customize the appearance of the Radio Button component by using the CSS rules.
Define own CSS rules according to your requirement and assign the class name to the [`CssClass`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Buttons.SfRadioButton~CssClass.html) property.

The background and border color of the Radio Button is customized through the custom classes to create the primary, success, info, warning, and danger type of Radio Button.

```csharp
@using Syncfusion.Blazor.Buttons

<SfRadioButton Label="Primary" Name="custom" CssClass="e-primary"></SfRadioButton><br />
<SfRadioButton Label="Success" Name="custom" CssClass="e-success"></SfRadioButton><br />
<SfRadioButton Label="Info" Name="custom" CssClass="e-info"></SfRadioButton><br />
<SfRadioButton Label="Warning" Name="custom" CssClass="e-warning"></SfRadioButton><br />
<SfRadioButton Label="Danger" Name="custom" Checked="true" CssClass="e-danger"></SfRadioButton>

<style>
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

Output be like

![Radio Button Sample](./../images/rb-custom.png)