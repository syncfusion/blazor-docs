---
title: "Create right-to-left DropDownButton"
component: "DropDownButton"
description: "DropDownButton how to section, hide drop down arrow, group popup items using list view component, dialog open on popup item click."
---

# Create right-to-left DropDownButton

DropDownButton component has RTL support. This can be achieved by setting [`enableRtl`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.EJ2.RazorComponents~Syncfusion.EJ2.RazorComponents.SplitButtons.EjsDropDownButton~EnableRtl.html) as true.

The following example illustrates how to enable right-to-left support in DropDownButton component.

`Index.razor`

```csharp

<EjsDropDownButton ID="rtl" Items="@items" Content="Message" IconCss="ddb-icons e-message" EnableRtl="true"></EjsDropDownButton>

@functions {

   List<object> items = new List<object>
     {
            new { text = "Edit" },
            new { text = "Delete" },
            new { text = "Mark as Read" },
             new { text = "Like Message" }

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

    .ddb-icons {
        font-family: 'e-db-icons' !important;
        speak: none;
        font-size: 55px;
        font-style: normal;
        font-weight: normal;
        font-variant: normal;
        text-transform: none;
        line-height: 1;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
    }

    .e-message::before {
        content: '\e703';
    }

    button {
        margin: 25px 5px 20px 20px;
    }
</style>

  ```