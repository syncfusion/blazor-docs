---
title: "Data source binding"
component: "Menu Bar"
description: "This section helps to learn how to bind data source and custom Menu Bar items"
---

# Data source binding

## Data binding

The Menu Bar supports data source bindings such as data source that can be structured as either `Hierarchical` or `Self-referential` data.

### Hierarchical data

The Menu Bar can be populated with hierarchical data source by assigning it to the [`Items`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Navigations.SfMenu~Items.html) property, and the fields with corresponding keys can be mapped to the [`Fields`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Navigations.SfMenu~Fields.html) property.

#### JSON data

The Menu Bar can generate its menu items through an complex data source by mapping fields from the [`Fields`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Navigations.SfMenu~Fields.html) property.

```csharp

@using Syncfusion.Blazor.Navigations

<SfMenu Items="@MenuItems" Fields="@MenuFields"></SfMenu>

@code {
    public List<CountryData> MenuItems = new List<CountryData>{
       new CountryData{ Continent="Asia",
                        Countries = new List<CountryData>{
                            new CountryData { Country="China", Languages= new List<CountryData> {
                                new CountryData {Language = "Chinese" }, new CountryData { Language = "Cantonese"} } },
                            new CountryData{ Country="India", Languages = new List<CountryData> {
                                new CountryData { Language = "English" }, new CountryData { Language = "Hindi" }, new CountryData { Language = "Tamil" } } },
                            new CountryData { Country="Japan", Languages= new List<CountryData>{
                                new CountryData{ Language = "Japanese" } } },
                        } },
       new CountryData{ Continent="Africa",
                        Countries = new List<CountryData>{
                            new CountryData { Country="Nigeria", Languages= new List<CountryData> {
                                new CountryData {Language = "English" }, new CountryData { Language = "Hausa"} } } ,
                            new CountryData{ Country="Egypt", Languages = new List<CountryData> {
                                new CountryData { Language = "Arabic" } } },
                            new CountryData { Country="South Africa", Languages= new List<CountryData>{
                                new CountryData{ Language = "Tswana"}, new CountryData{ Language = "swati"} } },
                        } },
       new CountryData{ Continent="North America",
                        Countries = new List<CountryData>{
                            new CountryData { Country="Canada", Languages= new List<CountryData> {
                                new CountryData {Language = "French" } } } ,
                            new CountryData{ Country="Mexico", Languages = new List<CountryData> {
                                new CountryData { Language = "Spanish" } } },
                            new CountryData { Country="USA", Languages= new List<CountryData>{
                                new CountryData{ Language = "English"} } },
                        } },
       new CountryData{ Continent="South America",
                        Countries = new List<CountryData>{
                            new CountryData { Country="Brazil", Languages= new List<CountryData> {
                                new CountryData {Language = "Portuguese" } } } ,
                            new CountryData{ Country="Colombia", Languages = new List<CountryData> {
                                new CountryData { Language = "Spanish" } } },
                            new CountryData { Country="Argentina", Languages= new List<CountryData>{
                                new CountryData{ Language = "Spanish"} } },
                        } },
       new CountryData{ Continent="Oceania",
                        Countries = new List<CountryData>{
                            new CountryData { Country="New Zealand" } ,
                            new CountryData{ Country="Australia" },
                            new CountryData { Country="Samoa" }
                        } }
        };

    public MenuFieldSettings MenuFields = new MenuFieldSettings()
    {
        Text = new string[] { "Continent", "Country", "Language" },
        Children = new string[] { "Countries", "Languages" }
    };

    public class CountryData
    {
        public string Country { get; set; }
        public string Continent { get; set; }
        public List<CountryData> Countries { get; set; }
        public List<CountryData> Languages { get; set; }
        public string Language { get; set; }
    }
}

```

Output be like

![Menu Sample](./images/menu-db.png)

#### Self-referential data

Menu Bar can be populated from self-referential data structure that contains data with `ParentId` mapping.

In the following example, the **id**, **pId**, and **text** columns from self-referential data have been mapped to the [`ItemId`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Navigations.MenuFieldSettings~ItemId.html), [`ParentId`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Navigations.MenuFieldSettings~ParentId.html), and [`Text`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Navigations.MenuFieldSettings~Text.html) fields, respectively.

```csharp

@using Syncfusion.Blazor.Navigations

<SfMenu Items="@MenuItems" Fields="@MenuFields"></SfMenu>

@code {
    public List<CustomMenuItem> MenuItems = new List<CustomMenuItem>
        {
        new CustomMenuItem{ Id = "parent1", Text = "Events" },
        new CustomMenuItem{ Id = "parent2", Text = "Movies" },
        new CustomMenuItem{ Id = "parent3", Text = "Directory" },
        new CustomMenuItem{ Id = "parent4", Text = "Queries", ParentId = "null"  },
        new CustomMenuItem{ Id = "parent5", Text = "Services", ParentId = "null" },
        new CustomMenuItem{ Id = "parent6", Text = "Conferences", ParentId = "parent1" },
        new CustomMenuItem{ Id = "parent7", Text = "Music", ParentId = "parent1" },
        new CustomMenuItem{ Id = "parent8", Text = "Workshops", ParentId = "parent1" },

        new CustomMenuItem{ Id = "parent9", Text = "Now Showing", ParentId = "parent2" },
        new CustomMenuItem{ Id = "parent10", Text = "Coming Soon", ParentId = "parent2" },

        new CustomMenuItem{ Id = "parent10", Text = "Media Gallery", ParentId = "parent3" },
        new CustomMenuItem{ Id = "parent11", Text = "Newsletters", ParentId = "parent3" },

        new CustomMenuItem{ Id = "parent12", Text = "Our Policy", ParentId = "parent4" },
        new CustomMenuItem{ Id = "parent13", Text = "Site Map", ParentId = "parent4" },
        new CustomMenuItem{ Id = "parent14", Text = "Pop", ParentId = "parent7" },
        new CustomMenuItem{ Id = "parent15", Text = "Folk", ParentId = "parent7" },
        new CustomMenuItem{ Id = "parent16", Text = "Classical", ParentId = "parent7" }

        };

    public MenuFieldSettings MenuFields = new MenuFieldSettings()
    {
        ItemId = "Id",
        Text = "Text",
        ParentId = "ParentId"
    };

    public class CustomMenuItem
    {
        public string Id { get; set; }
        public string Text { get; set; }
        public string ParentId { get; set; }
    }
}


```

Output be like

![Menu Sample](./images/menu-db2.png)

## Custom Menu Bar Items

To customize Menu Bar items in your application, set your customized template using [`MenuTemplates`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Navigations.MenuTemplates.html). In the following example, the Menu Bar has been rendered with customized Menu Bar items.

```csharp

@using Syncfusion.Blazor.Navigations
@inject Microsoft.AspNetCore.Components.IUriHelper UriHelper

<div class="menu-control">
    <SfMenu Items="@data" Fields="@MenuFields" ModelType="@MenuTemplateModel">
        <MenuTemplates>
            <Template>
                @{
                    var MenuItems = (context as CategoryModel);
                    if (@MenuItems.Category != null)
                    {
                        <div>@(@MenuItems.Category)</div>
                    }
                    else if (@MenuItems.Value != null)
                    {
                        <div style="width: 100%;display: flex;justify-content: space-between;">
                            @{
                                if (@MenuItems.Url != null)
                                {
                                    <img class="e-avatar e-avatar-small" src="@UriHelper.ToAbsoluteUri($"images/MenuBar/{MenuItems.Url}.png")" />
                                }
                                <span style="width:100%;">@MenuItems.Value</span>
                                if (@MenuItems.Count != null)
                                {
                                    <span class="e-badge e-badge-success">@MenuItems.Count</span>
                                }
                            }
                        </div>
                    }
                    else
                    {
                        <div tabindex="0" class="e-card">
                            <div class="e-card-header">
                                <div class="e-card-header-caption">
                                    <div class="e-card-header-title">About Us</div>
                                </div>
                            </div>
                            <div class="e-card-content">
                                @MenuItems.About
                            </div>
                            <div class="e-card-actions">
                                <input type="button" class="e-btn e-outline" style="pointer-events: auto;" value="Read More" />

                            </div>
                        </div>
                    }
                }
            </Template>
        </MenuTemplates>
    </SfMenu>
</div>

@code{

    CategoryModel MenuTemplateModel = new CategoryModel();

    private List<CategoryModel>data = new List<CategoryModel>
    {
        new CategoryModel {
        Category = "Products",
        Options = new List<CategoryModel>{
            new CategoryModel { Value= "JavaScript", Url= "javascript" },
            new CategoryModel { Value= "Angular", Url= "angular" },
            new CategoryModel { Value= "ASP.NET Core", Url= "core" },
            new CategoryModel { Value= "ASP.NET MVC", Url= "mvc" }
        }
    },

        new CategoryModel{
        Category = "Services",
        Options = new List<CategoryModel>{
            new CategoryModel { Value= "Application Development", Count= "1200+" },
            new CategoryModel { Value= "Maintenance & Support", Count= "3700+" },
            new CategoryModel { Value= "Quality Assurance" },
            new CategoryModel { Value= "Cloud Integration", Count= "900+" }
        }
    },

        new CategoryModel{
        Category = "About Us",
        Options =  new List<CategoryModel>{
            new CategoryModel{ id = "about", About = "We are on a mission to provide world-class best software solutions for web, mobile and desktop platforms. Around 900+ applications are desgined and delivered to our customers to make digital & strengthen their businesses." }
        }
    },
        new CategoryModel { Category = "Careers" },
        new CategoryModel { Category = "Sign In" }
    };

    MenuFieldSettings MenuFields = new MenuFieldSettings()
    {
        Text = new string[] { "Category", "Value" },
        Children = new string[] { "Options" }
    };

    private class CategoryModel
    {
        public string Category { get; set; }
        public List<CategoryModel>Options { get; set; }
        public string Value { get; set; }
        public string Url { get; set; }
        public string Count { get; set; }
        public string id { get; set; }
        public string About { get; set; }
        public string IconCss { get; set; }
    }
}

<style>
    .menu-control {
        margin-top: 45px;
        text-align: center;
    }

    /* Common ul & li styles */
    .e-bigger .e-menu-wrapper ul.e-ul,
    .e-menu-wrapper ul.e-ul {
        padding: 0;
    }

        .e-bigger .e-menu-wrapper ul.e-ul .e-menu-item,
        .e-menu-wrapper ul.e-ul .e-menu-item {
            display: flex;
            padding: 0 10px;
            outline-color: transparent;
        }

    /** Avatar customization */
    .e-menu-wrapper ul .e-menu-item .e-avatar {
        background-color: inherit;
        font-size: 8px;
        margin-right: 8px;
        align-self: center;
        width: auto;
        overflow: visible;
    }

    .e-bigger .e-menu-wrapper ul .e-menu-item .e-avatar {
        font-size: 10px;
    }

    /** Badge customization */
    .e-menu-wrapper ul .e-menu-item .e-badge {
        margin-left: 10px;
        align-self: center;
        overflow: visible;
    }

    /** Card customization */
    .e-menu-wrapper ul.e-ul .e-menu-item .e-card {
        width: 290px;
        font-size: inherit;
        background-color: inherit;
        border-color: transparent;
    }

    .e-bigger .e-menu-wrapper ul.e-ul .e-menu-item .e-card {
        width: 320px;
    }

    .e-menu-wrapper ul.e-ul .e-menu-item .e-card .e-card-content {
        white-space: normal;
        color: inherit;
        padding-top: 0;
        text-align: justify;
        font-size: inherit;
    }

    .e-menu-wrapper ul.e-ul .e-menu-item#about {
        height: auto;
        padding: 0;
    }

    .e-menu-wrapper ul.e-ul .e-menu-item#about.e-focused {
        background-color: transparent;
        outline-color: transparent;
        pointer-events: none;
    }

</style>

```

Output be like

![Menu Sample](./images/menu-templates.png)