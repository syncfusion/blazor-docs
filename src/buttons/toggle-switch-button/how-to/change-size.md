---
title: "Change Size"
component: "Toggle Switch Button"
description: "Toggle Switch Button how to section, customization of Toggle Switch Button bar and handle, change size, name and value in form submit."
---

# Change Size

The different Toggle Switch Button sizes available are default and small. To reduce the size of default Toggle Switch Button to small,
set the [`CssClass`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Buttons.SfSwitch~CssClass.html) property to `e-small`.

```csharp
@using Syncfusion.Blazor.Buttons

<label for='switch1'>Checked</label>
<SfSwitch ID='switch1' CssClass="e-small" Checked="true"></SfSwitch>
<label for='switch2'>Unchecked</label>
<SfSwitch ID='switch2'></SfSwitch>

```

Output be like

![Switch Sample](./../images/switch-size.png)