---
title: "DropDownButton Icons"
component: "DropDownButton"
description: "DropDownButton allows the end user to place the icons/sprite images in DropDownButton."
---

# Icons and Styles

## DropDownButton icons

DropDownButton can have an icon to provide the visual representation of the action. To place the icon on a DropDownButton,
set the [`iconCss`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.EJ2.RazorComponents~Syncfusion.EJ2.RazorComponents.SplitButtons.EjsDropDownButton~IconCss.html) property to `e-icons` with the required icon CSS. By default,
the icon is positioned to the left side of the DropDownButton. You can customize the icon's position using
the [`iconPosition`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.EJ2.RazorComponents~Syncfusion.EJ2.RazorComponents.SplitButtons.EjsDropDownButton~IconPosition.html) property.

In the following example, the DropDownButton with default iconPosition and iconPosition as `Top` is showcased:

`Index.razor`

```csharp

<EjsDropDownButton ID="left-icon" Content="Message" Items="@items" IconCss="ddb-icons e-message"></EjsDropDownButton>
<EjsDropDownButton ID="top-icon" Content="Message" Items="@items" IconCss="ddb-icons e-message" IconPosition="@Syncfusion.EJ2.RazorComponents.SplitButtons.SplitButtonIconPosition.Top"></EjsDropDownButton>

@functions {

    List<object> items = new List<object>
     {
            new { text = "Edit" },
            new { text = "Delete" },
            new { text = "Mark as Read" },
            new { text = "Like Message" },

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

> The Essential JS 2 provides a set of icons that can be loaded by applying `e-icons` class name to the element.
You can also use third party icons on the DropDownButton using the [`iconCss`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.EJ2.RazorComponents~Syncfusion.EJ2.RazorComponents.SplitButtons.EjsDropDownButton~IconCss.html) property.

### Vertical button

Vertical button in DropDownButton can be achieved by adding `e-vertical` class using [`cssClass`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.EJ2.RazorComponents~Syncfusion.EJ2.RazorComponents.SplitButtons.EjsDropDownButton~CssClass.html) property.

`Index.razor`

```csharp

<EjsDropDownButton ID="vertical-btn" Content="Message" Items="@items" IconCss="ddb-icons e-message"></EjsDropDownButton>

@functions {

    List<object> items = new List<object>
     {
            new { text = "Edit" },
            new { text = "Delete" },
            new { text = "Mark as Read" },
            new { text = "Like Message" },
        };
}

  ```

  `_Host.cshtml`

   ```html

<style>
    /* csslint ignore:start */
    @@font-face {
        font-family: 'e-db-icons';
        src:
        url(data:application/x-font-ttf;charset=utf-8;base64,AAEAAAAKAIAAAwAgT1MvMj0jSRoAAAEoAAAAVmNtYXDnFudgAAABkAAAADpnbHlmSrKTCAAAAdgAAAC4aGVhZBKtK8cAAADQAAAANmhoZWEHmQNtAAAArAAAACRobXR4D7gAAAAAAYAAAAAQbG9jYQB4ADoAAAHMAAAACm1heHABEAAYAAABCAAAACBuYW1lH00mDAAAApAAAAJJcG9zdIwkSr0AAATcAAAATQABAAADUv9qAFoEAAAA//4D6gABAAAAAAAAAAAAAAAAAAAABAABAAAAAQAAGc/PS18PPPUACwPoAAAAANfSc3wAAAAA19JzfAAAAAAD6gPqAAAACAACAAAAAAAAAAEAAAAEAAwAAgAAAAAAAgAAAAoACgAAAP8AAAAAAAAAAQPuAZAABQAAAnoCvAAAAIwCegK8AAAB4AAxAQIAAAIABQMAAAAAAAAAAAAAAAAAAAAAAAAAAAAAUGZFZABA5wPnBQNS/2oAWgPqAJYAAAABAAAAAAAABAAAAAPoAAAD6AAAA+gAAAAAAAIAAAADAAAAFAADAAEAAAAUAAQAJgAAAAQABAABAADnBf//AADnA///AAAAAQAEAAAAAQACAAMAAAAAAAAAHAA6AFwAAAACAAAAAAPqA2UABgAKAAA3IREjCQEjBRcBIQID6AL+Dv4NAQEY3QG4/I+IAsL+GAHonroBcwAAAAIAAAAAA8YD6gAFAAoAADchESMJASUHCQImA6AD/jL+MQEEywGWAZb+agICX/4+AcLXsv6cAWQBZAAAAAEAAAAAA+oD6gALAAATCQEXCQE3CQEnCQECATP+zcIBMgEzwf7OATLB/s3+zgMp/s3+zsIBM/7NwgEyATPB/s4BMgAAAAASAN4AAQAAAAAAAAABAAAAAQAAAAAAAQAKAAEAAQAAAAAAAgAHAAsAAQAAAAAAAwAKABIAAQAAAAAABAAKABwAAQAAAAAABQALACYAAQAAAAAABgAKADEAAQAAAAAACgAsADsAAQAAAAAACwASAGcAAwABBAkAAAACAHkAAwABBAkAAQAUAHsAAwABBAkAAgAOAI8AAwABBAkAAwAUAJ0AAwABBAkABAAUALEAAwABBAkABQAWAMUAAwABBAkABgAUANsAAwABBAkACgBYAO8AAwABBAkACwAkAUcgZS1kYi1pY29uc1JlZ3VsYXJlLWRiLWljb25zZS1kYi1pY29uc1ZlcnNpb24gMS4wZS1kYi1pY29uc0ZvbnQgZ2VuZXJhdGVkIHVzaW5nIFN5bmNmdXNpb24gTWV0cm8gU3R1ZGlvd3d3LnN5bmNmdXNpb24uY29tACAAZQAtAGQAYgAtAGkAYwBvAG4AcwBSAGUAZwB1AGwAYQByAGUALQBkAGIALQBpAGMAbwBuAHMAZQAtAGQAYgAtAGkAYwBvAG4AcwBWAGUAcgBzAGkAbwBuACAAMQAuADAAZQAtAGQAYgAtAGkAYwBvAG4AcwBGAG8AbgB0ACAAZwBlAG4AZQByAGEAdABlAGQAIAB1AHMAaQBuAGcAIABTAHkAbgBjAGYAdQBzAGkAbwBuACAATQBlAHQAcgBvACAAUwB0AHUAZABpAG8AdwB3AHcALgBzAHkAbgBjAGYAdQBzAGkAbwBuAC4AYwBvAG0AAAAAAgAAAAAAAAAKAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAEAQIBAwEEAQUADG1lc3NhZ2UtbWFpbAtyZWFkLXVucmVhZAZkZWxldGUAAAAAAA==) format('truetype');
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

## See Also

* [Dropdown popup with icons](./popup-items#icons)
* [Customized icon size](./how-to/customize-icon-and-width)