---
title: "Customized CheckBox"
component: "CheckBox"
description: "CheckBox how to section, name and value in form submit, and customization of CheckBox appearance, frame & check icon."
---

# Customized CheckBox

## Customize CheckBox Appearance

You can customize the appearance of the CheckBox component using the CSS rules.
Define own CSS rules according to your requirement and assign the class name to the
[`cssClass`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.EJ2.RazorComponents~Syncfusion.EJ2.RazorComponents.Buttons.EjsCheckBox~CssClass.html) property.

The background and border color of the CheckBox is customized through the custom classes to create primary, success, warning, and danger info type of checkbox.

`Index.razor`

```csharp

<ul>
    <li>
        <EjsCheckBox ID="primary" Checked="true" Label="Primary" CssClass="e-primary"></EjsCheckBox>
    </li>
    <li>
        <EjsCheckBox ID="success" Checked="true" Label="Success" CssClass="e-success"></EjsCheckBox>
    </li>
    <li>
        <EjsCheckBox ID="info" Checked="true" Label="Info" CssClass="e-info"></EjsCheckBox>
    </li>
    <li>
        <EjsCheckBox ID="warning" Checked="true" Label="Warning" CssClass="e-warning"></EjsCheckBox>
    </li>
    <li>
        <EjsCheckBox ID="danger" Checked="true" Label="Danger" CssClass="e-danger"></EjsCheckBox>
    </li>
</ul>

  ```

  `_Host.cshtml`

   ```html

     <style>

        .e-checkbox-wrapper {
            margin-top: 18px;
        }

        li {
            list-style: none;
        }

        .e-checkbox-wrapper.e-primary:hover .e-frame.e-check { /* csslint allow: adjoining-classes */
            background-color: #e03872;
        }

        .e-checkbox-wrapper.e-success .e-frame.e-check,
        .e-checkbox-wrapper.e-success .e-checkbox:focus + .e-frame.e-check { /* csslint allow: adjoining-classes */
            background-color: #689f38;
        }

        .e-checkbox-wrapper.e-success:hover .e-frame.e-check { /* csslint allow: adjoining-classes */
            background-color: #449d44;
        }

        .e-checkbox-wrapper.e-info .e-frame.e-check,
        .e-checkbox-wrapper.e-info .e-checkbox:focus + .e-frame.e-check { /* csslint allow: adjoining-classes */
            background-color: #2196f3;
        }

        .e-checkbox-wrapper.e-info:hover .e-frame.e-check { /* csslint allow: adjoining-classes */
            background-color: #0b7dda;
        }

        .e-checkbox-wrapper.e-warning .e-frame.e-check,
        .e-checkbox-wrapper.e-warning .e-checkbox:focus + .e-frame.e-check { /* csslint allow: adjoining-classes */
            background-color: #ef6c00;
        }

        .e-checkbox-wrapper.e-warning:hover .e-frame.e-check { /* csslint allow: adjoining-classes */
            background-color: #cc5c00;
        }

        .e-checkbox-wrapper.e-danger .e-frame.e-check,
        .e-checkbox-wrapper.e-danger .e-checkbox:focus + .e-frame.e-check { /* csslint allow: adjoining-classes */
            background-color: #d84315;
        }

        .e-checkbox-wrapper.e-danger:hover .e-frame.e-check { /* csslint allow: adjoining-classes */
            background-color: #ba3912;
        }
    </style>

  ```  

## Customize width and height

The height and width of the CheckBox component can be customized by setting `height` and `width` property.

The following section explains about how to customize the height and width of the CheckBox component.

`Index.razor`

```csharp

<EjsCheckBox ID="customsize" CssClass="e-customsize" Label="Default"></EjsCheckBox>

  ```

  `_Host.cshtml`

   ```html

     <style>

        .e-checkbox-wrapper {
            margin-top: 30px;
        }

        .e-customsize.e-checkbox-wrapper .e-frame {
            height: 30px;
            width: 30px;
            padding: 8px 0;
        }

        .e-customsize.e-checkbox-wrapper .e-check {
            font-size: 20px;
        }

        .e-customsize.e-checkbox-wrapper .e-ripple-container {
            height: 52px;
            top: -11px;
            width: 47px;
        }

        .e-customsize.e-checkbox-wrapper .e-label {
            line-height: 30px;
            font-size: 20px;
        }
    </style>

  ```  

## Custom Frame

CheckBox frame can be customized as per the requirement by adding CSS rules.

In the following example, to-do list is displayed with round checkbox by changing
`border-radius` as `100%` by adding `e-custom` class.

`Index.razor`

```csharp

<ul>
    <li>
        <EjsCheckBox ID="cbox2" Label="Buy Groceries" Checked="true" CssClass="e-custom"></EjsCheckBox>
    </li>
    <li>
        <EjsCheckBox ID="cbox3" Label="Pay Rent" Checked="true" CssClass="e-custom"></EjsCheckBox>
    </li>
    <li>
        <EjsCheckBox ID="cbox4" Label="Make Dinner" CssClass="e-custom"></EjsCheckBox>
    </li>
    <li>
        <EjsCheckBox ID="cbox1" Label="Finish To-do List Article" CssClass="e-custom"></EjsCheckBox>
    </li>
</ul>

  ```

  `_Host.cshtml`

   ```html

     <style>

        li {
            list-style: none;
        }

        .e-checkbox-wrapper {
            margin-top: 18px;
        }

        .e-custom .e-frame {
            border-radius: 100%;
        }

        .e-checkicon.e-checkbox-wrapper .e-frame.e-check::before {
            content: '\e77d';
        }

        .e-checkicon.e-checkbox-wrapper .e-check {
            font-size: 8.5px;
        }

        .e-checkicon.e-checkbox-wrapper .e-frame.e-check {
            background-color: white;
            border-color: grey;
            color: grey;
        }

        .e-checkicon.e-checkbox-wrapper:hover .e-frame.e-check {
            background-color: white;
            border-color: grey;
            color: grey;
        }

        .e-checkicon.e-checkbox-wrapper .e-checkbox:focus + .e-frame.e-check {
            background-color: white;
            border-color: grey;
            box-shadow: none;
            color: grey;
        }
    </style>

  ```  

## Custom Check Icon

CheckBox check icon can be customized as per the requirement by adding CSS rules.

In the following example, the check icon can be customized by changing check icon content, background and
border color in focus and hovered states by adding `e-checkicon` class.

`Index.razor`

```csharp

<ul>
    <li>
        <EjsCheckBox ID="cbox2" Label="Buy Groceries" Checked="true" CssClass="e-checkicon"></EjsCheckBox>
    </li>
    <li>
        <EjsCheckBox ID="cbox3" Label="Pay Rent" Checked="true" CssClass="e-checkicon"></EjsCheckBox>
    </li>
    <li>
        <EjsCheckBox ID="cbox4" Label="Make Dinner" CssClass="e-checkicon"></EjsCheckBox>
    </li>
    <li>
        <EjsCheckBox ID="cbox1" Label="Finish To-do List Article" CssClass="e-checkicon"></EjsCheckBox>
    </li>
</ul>

  ```

  `_Host.cshtml`

   ```html

    <style>
        li {
            list-style: none;
        }

        .e-checkbox-wrapper {
            margin-top: 18px;
        }

        .e-checkicon.e-checkbox-wrapper .e-frame.e-check::before {
            content: '\e77d';
        }

        .e-checkicon.e-checkbox-wrapper .e-check {
            font-size: 8px;
        }

        .e-checkicon.e-checkbox-wrapper .e-frame.e-check {
            background-color: white;
            border-color: grey;
            color: grey;
        }

        .e-checkicon.e-checkbox-wrapper:hover .e-frame.e-check {
            background-color: white;
            border-color: grey;
            color: grey;
        }

        .e-checkicon.e-checkbox-wrapper .e-checkbox:focus + .e-frame.e-check {
            background-color: white;
            border-color: grey;
            box-shadow: none;
            color: grey;
        }

        .e-checkicon.e-checkbox-wrapper .e-ripple-element {
            background: grey;
        }
    </style>

  ```  
