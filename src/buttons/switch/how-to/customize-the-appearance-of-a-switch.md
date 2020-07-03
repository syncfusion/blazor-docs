---
title: "Customize the appearance of a Switch"
component: "Switch"
description: "Switch how to section, customization of Switch bar and handle, change size, name and value in form submit."
---

# Customize the appearance of a Switch

You can customize the appearance of the Switch component using the CSS rules. Define your own CSS rules according to your requirement and assign the class name to the [`cssClass`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.EJ2.RazorComponents~Syncfusion.EJ2.RazorComponents.Buttons.EjsSwitch~CssClass.html) property.

## Customize Switch bar and handle

Switch bar and handle can be customized as per requirement using CSS rules. Switch bar and handle customized using `cssClass` property. In the following sample, the `border-radius` CSS property for `e-switch-inner` and `e-switch-handle` elements was changed border radius circle to square shape.

`Index.razor`

```csharp

<ul>
        <li>
            <EjsSwitch ID="switch11" CssClass="square"></EjsSwitch>
        </li>
        <li>
            <EjsSwitch ID="switch22" CssClass="custom-switch"></EjsSwitch>
        </li>
        <li>
            <EjsSwitch ID="switch3" CssClass="handle-text"></EjsSwitch>
        </li>
    </ul>

  ```

  `_Host.cshtml`

   ```html

<style>
    /* Square Switch */
    .e-switch-wrapper.square .e-switch-inner,
    .e-switch-wrapper.square .e-switch-handle {
        border-radius: 0;
    }

    li {
        list-style: none;
        padding: 10px;
    }
    /* Customize Handle and Bar Switch */
    .e-switch-wrapper.custom-switch {
        width: 50px;
        height: 24px;
    }

        .e-switch-wrapper.custom-switch .e-switch-handle {
            width: 20px;
            height: 16px;
        }

        .e-switch-wrapper.custom-switch .e-switch-inner,
        .e-switch-wrapper.custom-switch .e-switch-handle {
            border-radius: 0;
        }

            .e-switch-wrapper.custom-switch .e-switch-handle.e-switch-active {
                left: 42px;
            }

    /* Customize Handle and Bar Switch */
    .e-switch-wrapper.handle-text {
        width: 58px;
        height: 24px;
    }

        .e-switch-wrapper.handle-text .e-switch-handle {
            width: 26px;
            height: 20px;
            left: 2px;
            background-color: #fff;
        }

        .e-switch-wrapper.handle-text .e-switch-inner,
        .e-switch-wrapper.handle-text .e-switch-handle {
            border-radius: 0;
        }

            .e-switch-wrapper.handle-text .e-switch-handle.e-switch-active {
                left: 46px;
            }

            .e-switch-wrapper.handle-text .e-switch-inner.e-switch-active,
            .e-switch-wrapper.handle-text:hover .e-switch-inner.e-switch-active .e-switch-on {
                background-color: #4d841d;
                border-color: #4d841d;
            }

        .e-switch-wrapper.handle-text .e-switch-inner,
        .e-switch-wrapper.handle-text .e-switch-off {
            background-color: #e3165b;
            border-color: #e3165b;
        }

            .e-switch-wrapper.handle-text .e-switch-inner:after,
            .e-switch-wrapper.handle-text .e-switch-inner:before {
                font-size: 10px;
                position: absolute;
                line-height: 21px;
                font-family: "Helvetica", sans-serif;
                z-index: 1;
                height: 100%;
                transition: all 200ms cubic-bezier(0.445, 0.05, 0.55, 0.95);
            }

            .e-switch-wrapper.handle-text .e-switch-inner:before {
                content: "OFF";
                color: #e3165b;
                left: 3px;
            }

            .e-switch-wrapper.handle-text .e-switch-inner:after {
                content: "ON";
                right: 5px;
                color: #fff;
            }

            .e-switch-wrapper.handle-text .e-switch-inner.e-switch-active:before {
                color: #fff;
            }

            .e-switch-wrapper.handle-text .e-switch-inner.e-switch-active:after {
                color: #4d841d;
            }
</style>

  ```

## Color the Switch

Switch colors can be customized as per the requirement using CSS rules. Switch bar and handle colors customized using `cssClass` property. In the following sample, the `e-switch-inner` and `e-switch-off` elements background and border colors were changed from default colors.

`Index.razor`

```csharp

<ul>
        <li>
            <EjsSwitch ID="switch11" CssClass="bar-color"></EjsSwitch>
        </li>
        <li>
            <EjsSwitch ID="switch22" CssClass="handle-color"></EjsSwitch>
        </li>
        <li>
            <EjsSwitch ID="switch3" CssClass="custom-iOS"></EjsSwitch>
        </li>
    </ul>

  ```

  `_Host.cshtml`

   ```html

<style>
    /* Custom color Switch */
    .e-switch-wrapper.bar-color .e-switch-inner.e-switch-active,
    .e-switch-wrapper.bar-color:hover .e-switch-inner.e-switch-active .e-switch-on {
        background-color: #4d841d;
        border-color: #4d841d;
    }

    li {
        list-style: none;
    }

    .e-switch-wrapper.bar-color .e-switch-inner,
    .e-switch-wrapper.bar-color .e-switch-off {
        background-color: #e3165b;
        border-color: #e3165b;
    }

    .e-switch-wrapper.bar-color .e-switch-handle {
        background-color: #fff;
    }

    /* handle color Switch */
    .e-switch-wrapper.handle-color .e-switch-handle {
        background-color: #e3165b;
    }

        .e-switch-wrapper.handle-color .e-switch-handle.e-switch-active {
            background-color: #4d841d
        }

    .e-switch-wrapper.handle-color .e-switch-inner.e-switch-active,
    .e-switch-wrapper.handle-color:hover .e-switch-inner.e-switch-active .e-switch-on {
        background-color: #fff;
        border-color: #ccc;
    }

    .e-switch-wrapper.handle-color .e-switch-inner,
    .e-switch-wrapper.handle-color .e-switch-off {
        background-color: #fff;
        border-color: #ccc;
    }

    /* iOS Switch */
    .e-switch-wrapper.custom-iOS .e-switch-inner.e-switch-active,
    .e-switch-wrapper.custom-iOS:hover .e-switch-inner.e-switch-active .e-switch-on {
        background-color: #3df865;
        border-color: #3df665;
    }

    .e-switch-wrapper.custom-iOS {
        width: 42px;
        height: 24px;
    }

        .e-switch-wrapper.custom-iOS .e-switch-handle {
            width: 20px;
            height: 20px;
        }

            .e-switch-wrapper.custom-iOS .e-switch-handle.e-switch-active {
                margin-left: -22px;
            }
</style>

  ```