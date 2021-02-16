# Disable a DropDownButton

DropdownButton component can be enabled/disabled by giving [`disabled`](https://help.syncfusion.com/cr/cref_files/aspnetcore-blazor/Syncfusion.EJ2.RazorComponents~Syncfusion.EJ2.RazorComponents.SplitButtons.EjsDropDownButton~Disabled.html) property.
To disable DropdownButton component, the disabled property can be set as `true`.

`Index.razor`

```csharp

<EjsDropDownButton ID="disabled" Items="@items" Content="Message" IconCss="e-icons e-search" Disabled="true"></EjsDropDownButton>

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