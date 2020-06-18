---
title: "ButtonGroup Types and Styles"
component: "ButtonGroup"
description: "ButtonGroup CSS control supports outline type and predefined styles."
---

# Types and Styles

This section explains about different types and styles of ButtonGroup.

## ButtonGroup types

### Outline ButtonGroup

An Outline ButtonGroup has a border with transparent background. To create Outline ButtonGroup, `e-outline` class should
be added to the target element and to each button elements using `CssClass` property.

The following sample illustrates how to achieve an Outline ButtonGroup,

`Index.razor`

```csharp

   <div class='e-btn-group e-outline'>
    <EjsButton ID="html" CssClass='e-outline' Content="HTML"></EjsButton>
    <EjsButton ID="css" CssClass='e-outline' Content="CSS"></EjsButton>
    <EjsButton ID="javascript" CssClass='e-outline' Content="Javascript"></EjsButton>
</div>

  ```

  `_Host.cshtml`

   ```html

    <style>
        .e-btn-group {
       margin: 25px 5px 20px 20px;
     }
    </style>

  ```  

> ButtonGroup does not have support for `flat` and `round` types.

## ButtonGroup styles

The Essential JS 2 ButtonGroup has the following predefined styles. This can be achieved by adding corresponding class name
in each button elements using `CssClass` property.

| Class | Description |
| -------- | -------- |
| e-primary | Used to represent a primary action. |
| e-success | Used to represent a positive action. |
| e-info | Used to represent an informative action. |
| e-warning | Used to represent an action with caution. |
| e-danger | Used to represent a negative action. |

The following example illustrates how to achieve predefined styles in ButtonGroup.

`Index.razor`

```csharp

   <div class='e-btn-group'>
    <EjsButton ID="approve" Content="Approve" CssClass='e-success'></EjsButton>
    <EjsButton ID="reject" Content="Reject" CssClass='e-warning'></EjsButton>
    <EjsButton ID="view" Content="View" CssClass='e-info'></EjsButton>
    <EjsButton ID="edit" Content="Edit" CssClass='e-primary'></EjsButton>
    <EjsButton ID="delete" Content="Delete" CssClass='e-danger'></EjsButton>
</div>

  ```

  `_Host.cshtml`

   ```html

    <style>
        .e-btn-group {
       margin: 25px 5px 20px 20px;
     }
    </style>

  ```  

> Predefined ButtonGroup styles provide only the visual indication. So,
ButtonGroup content should define the ButtonGroup style for the users of assistive technologies such as screen readers.

## See Also

* [ButtonGroup with icons](./how-to/create-buttongroup-with-icons)
* [Create ButtonGroup with rounded corner](./how-to/create-buttongroup-with-rounded-corner)