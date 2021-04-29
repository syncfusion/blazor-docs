---
title: "Methods in Blazor Sparkline component | Syncfusion"

component: "Sparkline"

description: "Learn here all about methods of Syncfusion Sparkline (SfSparkline) component and more."
---

# Methods in Blazor Sparkline (SfSparkline)

Using the `@ref` property, create an object for the Sparkline component and call the desired method.

## Refresh

The refresh method helps to render the Sparkline component again.

```csharp
@using Syncfusion.Blazor.Charts

<button @onclick="RefreshCall">Refresh</button>
<SfSparkline @ref="@Sparkline" DataSource="new int[]{ 3, 6, 4, 1, 3, 2, 5 }" Type="SparklineType.Area" Height="200px" Width="350px" Fill="#b2cfff" LineWidth="1">
</SfSparkline>

@code
{
    public SfSparkline<int> Sparkline { get; set; }
    public async Task RefreshCall()
    {
        await Sparkline.Refresh();
    }
}
```