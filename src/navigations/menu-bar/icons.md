---
title: "Icons and Submenu Items"
component: "Menu Bar"
description: "This section helps you to learn how to create the icons and Submenu Bar items in Menu Bar in Blazor application in step-by-step procedure."
---

# Icons and Sub Menu items

## Icons

The menu item contains an icon/image in it to provide a visual representation of an action.
To place the icon on a menu item, set the [`IconCss`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Navigations.MenuItem~IconCss.html)
property with the required icon CSS. By default, the icon is positioned at the left of the
menu item. In the following sample, the icons of `File` and `Edit` menu items and `Open`,
`Save`, `Cut`, `Copy`,and `Paste` sub menu items are added using the [`IconCss`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Navigations.MenuItem~IconCss.html) property.

```csharp
@using Syncfusion.Blazor.Navigations

<SfMenu Items="@MenuItems"></SfMenu>

@code {
    public List<MenuItem> MenuItems = new List<MenuItem>{
        new MenuItem{ Text = "File", IconCss = "e-icons e-file", Items = new List<MenuItem>{
            new MenuItem { Text= "Open", IconCss= "e-icons e-open" },
            new MenuItem { Text= "Save", IconCss= "e-icons e-save" },
            new MenuItem { Separator= true },
            new MenuItem { Text= "Exit" }}
    },
        new MenuItem{ Text = "Edit", IconCss = "e-icons e-edit", Items = new List<MenuItem>{
            new MenuItem{ Text= "Cut", IconCss= "e-icons e-cut" },
            new MenuItem{ Text= "Copy", IconCss= "e-icons e-copy" },
            new MenuItem{ Text= "Paste", IconCss= "e-icons e-paste" }}
    },
        new MenuItem{ Text = "View", Items = new List<MenuItem>{
            new MenuItem{ Text = "Toolbars", Items = new List<MenuItem>{
            new MenuItem { Text= "Menu Bar" },
            new MenuItem { Text= "Bookmarks Toolbar" },
            new MenuItem { Text= "Customize" }}
    },
        new MenuItem { Text = "Zoom", Items = new List<MenuItem>{
            new MenuItem { Text= "Zoom In" },
            new MenuItem { Text= "Zoom Out" },
            new MenuItem { Text= "Reset" },}
    },
        new MenuItem { Text = "Full Screen" }}
    },
        new MenuItem{ Text = "Tools", Items = new List<MenuItem>() {
            new MenuItem { Text= "Spelling & Grammar" },
            new MenuItem { Text= "Customize" },
            new MenuItem { Separator= true },
            new MenuItem { Text= "Options" }}
    },
        new MenuItem { Text = "Help" }
    };
}

<style>
    .e-file::before {
        content: '\e30d';
    }

    .e-edit::before {
        content: '\e7a3';
    }

    .e-open::before {
        content: '\ec04';
    }

    .e-save::before {
        content: '\ec11';
    }

    .e-cut::before {
        content: '\e279';
    }

    .e-copy::before {
        content: '\e280';
    }

    .e-paste::before {
        content: '\e601';
    }
</style>
```

Output be like

![Menu Sample](./images/icons.png)

## Navigation

Navigation in Menu Bar is used to navigate to the other web page when a Menu Bar item is clicked.
It can be achieved by providing a link to the Menu Bar item using the [`Url`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Navigations.MenuItem~Url.html) property. In the following sample,
the Navigation URL is added to sub menu Bar items using the [`Url`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Navigations.MenuItem~Url.html) property.

```csharp
@using Syncfusion.Blazor.Navigations

<SfMenu Items="@MenuItems"></SfMenu>

@code {
    public List<MenuItem> MenuItems = new List<MenuItem>{
        new MenuItem{
            Text = "Appliances",
            Items = new List<MenuItem>{
                new MenuItem { Text= "Washing Machine", Url= "https://www.google.com/search?q=washing+machine" },
                new MenuItem { Text= "Air Conditioners", Url= "https://www.google.com/search?q=air+conditioners"}}
            },
            new MenuItem{
                Text = "Mobile",
                Items = new List<MenuItem>{
                    new MenuItem{ Text= "Headphones", Url= "https://www.google.com/search?q=headphones" },
                    new MenuItem{ Text= "Memory Cards", Url= "https://www.google.com/search?q=memory+cards" },
                    new MenuItem{ Text= "Power Banks", Url= "https://www.google.com/search?q=power+banks" }
                }
            },
            new MenuItem{
                Text = "Entertainment",
                Items = new List<MenuItem>(){
                    new MenuItem { Text= "Televisions", Url= "https://www.google.com/search?q=televisions" },
                    new MenuItem { Text= "Home Theatres", Url= "https://www.google.com/search?q=home+theatres" },
                    new MenuItem { Text= "Gaming Laptops", Url= "https://www.google.com/search?q=gaming+laptops" }
                }
            },
                    new MenuItem { Text = "Fashion", Url = "https://www.google.com/search?q=fashion"},
                    new MenuItem { Text = "Offers", Url = "https://www.google.com/search?q=offers" }
                };
}
```

Output be like

![Menu Sample](./images/navigation.png)

## Multilevel nesting

The Menu Bar supports multiple level nesting, and it can be achieved by mapping the [`Items`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Navigations.MenuItem~Items.html)
property inside the parent `MenuItems`.
In the following sample, three-level nesting of Menu Bar has been provided.

```csharp
@using Syncfusion.Blazor.Navigations

<SfMenu Items="@MenuItems"></SfMenu>

@code{
    public List<MenuItem> MenuItems = new List<MenuItem>{
          new MenuItem{ Text = "Fashion", Items = new List<MenuItem>{
          new MenuItem{ Text = "Men Fashion", Items = new List<MenuItem>{
          new MenuItem{ Text = "Personal Care", Items = new List<MenuItem>{
                  new MenuItem{ Text = "Trimmers"},
                  new MenuItem{ Text = "Shavers"} }
              },
          new MenuItem{ Text = "Clothing", Items = new List<MenuItem>{
              new MenuItem{ Text = "shirts"},
              new MenuItem{ Text = "Jackets"},
              new MenuItem{ Text = "TrackSuits"} }
          },
              new MenuItem{ Text = "Footwear"}
          } },
           new MenuItem{ Text = "Women Fashion", Items = new List<MenuItem>{
           new MenuItem{ Text = "Clothing", Items = new List<MenuItem> {
              new MenuItem{ Text = "Salwars"},
              new MenuItem{ Text = "Kurtas"},
              new MenuItem{ Text = "Sarees"}   }
          },
          new MenuItem{ Text = "Jewellery", Items = new List<MenuItem>{
              new MenuItem{ Text = "Nosepin"},
              new MenuItem{ Text = "Anklets"} }
          }, }
          } } },
          new MenuItem{ Text = "Home & Living", Items = new List<MenuItem>{
              new MenuItem{ Text = "Washing Machine", Items = new List<MenuItem>{
                  new MenuItem{ Text = "Fully Automatic"},
                  new MenuItem{ Text = "Semi Automatic"}  }
          },
          new MenuItem{ Text = "Air Conditioners", Items = new List<MenuItem>{
              new MenuItem{ Text = "Inverter AC"},
              new MenuItem{ Text = "Split AC"} }
          },
          } },
          new MenuItem{ Text = "Accessories"},
          new MenuItem{ Text = "Sports"},
          new MenuItem{ Text = "Gaming"}
      };
};
```

Output be like

![Menu Sample](./images/multilevel.png)