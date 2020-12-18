---
title: "Customize Menu Items"
component: "Menu Bar"
description: "This section helps to learn how to Customize Menu Items."
---

# Customize Menu Items

## Add or Remove Menu Items

Menu items can be added or removed using the [`InsertAfter`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Navigations.SfContextMenu~InsertAfter.html), [`InsertBefore`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Navigations.SfContextMenu~InsertBefore.html) and [`RemoveItems`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Navigations.SfContextMenu~RemoveItems.html) methods.

In the following example, the `Europe` menu items are added before the Oceania item, the `Africa` menu items are added after the Asia, and the South America and Mexico items are removed from menu.

```csharp

@using Syncfusion.Blazor.Navigations

<SfMenu Items="@MenuItems" @ref="MenuObj">
    <MenuEvents Created="@Created"></MenuEvents>
    <MenuFieldSettings Text="@TextValues" Children="@ChildrenValues"></MenuFieldSettings>
</SfMenu>

@code{
    SfMenu MenuObj;
    public string[] TextValues = new string[] { "Continent", "Country" };
    public string[] ChildrenValues = new string[] { "Countries" };

    public List<CountryData> MenuItems = new List<CountryData>{
        new CountryData{ Continent = "Asia", Countries = new List<CountryData>{
            new CountryData{ Country= "China" },
            new CountryData{ Country= "India" },
            new CountryData{ Country= "Japan" }}
    },
        new CountryData{ Continent = "North America", Countries = new List<CountryData>{
            new CountryData{ Country= "Canada" },
            new CountryData{ Country= "Mexico" },
            new CountryData{ Country= "USA" }}
    },
        new CountryData{ Continent = "South America", Countries = new List<CountryData>{
            new CountryData{ Country = "Brazil" },
            new CountryData{ Country = "Colombia" },
            new CountryData{ Country = "Argentina" }}
    },
        new CountryData{ Continent = "Oceania", Countries = new List<CountryData>{
            new CountryData{ Country= "Australia" },
            new CountryData{ Country= "NewZealand" },
            new CountryData{ Country= "Samoa" }}
    },
        new CountryData{ Continent = "Antartica" }
    };

    public class CountryData
    {
        public string Country { get; set; }
        public string Continent { get; set; }
        public List<CountryData> Countries { get; set; }
    }

    public List<CountryData> EuropeCountries = new List<CountryData>
    {
        new CountryData{ Continent = "Europe", Countries = new List<CountryData>
        {
            new CountryData{ Country = "Austria"},
            new CountryData{ Country = "Germany"}
        }
    }
    };

    public List<CountryData> AfricaCountries = new List<CountryData>
    {
        new CountryData{ Continent = "Africa", Countries = new List<CountryData>
        {
            new CountryData{ Country = "Nigeria"},
            new CountryData{ Country = "Ethiopia"}
        }
    }
    };

    public void Created()
    {
        this.MenuObj.InsertBefore(EuropeCountries, "Oceania", false);
        this.MenuObj.InsertAfter(AfricaCountries, "Asia", false);
        this.MenuObj.RemoveItems(new string[] { "South America", "Mexico" }, false);
    }
}

```

Output be like

![Menu Sample](./../images/menu-insertbefore.png)

## Enable or Disable Menu Items

You can enable and disable the menu items using the [`EnableItems`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Navigations.SfContextMenu~EnableItems.html) method in Menu. To enable menuItems, set the `Enable` property in argument to true and vice-versa.

In the following example, the Directory header item, Conferences, and Music sub menu items are disabled.

```csharp

@using Syncfusion.Blazor.Navigations
@using Syncfusion.Blazor.Buttons

<SfMenu Items="@MenuItems" @ref="MenuObj">
    <MenuEvents Created="@Created"></MenuEvents>
</SfMenu>
<SfButton @onclick="EnableItems">Enable all items</SfButton>

@code {
    SfMenu MenuObj;
    public List<MenuItem> MenuItems = new List<MenuItem>{
        new MenuItem{ Text = "Events", Items = new List<MenuItem>{
            new MenuItem{ Text= "Conferences" },
            new MenuItem{ Text= "Music" },
            new MenuItem{ Text= "Workshops" }}
    },
        new MenuItem{ Text = "Movies", Items = new List<MenuItem>{
            new MenuItem{ Text= "Now Showing" },
            new MenuItem{ Text= "Coming Soon" } }
    },
        new MenuItem{ Text = "Directory", Items = new List<MenuItem>{
            new MenuItem{ Text = "Newsletter" },
            new MenuItem{ Text = "Media Gallery" } }
    },
        new MenuItem{ Text = "Queries", Items = new List<MenuItem>{
            new MenuItem{ Text= "Our Policy" },
            new MenuItem{ Text= "Site Map" }}
    },
        new MenuItem{ Text = "Services" }
    };

    public string[] Items = new string[] { "Conferences", "Music", "Directory" };

    public void Created()
    {
        this.MenuObj.EnableItems(Items, false, false);
    }

    public void EnableItems()
    {
        this.MenuObj.EnableItems(Items, true, false);
    }
}

```

Output be like

![Menu Sample](./../images/menu-enable.png)

## Show or Hide Menu Items

You can show or hide the menu items using the [`ShowItems`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Navigations.SfContextMenu~ShowItems.html) and [`HideItems`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Navigations.SfContextMenu~HideItems.html) methods.

In the following example, the Movies header item, Workshops, and Music sub menu items are hidden in menu.

```csharp

@using Syncfusion.Blazor.Navigations
@using Syncfusion.Blazor.Buttons

<SfMenu Items="@MenuItems" @ref="MenuObj">
    <MenuEvents Created="@Created"></MenuEvents>
</SfMenu>
<SfButton @onclick="ShowItems">Show all items</SfButton>

@code {
    SfMenu MenuObj;
    public List<MenuItem> MenuItems = new List<MenuItem>{
        new MenuItem{ Text = "Events", Items = new List<MenuItem>{
            new MenuItem{ Text= "Conferences" },
            new MenuItem{ Text= "Music" },
            new MenuItem{ Text= "Workshops" }}
    },
        new MenuItem{ Text = "Movies", Items = new List<MenuItem>{
            new MenuItem{ Text= "Now Showing" },
            new MenuItem{ Text= "Coming Soon" } }
    },
        new MenuItem{ Text = "Directory", Items = new List<MenuItem>{
            new MenuItem{ Text = "Newsletter" },
            new MenuItem{ Text = "Media Gallery" } }
    },
        new MenuItem{ Text = "Queries", Items = new List<MenuItem>{
            new MenuItem{ Text= "Our Policy" },
            new MenuItem{ Text= "Site Map" }}
    },
        new MenuItem{ Text = "Services" }
    };

    public string[] Items = new string[] { "Workshops", "Music", "Movies" };

    public void Created()
    {
        this.MenuObj.HideItems(Items, false);
    }

    public void ShowItems()
    {
        this.MenuObj.ShowItems(Items, false);
    }
}

```

Output be like

![Menu Sample](./../images/menu-show.png)