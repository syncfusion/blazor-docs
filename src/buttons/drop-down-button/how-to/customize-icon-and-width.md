---
title: "Customize icon and width"
component: "DropDownButton"
description: "DropDownButton how to section, hide drop down arrow, group popup items using list view component, dialog open on popup item click."
---

# Customize icon and width

Width of the DropDownButton can be customized by setting required width to the dropdown element.

The following UI can be achieved by setting
[`iconPosition`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.EJ2.RazorComponents~Syncfusion.EJ2.RazorComponents.SplitButtons.EjsDropDownButton~IconPosition.html) as `Top`, width as `85px`
and size of the font icon as `40px` by adding `e-custom` class.

`Index.razor`

```csharp

<EjsDropDownButton ID="rtl" Items="@items" Content="Search" IconCss="e-icons e-search" CssClass = "e-custom" IconPosition ="@Syncfusion.EJ2.RazorComponents.SplitButtons.SplitButtonIconPosition.Top"></EjsDropDownButton>

@functions {

      List<object> items = new List<object>
     {
            new { text = "Find" },
            new { text = "Replace" },
            new { text = "Go To" },
             new { text = "Go To Special" }

        };

}
  ```

  `_Host.cshtml`

   ```html

<style>

    /* csslint ignore:start */
    @@font-face {
        font-family: 'e-db-icons';
        src: url(data:application/x-font-ttf;charset=utf-8;base64,AAEAAAAKAIAAAwAgT1MvMj0jSRoAAAEoAAAAVmNtYXDnFudgAAABkAAAADpnbHlmSrKTCAAAAdgAAAC4aGVhZBKtK8cAAADQAAAANmhoZWEHmQNtAAAArAAAACRobXR4D7gAAAAAAYAAAAAQbG9jYQB4ADoAAAHMAAAACm1heHABEAAYAAABCAAAACBuYW1lH00mDAAAApAAAAJJcG9zdIwkSr0AAATcAAAATQABAAADUv9qAFoEAAAA//4D6gABAAAAAAAAAAAAAAAAAAAABAABAAAAAQAAGc/PS18PPPUACwPoAAAAANfSc3wAAAAA19JzfAAAAAAD6gPqAAAACAACAAAAAAAAAAEAAAAEAAwAAgAAAAAAAgAAAAoACgAAAP8AAAAAAAAAAQPuAZAABQAAAnoCvAAAAIwCegK8AAAB4AAxAQIAAAIABQMAAAAAAAAAAAAAAAAAAAAAAAAAAAAAUGZFZABA5wPnBQNS/2oAWgPqAJYAAAABAAAAAAAABAAAAAPoAAAD6AAAA+gAAAAAAAIAAAADAAAAFAADAAEAAAAUAAQAJgAAAAQABAABAADnBf//AADnA///AAAAAQAEAAAAAQACAAMAAAAAAAAAHAA6AFwAAAACAAAAAAPqA2UABgAKAAA3IREjCQEjBRcBIQID6AL+Dv4NAQEY3QG4/I+IAsL+GAHonroBcwAAAAIAAAAAA8YD6gAFAAoAADchESMJASUHCQImA6AD/jL+MQEEywGWAZb+agICX/4+AcLXsv6cAWQBZAAAAAEAAAAAA+oD6gALAAATCQEXCQE3CQEnCQECATP+zcIBMgEzwf7OATLB/s3+zgMp/s3+zsIBM/7NwgEyATPB/s4BMgAAAAASAN4AAQAAAAAAAAABAAAAAQAAAAAAAQAKAAEAAQAAAAAAAgAHAAsAAQAAAAAAAwAKABIAAQAAAAAABAAKABwAAQAAAAAABQALACYAAQAAAAAABgAKADEAAQAAAAAACgAsADsAAQAAAAAACwASAGcAAwABBAkAAAACAHkAAwABBAkAAQAUAHsAAwABBAkAAgAOAI8AAwABBAkAAwAUAJ0AAwABBAkABAAUALEAAwABBAkABQAWAMUAAwABBAkABgAUANsAAwABBAkACgBYAO8AAwABBAkACwAkAUcgZS1kYi1pY29uc1JlZ3VsYXJlLWRiLWljb25zZS1kYi1pY29uc1ZlcnNpb24gMS4wZS1kYi1pY29uc0ZvbnQgZ2VuZXJhdGVkIHVzaW5nIFN5bmNmdXNpb24gTWV0cm8gU3R1ZGlvd3d3LnN5bmNmdXNpb24uY29tACAAZQAtAGQAYgAtAGkAYwBvAG4AcwBSAGUAZwB1AGwAYQByAGUALQBkAGIALQBpAGMAbwBuAHMAZQAtAGQAYgAtAGkAYwBvAG4AcwBWAGUAcgBzAGkAbwBuACAAMQAuADAAZQAtAGQAYgAtAGkAYwBvAG4AcwBGAG8AbgB0ACAAZwBlAG4AZQByAGEAdABlAGQAIAB1AHMAaQBuAGcAIABTAHkAbgBjAGYAdQBzAGkAbwBuACAATQBlAHQAcgBvACAAUwB0AHUAZABpAG8AdwB3AHcALgBzAHkAbgBjAGYAdQBzAGkAbwBuAC4AYwBvAG0AAAAAAgAAAAAAAAAKAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAEAQIBAwEEAQUADG1lc3NhZ2UtbWFpbAtyZWFkLXVucmVhZAZkZWxldGUAAAAAAA==) format('truetype');
        font-weight: normal;
        font-style: normal;
    }
    /* csslint ignore:stop */

    .e-search::before {
  content: '\e993';
}

button {
  margin: 25px 5px 20px 20px;
}

.e-dropdown-btn.e-custom {
  width: 85px;
}

.e-dropdown-btn.e-custom .e-search::before {
  font-size: 40px;
}
</style>

  ```