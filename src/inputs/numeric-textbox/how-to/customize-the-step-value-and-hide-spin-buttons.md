# Customize the step value and hide spin buttons

The spin buttons allows you to increase or decrease the value with the predefined [Step](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Inputs.SfNumericTextBox%601~Step.html)
value. The visibility of spin buttons can be set using the [ShowSpinButton](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Inputs.SfNumericTextBox%601~ShowSpinButton.html) property.

```csharp
@using Syncfusion.Blazor.Inputs

<SfNumericTextBox TValue="int?" Value=10 Min=10 Max=100 Step=2 ShowSpinButton=false></SfNumericTextBox>
```

The output will be as follows.

![NumericTextBox Sample](../images/icon_disable.png)
