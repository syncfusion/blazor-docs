---
title: "Customize input and anchor elements"
component: "Button"
description: "Button how to section, block button, repeat button, tooltip for Button, customization of button appearance, input and anchor elements."
---

# Customize input and anchor elements

You can customize the appearance of the input and anchor elements using predefined styles through the class property. In the following code
snippet, the input element is customized as a link Button by setting the `e-btn e-link` class, and the anchor element is customized as a
primary Button by setting the `e-btn e-primary` class.

`Index.razor`

```csharp

   <div>
    <input type="button" ID="inputbtn" value="Input Button" class="e-btn e-link">
</div>

<div>
    <a ID="anchorbtn" class="e-btn e-primary" href="#">Google</a>
</div
  ```