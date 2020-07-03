---
title: "Hide Blazor DataGrid header"
component: "DataGrid"
description: "Learn how to hide the header in Blazor Data DataGrid component"
---

# Hide DataGrid header

You can hide the DataGrid header by applying the below styles to DataGrid component.

```html
<style>
    .e-grid .e-gridheader .e-columnheader{
        display: none;
    }
</style>
```

> if you want to hide the header for particular DataGrid, then you can apply the above styles to that DataGrid using the ID (#Grid.e-grid .e-gridheader .e-columnheader) property value.