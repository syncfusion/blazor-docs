---
title: "States | ASP.NET Core Blazor "
component: "ProgressBar"
description: "Visualize progress in different states."
---

# States

Visualize progress in different states.

## Determinate

<!-- markdownlint-disable MD033 -->

This is the default state. You can use it when the progress estimation is known.

```csharp
    <SfProgressBar Type="ProgressType.Linear" Value="100" Height="60" Minimum="0" Maximum="100">
    </SfProgressBar>
```

![progress bar](images/determinate.png)

## Indeterminate

By enabling the **IsIndeterminate** property, the state of the progress bar can be changed to indeterminate when the progress cannot be estimated or is not being calculated. It can be combined with determinate mode to know that the application is estimating progress before the actual progress starts.

```csharp
    <SfProgressBar Type="ProgressType.Linear" Value="20" Height="60" IsIndeterminate="true" Minimum="0" Maximum="100">
    </SfProgressBar>
```

![progress bar](images/indeterminate.png)

## Buffer

<!-- markdownlint-disable MD033 -->
You can use a secondary progress indicator when the primary progress depends on the secondary progress. This will allow users to visualize both primary and secondary progress simultaneously.

```csharp
    <SfProgressBar Type="ProgressType.Linear" Value="40" Height="60" SecondaryProgress="60" Minimum="0" Maximum="100">
    </SfProgressBar>
```

![progress bar](images/buffer.png)
