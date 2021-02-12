---
component: "Diagram"
---

# Virtualization

## Virtualization in Diagram

Virtualization is the process of loading the diagramming objects available in the visible area of the Diagram control, that is, only the diagramming objects that lie within the `ViewPort` of the Scroll Viewer are loaded (remaining objects are loaded only when they come into view).

This feature gives an optimized performance while loading and dragging items to the Diagram that consists of many Nodes and Connectors.

The following code illustrates how to enable [`Virtualization`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Diagrams.DiagramConstraints.html) mode in the diagram.

```csharp
@using Syncfusion.Blazor.Diagrams

@* Initialize Diagram *@
<SfDiagram Height="600px" Constraints="@Constraints">
</SfDiagram>

@code{
    public DiagramConstraints Constraints = DiagramConstraints.Default | DiagramConstraints.Virtualization;
}

```
