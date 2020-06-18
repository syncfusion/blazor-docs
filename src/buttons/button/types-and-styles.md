---
title: "ButtonGroup Types and Styles"
component: "Button"
description: "Button control supports different types, predefined styles, sizes and also has support for icons."
---

# Types and Styles

This section explains the different styles and types of Buttons.

## Button styles

The Essential JS 2 Button has the following predefined styles that can be defined using the [`cssClass`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.EJ2.RazorComponents~Syncfusion.EJ2.RazorComponents.Buttons.EjsButton~CssClass.html) property.

| Class | Description |
| -------- | -------- |
| e-primary | Used to represent a primary action. |
| e-success | Used to represent a positive action. |
| e-info |  Used to represent an informative action. |
| e-warning | Used to represent an action with caution. |
| e-danger | Used to represent a negative action. |
| e-link |  Changes the appearance of the Button like a hyperlink. |

`Index.razor`

```csharp

   <EjsButton ID="primarybtn" CssClass="e-primary" Content="Primary"></EjsButton>
   <EjsButton ID="successbtn" CssClass="e-success" Content="Success"></EjsButton>
   <EjsButton ID="infobtn" CssClass="e-info" Content="Info"></EjsButton>
   <EjsButton ID="warningbtn" CssClass="e-warning" Content="Warning"></EjsButton>
   <EjsButton ID="dangerbtn" CssClass="e-danger" Content="Danger"></EjsButton>
   <EjsButton ID="linkbtn" CssClass="e-link" Content="Link"></EjsButton>

  ```

  `_Host.cshtml`

  ```html

   <style>
        button {
            margin: 25px 5px 20px 20px;
        }
    </style>

  ```  

> Predefined Button styles provide only the visual indication. So,
Button content should define the Button style for the users of assistive technologies such as screen readers.

## Button types

The types of Essential JS 2 Button are as follows:

* Flat Button
* Outline Button
* Round Button
* Toggle Button

### Flat Button

The Flat Button is styled with no background color. To create a flat Button,
set the [`cssClass`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.EJ2.RazorComponents~Syncfusion.EJ2.RazorComponents.Buttons.EjsButton~CssClass.html) property to `e-flat`.

### Outline Button

An outline Button has a border with transparent background. To create an outline Button,
set the [`cssClass`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.EJ2.RazorComponents~Syncfusion.EJ2.RazorComponents.Buttons.EjsButton~CssClass.html) property to `e-outline`.

### Round Button

A round Button is shaped like a circle. Usually, it contains an icon representing its action. To create a round Button,
set the [`cssClass`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.EJ2.RazorComponents~Syncfusion.EJ2.RazorComponents.Buttons.EjsButton~CssClass.html) property to `e-round`.

`Index.razor`

```csharp

   <EjsButton ID="flat" CssClass="e-flat" Content="Flat"></EjsButton>
   <EjsButton ID="outline" CssClass="e-outline" Content="Outline"></EjsButton>
   <EjsButton ID="round" CssClass="e-round" IconCss="e-icons e-plus-icon" IsPrimary="true"></EjsButton>

  ```

`_Host.cshtml`

  ```html

   <style>

        button {
            margin: 25px 5px 20px 20px;
        }

        .e-plus-icon::before {
            content: '\e823';
        }
    </style>

  ```  

### Toggle Button

A toggle Button allows you to change between the two states. The Button is active in toggled state and can be recognized through the `e-active` class.
The functionality of the toggle Button is handled by click event. To create a toggle Button,
set the [`isToggle`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.EJ2.RazorComponents~Syncfusion.EJ2.RazorComponents.Buttons.EjsButton~IsToggle.html) property to `true`. In the following code snippet,
the toggle Button text changes to play/pause based on the state of the Button with the use of click event.

`Index.razor`

```csharp

   <EjsButton ID="togglebtn" ref="togglebtn" onclick="@onToggleClick" CssClass="e-flat" IsToggle="true" IsPrimary="true" Content="@content" IconCss="@iconCss"></EjsButton>

   @functions {

     EjsButton togglebtn;
    public string content = "Play";
    public string iconCss = "e-btn-sb-icons e-play-icon";
    private void onToggleClick(UIMouseEventArgs args)
    {
        if (togglebtn.Content == "Play")
        {
            this.content = "Pause";
            this.iconCss = "e-btn-sb-icons e-pause-icon";
        }
        else
        {
            this.content = "Play";
            this.iconCss = "e-btn-sb-icons e-play-icon";
        }
        togglebtn.Content = this.content;
        togglebtn.IconCss = this.iconCss;
        togglebtn.DataBind();
    }
   }

  ```

  `_Host.cshtml`

  ```html

   <style>
        @@font-face {
            font-family: 'button-icons';
            src: url(data:application/x-font-ttf;charset=utf-8;base64,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) format('truetype');
            font-weight: normal;
            font-style: normal;
        }

        .e-btn-sb-icons {
            font-family: 'button-icons';
            line-height: 1;
            font-style: normal;
            font-weight: normal;
            font-variant: normal;
            text-transform: none;
            -webkit-font-smoothing: antialiased;
            -moz-osx-font-smoothing: grayscale;
        }

        .e-play-icon::before {
            content: '\e701';
        }

        .e-pause-icon::before {
            content: '\e705';
        }
    </style>

  ```  

## Icons

### Button with font icons

The Button can have an icon to provide the visual representation of the action. To place the icon on a Button,
set the [`iconCss`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.EJ2.RazorComponents~Syncfusion.EJ2.RazorComponents.Buttons.EjsButton~IconCss.html)
property to `e-icons` with the required icon CSS. By default, the icon is positioned to the left side of the Button.
You can customize the icon's position by using the [`iconPosition`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.EJ2.RazorComponents~Syncfusion.EJ2.RazorComponents.Buttons.EjsButton~IconPosition.html) property.

`Index.razor`

```csharp

   <EjsButton ID="iconbutton" Content="PREVIOUS" IconCss="e-btn-sb-icon e-prev-icon"></EjsButton>
   <EjsButton ID="iconposbtn" Content="STOP" IconCss="e-btn-sb-icon e-stop-icon"></EjsButton>

  ```

`_Host.cshtml`

  ```html

   <style>
        button {
            margin: 25px 5px 20px 20px;
        }

        @@font-face {
            font-family: 'btn-icon';
            src: url(data:application/x-font-ttf;charset=utf-8;base64,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) format('truetype');
            font-weight: normal;
            font-style: normal;
        }

        .e-btn-sb-icon {
            font-family: 'btn-icon' !important;
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

        .e-stop-icon::before {
            content: '\e703';
        }

        .e-prev-icon::before {
            content: '\e702';
        }
    </style>

  ```  

> The Essential JS 2 provides a set of icons that can be loaded by applying `e-icons` class name to the element.
You can also use third party icons on the Button using the [`iconCss`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.EJ2.RazorComponents~Syncfusion.EJ2.RazorComponents.Buttons.EjsButton~IconCss.html) property.

### Button with SVG image

SVG image can be added to the Button using [`iconCss`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.EJ2.RazorComponents~Syncfusion.EJ2.RazorComponents.Buttons.EjsButton~IconCss.html)
property.

In the following example, SVG image is added using the iconCss class `e-search-icon` by setting `height` and `width` property.

`Index.razor`

```csharp

   <EjsButton ID="iconbutton" IconCss="e-search-icon"></EjsButton>

  ```

`_Host.cshtml`

  ```html

    <style>
        button {
            margin: 25px 5px 20px 20px;
        }

        .e-btn-icon.e-search-icon {
            background: url('search_icon.svg');
            height: 25px;
            width: 25px;
        }
    </style>

  ```  

## Button size

The two types of Button sizes are default and small. To change the size of the default Button to small Button,
set the [`cssClass`](https://help.syncfusion.com/cr/aspnetcore-blazor/Syncfusion.EJ2.RazorComponents~Syncfusion.EJ2.RazorComponents.Buttons.EjsButton~CssClass.html) property to `e-small`.

`Index.razor`

```csharp

   <EjsButton ID="smallbtn" CssClass="e-small" Content="SMALL"></EjsButton>
   <EjsButton ID="normalbtn" Content="NORMAL"></EjsButton>

  ```

## See Also

* [Customize Button appearance](./how-to/customize-button-appearance)
* [How to create block button](./how-to/create-a-block-button)