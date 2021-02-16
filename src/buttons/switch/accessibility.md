# Accessibility

The web accessibility makes web content and web applications more accessible for people with disabilities. It especially helps in dynamic content change and development of advanced user interface controls with AJAX, HTML, JavaScript, and related technologies.

Switch provides built-in compliance with `WAI-ARIA` specifications. `WAI-ARIA` support is achieved through the attributes like `aria-checked` and `aria-disabled`. It helps the people with disabilities by providing information about the widget for assistive technology in the screen readers, such as screen readers.

| Properties | Functionality |
| ------------ | ----------------------- |
| role | Indicates the switch component. |
| aria-checked | Indicates whether the input is checked, unchecked. |
| aria-disabled | Indicates that the element is perceivable but disabled, so it is not editable or otherwise operable. |

## Keyboard interaction

<!-- markdownlint-disable MD033 -->
<table>
<tr>
<td>
<b>Keyboard shortcuts</b></td><td>
<b>Actions</b></td></tr>
<tr>
<td>
<kbd>Space</kbd></td><td>
When the switch has focus, pressing the Space key changes the state of the switch.</td></tr>
</table>

`Index.razor`

```csharp

<div id='container'>
    <table class='size'>
        <tr>
            <td class='lSize'>Checked</td>
            <td>
                <EjsSwitch Id="switch1" Checked="true"></EjsSwitch>
            </td>
        </tr>
        <tr>
            <td class='lSize'>Unchecked</td>
            <td>
                <EjsSwitch Id="switch2"></EjsSwitch>
            </td>
        </tr>
    </table>
</div>

  ```

  `_Host.cshtml`

   ```html

<style>
    .size tr td {
        padding: 10px;
    }

    .size .lSize {
        font-family: "Roboto", "Segoe UI", "GeezaPro", "DejaVu Serif", "sans-serif";
        font-size: 13px;
        cursor: pointer;
        user-select: none;
    }
</style>

  ```