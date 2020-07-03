---
title: "Create ButtonGroup with rounded corner"
component: "ButtonGroup"
description: "ButtonGroup how to section, create ButtonGroup using util function, icons, form submit, show selected state on initial render."
---

# Create ButtonGroup with rounded corner

The ButtonGroup with rounded corner has round edges on both sided. To ButtonGroup with rounded corner, `e-round-corner` class is to be
added to the target element.

The following example illustrates how to create ButtonGroup with rounded corner.

`Index.razor`

```csharp

<div class='e-btn-group e-round-corner'>
    <EjsButton ID="html" Content="HTML"></EjsButton>
    <EjsButton ID="css" Content="CSS"></EjsButton>
    <EjsButton ID="javascript" Content="Javascript"></EjsButton>
</div>

  ```