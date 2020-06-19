---
title: " RangeNavigator Customization | ASP.NET Core Blazor "

component: "RangeNavigator"

description: "Range navigator can be customized using the navigatorBorder, navigatorStyleSettings, seleced or unselected region color properties."
---

# Customization

## Navigator appearance

The navigator can be customized using the [`NavigatorStyleSettings`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.RangeNavigatorStyleSettings.html) property. The [`SelectedRegionColor`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.RangeNavigatorStyleSettings~SelectedRegionColor.html) property is used to specify the color for selected region whereas the [`UnSelectedRegionColor`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.RangeNavigatorStyleSettings~UnselectedRegionColor.html) property is used to specify the color for unselected region.

{% aspTab template="range-navigator/custom/appearance", sourceFiles="appearance.razor" %}

{% endaspTab %}

![Navigator](images/custom/appearance.png)

## Thumb

The [`Thumb`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.RangeNavigatorStyleSettings~Thumb.html) property provides options to customize the Border, Fill, Size, and Type of thumb. The types of thumb can be `Circle` and `Rectangle`.

{% aspTab template="range-navigator/custom/thumb", sourceFiles="thumb.razor" %}

{% endaspTab %}

![Thumb](images/custom/thumb.png)

## Border customization

Using the [`NavigatorBorder`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.EjsRangeNavigator~NavigatorBorder.html) property, you can customize the [`Width`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.RangeNavigatorBorder~Width.html) and [`Color`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.RangeNavigatorBorder~Color.html) of the range navigator.

{% aspTab template="range-navigator/custom/border", sourceFiles="border.razor" %}

{% endaspTab %}

![Border](images/custom/border.png)

## Deferred update

If the [`EnableDeferredUpdate`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.RangeNavigatorModel~EnableDeferredUpdate.html) property is set to true, then the changed event will be fired after dragging the slider.
If the `EnableDeferredUpdate` is false, then the changed event will be fired when dragging the slider. By default,
the `EnableDeferredUpdate` is set to false.

## Allow snapping

The [`AllowSnapping`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.RangeNavigatorModel~AllowSnapping.html) property toggles the placement of the slider exactly to the left or on the nearest interval.

{% aspTab template="range-navigator/custom/snap", sourceFiles="snap.razor" %}

{% endaspTab %}

## Animation

The speed of the animation can be controlled using the [`AnimationDuration`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Charts.RangeNavigatorModel~AnimationDuration.html) property. The default value of the `AnimationDuration` property is 500 milliseconds.

{% aspTab template="range-navigator/custom/animation", sourceFiles="animation.razor" %}

{% endaspTab %}

## See Also

* [Grid and Tick Lines](./grid-tick/)
* [Labels](./labels/)