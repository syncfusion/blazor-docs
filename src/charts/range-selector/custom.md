# Customization

## Navigator appearance

The navigator can be customized using the [`NavigatorStyleSettings`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.RangeNavigatorStyleSettings.html) property. The [`SelectedRegionColor`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.RangeNavigatorStyleSettings.html#Syncfusion_Blazor_Charts_RangeNavigatorStyleSettings_SelectedRegionColor) property is used to specify the color for selected region whereas the [`UnSelectedRegionColor`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.RangeNavigatorStyleSettings.html#Syncfusion_Blazor_Charts_RangeNavigatorStyleSettings_UnselectedRegionColor) property is used to specify the color for unselected region.

{% aspTab template="range-navigator/custom/appearance", sourceFiles="appearance.razor" %}

{% endaspTab %}

![Navigator](images/custom/appearance.png)

## Thumb

The [`Thumb`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.RangeNavigatorStyleSettings.html#Syncfusion_Blazor_Charts_RangeNavigatorStyleSettings_Thumb) property provides options to customize the Border, Fill, Size, and Type of thumb. The types of thumb can be `Circle` and `Rectangle`.

{% aspTab template="range-navigator/custom/thumb", sourceFiles="thumb.razor" %}

{% endaspTab %}

![Thumb](images/custom/thumb.png)

## Border customization

Using the [`NavigatorBorder`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartSeries.html#Syncfusion_Blazor_Charts_ChartSeries_IsClosed) property, you can customize the [`Width`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.RangeNavigatorBorder.html#Syncfusion_Blazor_Charts_RangeNavigatorBorder_Width) and [`Color`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.RangeNavigatorBorder.html#Syncfusion_Blazor_Charts_RangeNavigatorBorder_Color) of the range navigator.

{% aspTab template="range-navigator/custom/border", sourceFiles="border.razor" %}

{% endaspTab %}

![Border](images/custom/border.png)

## Allow snapping

The [`AllowSnapping`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.RangeNavigatorModel.html#Syncfusion_Blazor_Charts_RangeNavigatorModel_AllowSnapping) property toggles the placement of the slider exactly to the left or on the nearest interval.

{% aspTab template="range-navigator/custom/snap", sourceFiles="snap.razor" %}

{% endaspTab %}

## See Also

* [Grid and Tick Lines](./grid-tick/)
* [Labels](./labels/)