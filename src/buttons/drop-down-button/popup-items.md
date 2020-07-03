---
title: "DropDownButton Popup Items"
component: "DropDownButton"
description: "DropDownButton allows the end user to customize the whole popup or action items in popup using templates, navigate to other pages on action item click."
---

# Popup items

## Icons

The popup action item have an icon or image to provide visual representation of the action. To place the icon on a popup item,
set the [`iconCss`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.EJ2.RazorComponents~Syncfusion.EJ2.RazorComponents.SplitButtons.EjsDropDownButton~IconCss.html) property to `e-icons` with the required icon CSS. By default, the icon is
positioned to the left side of the popup action item.

In the following sample, the icons for edit, delete, mark as read  and like message menu items are
added using the iconCss property.

`Index.razor`

```csharp

<EjsDropDownButton ID="left-icon" Content="Message" Items="@items" IconCss="ddb-icons e-message"></EjsDropDownButton>

@functions {

    List<object> items = new List<object>
     {
            new { text = "Edit", iconCss = "ddb-icons e-edit" },
            new { text = "Delete", iconCss = "ddb-icons e-delete" },
            new { text = "Mark as Read", iconCss = "ddb-icons e-read" },
            new { text = "Like Message", iconCss = "ddb-icons e-like" },
        };
}

  ```

  `_Host.cshtml`

   ```html

<style>
    /* csslint ignore:start */
    @@font-face {
        font-family: 'ddb-icons';
        src: url(data:application/x-font-ttf;charset=utf-8;base64,AAEAAAAKAIAAAwAgT1MvMj1tSfYAAAEoAAAAVmNtYXDnGOdnAAABmAAAAD5nbHlm/RE9ZwAAAegAAAJ8aGVhZBOPuxsAAADQAAAANmhoZWEIUQQHAAAArAAAACRobXR4GAAAAAAAAYAAAAAYbG9jYQHiAO4AAAHYAAAADm1heHABFACZAAABCAAAACBuYW1l1LBM9QAABGQAAAI9cG9zdOdmKCAAAAakAAAAZgABAAAEAAAAAFwEAAAAAAAD9AABAAAAAAAAAAAAAAAAAAAABgABAAAAAQAAfI9ISF8PPPUACwQAAAAAANg+uxUAAAAA2D67FQAAAAAD9AP0AAAACAACAAAAAAAAAAEAAAAGAI0ABAAAAAAAAgAAAAoACgAAAP8AAAAAAAAAAQQAAZAABQAAAokCzAAAAI8CiQLMAAAB6wAyAQgAAAIABQMAAAAAAAAAAAAAAAAAAAAAAAAAAAAAUGZFZABA5wDnBAQAAAAAXAQAAAAAAAABAAAAAAAABAAAAAQAAAAEAAAABAAAAAQAAAAEAAAAAAAAAgAAAAMAAAAUAAMAAQAAABQABAAqAAAABAAEAAEAAOcE//8AAOcA//8AAAABAAQAAAABAAIAAwAEAAUAAAAAAAAALgBaAHYAlAE+AAAAAwAAAAAD9AP0AAIABgAZAAA3JSc3FwEnNwcXPwM1LwcPAgwBJOo76QHT6qlu6XIFBAICBAWmCAkJCgkJCQw66jrpAdLpqW7pcggJCgkKCQimBwQDAQEDBAAAAAAEAAAAAANNA/QAAwAHABAAGAAAAREjESMRIxEnETMVITUzESE3IxUhNSM1IQLIh4SFhUICGED9ZoWFApqF/nACp/3qAhb96gIWQv1mQ0MC3YVCQkMAAAAAAgAAAAAD8wNuAAYACgAANyERIwkBIwUXASEMA+gC/g3+DgEBGNwBufyOkgLC/hcB6Z+5AXIAAAACAAAAAAPQA/QABQAKAAA3IREjCQElBwkCMAOgA/4x/jIBA8sBlgGX/moMAl7+PgHC2LL+nAFkAWQAAAACAAAAAAP0A8UAAwCMAAA3MxEjAQ8DFRcPDBEzNx8ENxc/Cj0BLwU/Cy8INzU/CDUvBTU/DTUvCQclPwQ1LwsjDwEMra0B+QIKBAEBAQEYIREREhMiCQkoEAYhBzUHHjmT2w4FCAsNCwkFAwQCAgQJBgIBAQEDDgQJCAYHAwMBAQEBAwMDCQIBAQMWCwUEBAMDAgICBAQKAQEBBAoHBwYFBQQDAwEBAQEEBQcJBQUFBhH+rQ8JBAMCAQEDAwoMFQMHBgwLDQcHWgGHAd4BBQMDdh8KBCw6HRscGi8JCBsM/ooBAR8DAQEBAgEBAwYKCgwGCAgIBQgJCAsFBAQEBQMGAwcICAwIBwgHBgYGBQUJBAIGAgQMCQYFBgcJCQoJCAgHCwQCBQMCBAQEBQUGBwcIBwYGBgYKCQgGAgIBAQEBRjEZGhsNDQwNCyIeMQQEAgQBAQIAAAASAN4AAQAAAAAAAAABAAAAAQAAAAAAAQAJAAEAAQAAAAAAAgAHAAoAAQAAAAAAAwAJABEAAQAAAAAABAAJABoAAQAAAAAABQALACMAAQAAAAAABgAJAC4AAQAAAAAACgAsADcAAQAAAAAACwASAGMAAwABBAkAAAACAHUAAwABBAkAAQASAHcAAwABBAkAAgAOAIkAAwABBAkAAwASAJcAAwABBAkABAASAKkAAwABBAkABQAWALsAAwABBAkABgASANEAAwABBAkACgBYAOMAAwABBAkACwAkATsgZGRiLWljb25zUmVndWxhcmRkYi1pY29uc2RkYi1pY29uc1ZlcnNpb24gMS4wZGRiLWljb25zRm9udCBnZW5lcmF0ZWQgdXNpbmcgU3luY2Z1c2lvbiBNZXRybyBTdHVkaW93d3cuc3luY2Z1c2lvbi5jb20AIABkAGQAYgAtAGkAYwBvAG4AcwBSAGUAZwB1AGwAYQByAGQAZABiAC0AaQBjAG8AbgBzAGQAZABiAC0AaQBjAG8AbgBzAFYAZQByAHMAaQBvAG4AIAAxAC4AMABkAGQAYgAtAGkAYwBvAG4AcwBGAG8AbgB0ACAAZwBlAG4AZQByAGEAdABlAGQAIAB1AHMAaQBuAGcAIABTAHkAbgBjAGYAdQBzAGkAbwBuACAATQBlAHQAcgBvACAAUwB0AHUAZABpAG8AdwB3AHcALgBzAHkAbgBjAGYAdQBzAGkAbwBuAC4AYwBvAG0AAAAAAgAAAAAAAAAKAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAGAQIBAwEEAQUBBgEHAAdlZGl0XzAzCWRlbGV0ZV8wMgxtZXNzYWdlLW1haWwLcmVhZC11bnJlYWQJbGlrZS0tLTAxAAAAAA==) format('truetype');
        font-weight: normal;
        font-style: normal;
    }
    /* csslint ignore:stop */

    .ddb-icons {
        font-family: 'ddb-icons' !important;
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
        content: '\e702';
    }

    .e-edit::before {
        content: '\e700';
    }

    .e-delete::before {
        content: '\e701';
    }

    .e-read::before {
        content: '\e703';
    }

    .e-like::before {
        content: '\e704';
    }

    button {
        margin: 25px 5px 20px 20px;
    }
</style>

  ```