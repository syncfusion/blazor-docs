# Constraints

Constraints are used to enable or disable certain behaviors of the diagram, nodes, and connectors. Constraints are provided as flagged enumerations, so that multiple behaviors can be enabled or disabled using the Bitwise operators (&, |, ~, <<, etc.).

To know more about Bitwise operators, refer to the [`Bitwise Operations`](#bitwise-operations).

## Diagram constraints

Diagram constraints allow you to enable or disable the following behaviors. By default, `UndoRedo` , `UserInteraction` , `ApiUpdate` , `PageEditable` , `Zoom` , `Pan` constraints are enabled for diagram.

| Constraints | Description |
| -------- | -------- |
|None|Disable all diagram functionalities|
|Bridging|Enables or Disable Bridging support for connector in diagram|
|Undo/redo|Enables or Disable the Undo/Redo support for the diagram|
|UserInteraction|Enables or Disable user interaction support for the diagram|
|ApiUpdate|Enables or Disable update API support for the diagram|
|PageEditable|Enables or Disable Page Editable support for the diagram|
|Zoom|Enables or Disable Zoom support for the diagram|
|PanX|Enables or Disable Paning X coordinate support for the diagram|
|PanY|Enables or Disable Paning Y coordinate support for the diagram|
|Pan|Enables or Disable panning both X and Y coordinates support for the diagram|
|ZoomTextEdit|Enables or Disables zooming the text box while editing the text|
|Virtualization|Enables or Disable Virtualization support the diagram|
|Default|Enables or Disable all constraints in diagram|

The following example shows how to disable PageEditable constraint from default diagram constraints.

```csharp
@using Syncfusion.Blazor.Diagram

@* Initialize the diagram with constraints *@
<SfDiagramComponent Height="600px" Nodes="@NodeCollection" Constraints="@DiagramConstraints">
</SfDiagramComponent>
@code{
    //sets the Diagram constraints...
    DiagramConstraints DiagramConstraints = DiagramConstraints.Default & ~DiagramConstraints.PageEditable;
    //Initialize the Nodes Collection.
    DiagramObjectCollection<Node> NodeCollection;
    protected override void OnInitialized()
    {
        NodeCollection = new DiagramObjectCollection<Node>();
        Node node = new Node()
        {
            ID = "node1",
            Height = 100,
            Width = 100,
            OffsetX = 100,
            OffsetY = 100,
        };
        NodeCollection.Add(node);
    }
}
```

The following example shows how to add Bridging constraint to the default constraints of diagram.

```csharp

DiagramConstraints DiagramConstraints = DiagramConstraints.Default | DiagramConstraints.Bridging;

```

The diagram constraints are provided as flagged enumerations, so that multiple behaviors can be added or removed from the default constraints using the [`Bitwise Operations`](#bitwise-operations) in the diagram.

```csharp
 //Removing multiple constraints from default
DiagramConstraints DiagramConstraints = DiagramConstraints.Default & ~(DiagramConstraints.PageEditable|DiagramConstraints.Zoom);

```

For more information about diagram constraints, refer to the `DiagramConstraints`.

## Node constraints

Node constraints allows you to enable or disable the following behaviors of node.  By default, `Select` , `Drag` , `Resize` , `Rotate` , `Delete` ,`InConnect` ,`OutConnect` constraints are enabled for the node.

| Constraints | Description |
| -------- | -------- |
|None|Disable all node Constraints|
|Select|Enables or Disables node to be selected|
|Drag|Enables or Disables node to be Dragged|
|Rotate|Enables or Disables node to be rotating|
|Shadow|Enables or disables node to display shadow|
|PointerEvents|Enables or disables node to provide pointer option|
|Delete|Enables or Disables node to be deleting|
|InConnect|Enables or disables node to provide in connect option|
|OutConnect|Enables or disables node to provide out connect option|
|AllowDrop|Enables node to provide allow to drop option|
|ResizeNorthEast|Enable or disable to Resizing NorthEast side of the node|
|ResizeEast|Enable or disable to Resizing East side of the node|
|ResizeSouthEast|Enable or disable to Resizing SouthEast side of the node|
|ResizeSouth|Enable or disable to Resizing South side of the node|
|ResizeSouthWest|Enable or disable to Resizing SouthWest side of the node|
|ResizeWest|Enable or disable to Resizing West side of the node|
|ResizeNorthWest|Enable or disable to Resizing NorthWest side of the node|
|ResizeNorth|Enable or disable to Resizing North side of the node|
|AspectRatio|Enables the Aspect ratio of the node|
|ReadOnly|Enables the  ReadOnly support for annotation in node|
|HideThumbs|Enable to hide all resize thumbs for the node|
|Resize|Enables or Disables the expansion or compression of a node|
|Inherit|Enables the node to inherit the interaction option from the parent object|
|Default|Enables all default constraints for the node|

The following example shows how to disable rotate constraint from the default node constraints.

```csharp
@using Syncfusion.Blazor.Diagram

@* Initialize the diagram with NodeCollection *@
<SfDiagramComponent Height="600px" Nodes="@NodeCollection">
</SfDiagramComponent>

@code{

    DiagramObjectCollection<Node> NodeCollection;
    protected override void OnInitialized()
    {
        NodeCollection = new DiagramObjectCollection<Node>();
        Node node = new Node()
        {
            ID = "node1",
            Height = 100,
            Width = 100,
            OffsetX = 100,
            OffsetY = 100,
            //sets the NodeConstraints constraints...
            Constraints = NodeConstraints.Default & ~NodeConstraints.Rotate
        };
        NodeCollection.Add(node);
    }
}
```

The following example shows how to add Shadow constraint to the default constraints of node.

```csharp

NodeConstraints NodeConstraints = NodeConstraints.Default | NodeConstraints.Shadow;

```

The node constraints are provided as flagged enumerations, so that multiple behaviors can be added or removed from the default constraints using the [`Bitwise Operations`](#bitwise-operations).

```csharp
 //Removing multiple constraints from default
NodeConstraints NodeConstraints = NodeConstraints.Default & ~ (NodeConstraints.Select | NodeConstraints.Drag);

```

For more information about node constraints, refer to the `NodeConstraints`.

## Connector constraints

Connector constraints allow you to enable or disable the following behaviors of connectors. By default,
`Select`, `Drag`, `DragSourceEnd`, `DragTargetEnd`, `Delete`, `InheritBridging`, `PointerEvents` constraints are enabled for the connector.

| Constraints | Description |
| -------- | -------- |
|None|Disable all connector Constraints|
|Select|Enables or Disables node to be selected|
|Delete|Enables or Disables node to be deleting|
|Drag|Enables or Disables node to be Dragged|
|DragSourceEnd|Enables connectors source end to be selected|
|DragTargetEnd|Enables connectors target end to be selected|
|DragSegmentThumb|Enables control point and end point of every segment in a connector for editing|
|Interaction|Enables or disables Interaction for the connector|
|AllowDrop|Enables allow drop support to the connector|
|Bridging|Enables bridging to the connector|
|InheritBridging|Enables to inherit bridging option from the parent object|
|PointerEvents|Enables to set the pointer events|
|ConnectToNearByNode|Enables to connect to the nearest node|
|ConnectToNearByPort|Enables to connect to the nearest port|
|ConnectToNearByElement|Enables to connect to the nearest elements|
|ReadOnly|Enables or disables readonly for the connector|
|Default|Enables all constraints for the connector|

The following code shows how to disable select constraint from the default constraints of connector.

```csharp
@using Syncfusion.Blazor.Diagram

@* Initialize the diagram with ConnectorCollection *@
 <SfDiagramComponent Height="600px" Connectors="@ConnectorCollection">
 </SfDiagramComponent>

@code{

    DiagramObjectCollection<Connector> ConnectorCollection;
    protected override void OnInitialized()
    {
        ConnectorCollection = new DiagramObjectCollection<Connector>();
        Connector connector = new Connector()
        {
            ID = "connector1",
            Type = Segments.Straight,
            SourcePoint = new Point() { X = 100, Y = 100 },
            TargetPoint = new Point() { X = 200, Y = 200 },
            //sets the ConnectorConstraints...
            Constraints = ConnectorConstraints.Default & ~ConnectorConstraints.Select
        };
        ConnectorCollection.Add(connector);
    }
}
```

The following example shows how to add Bridging constraint to the default constraints of connector.

```csharp

ConnectorConstraints ConnectorConstraints = ConnectorConstraints.Default | ConnectorConstraints.Bridging;

```

The connector constraints are provided as flagged enumerations, so that multiple behaviors can be added or removed from the default constraints using the [`Bitwise Operations`](#bitwise-operations).

```csharp
 //Removing multiple constraints from default
ConnectorConstraints ConnectorConstraints = ConnectorConstraints.Default & ~ (ConnectorConstraints.Select | ConnectorConstraints.Drag);

```

For more information about connector constraints, refer to the `ConnectorConstraints`.

## Port constraints

You can enable or disable the following behaviors of port. By default, `InConnect` , `OutConnect` constraints are enabled for the port.

| Constraints | Description |
| -------- | -------- |
|None|Disable all port Constraints|
|Draw|Enables to create the connection when mouse hover on the port|
|InConnect|Enables or disables to only connect the target end of connector|
|OutConnect|Enables or disables to only connect the source end of connector|
|Default|Enables all constraints for the port|

The following code shows how to disable creating connections with a port.

```csharp
@using Syncfusion.Blazor.Diagram

@* Initialize the diagram with NodeCollection *@
<SfDiagramComponent Height="600px" Nodes="@NodeCollection">
</SfDiagramComponent>

@code{

    DiagramObjectCollection<Node> NodeCollection;
    protected override void OnInitialized()
    {
        //Initialize the NodeCollection.
        NodeCollection = new DiagramObjectCollection<Node>();
        Node node = new Node()
        {
            ID = "node1",
            Height = 100,
            Width = 100,
            OffsetX = 100,
            OffsetY = 100,
        };
        node.Ports = new DiagramObjectCollection<PointPort>()
    {
            new PointPort()
            {
                ID="port1",
                Offset=new Point(){X=0,Y=0.5},
                Shape=PortShapes.Circle,
                Visibility=PortVisibility.Visible,
                //sets the PortConstraints...
                Constraints=PortConstraints.None
            }
        };
        NodeCollection.Add(node);
    }
}
```

The following another code example shows to modify the port constraints to accept target connection alone.

```csharp
//Enable to create target connection alone.
port.Constraints = PortConstraints.InConnect;
```

The port constraints are provided as flagged enumerations, so that multiple behaviors can be added or removed from the default constraints using the [`Bitwise Operations`](#bitwise-operations).

```csharp
//Enable to create target connection alone.
port.Constraints = PortConstraints.Default | PortConstraints.Draw;
```

For more information about port constraints, refer to the `PortConstraints`.

## Annotation constraints

You can enable or disable read-only mode for the annotations by using the annotation constraints.

| Constraints | Description |
| -------- | -------- |
|ReadOnly|Enables or Disables the ReadOnly Constraints|
|InheritReadOnly|Enables or Disables to inherit the ReadOnly option from the parent object|
|None|Disables all constraints for the annotation|

The following code shows how to enable read-only mode for the annotations.

```csharp
@using Syncfusion.Blazor.Diagram

@* Initialize the diagram with NodeCollection *@
<SfDiagramComponent Height="600px" Nodes="@NodeCollection">
</SfDiagramComponent>

@code{

    DiagramObjectCollection<Node> NodeCollection;
    protected override void OnInitialized()
    {
        //Initialize the NodeCollection.
        NodeCollection = new DiagramObjectCollection<Node>();
        Node node = new Node()
        {
            ID = "node1",
            Height = 100,
            Width = 100,
            OffsetX = 100,
            OffsetY = 100,
        };
        node.Annotations = new DiagramObjectCollection<ShapeAnnotation>()
    {
            new ShapeAnnotation()
            {
                ID="annotation1",
                Content="Annotation Text Wrapping",
                //sets the Constraints for Annotation...
                Constraints=AnnotationConstraints.ReadOnly,
                Style= new TextShapeStyle()
                {
                    Color="#000000",
                    Fill="Transparent",
                    FontFamily="TimesNewRoman",
                    FontSize=12,
                    Bold=true,
                    Italic=true
                },
            }
        };
        NodeCollection.Add(node);
    }
}
```

For more details about annotation constraints, refer to the `AnnotationConstraints`.

## Selector constraints

Selector visually represents the selected elements with certain editable thumbs. The visibility of the thumbs can be controlled with selector constraints. By default, `ResizeAll`, `UserHandle`, `Rotate` constraints are enabled for the selected items.

| Constraints | Description |
| -------- | -------- |
|None|Hides all the selector elements|
|ConnectorSourceThumb|Shows or hides the source thumb of the connector|
|ConnectorTargetThumb|Shows or hides the target thumb of the connector|
|ResizeSouthEast|Shows or hides the bottom right resize handle of the selector|
|ResizeSouthWest|Shows or hides the bottom left resize handle of the selector|
|ResizeNorthEast|Shows or hides the top right resize handle of the selector|
|ResizeNorthWest|Shows or hides the top left resize handle of the selector|
|ResizeEast|Shows or hides the middle right resize handle of the selector|
|ResizeWest|Shows or hides the middle left resize handle of the selector|
|ResizeSouth|Shows or hides the bottom center resize handle of the selector|
|ResizeNorth|Shows or hides the top center resize handle of the selector|
|Rotate|Shows or hides the rotate handle of the selector|
|UserHandle|Shows or hides the user handles of the selector|
|ResizeAll|Shows or hides all resize handles of the selector|
|All|Shows all handles of the selector|

The following code shows how to hide rotator.

```csharp
@using Syncfusion.Blazor.Diagram

<SfDiagramComponent Height="600px" Nodes="@NodeCollection" SelectedItems="@selectedItems">
</SfDiagramComponent>

@code{

    DiagramObjectCollection<Node> NodeCollection;
    public Selector selectedItems = new Selector() { Constraints = SelectorConstraints.All & ~SelectorConstraints.Rotate };

    protected override void OnInitialized()
    {
        //Initialize the NodeCollection.
        NodeCollection = new DiagramObjectCollection<Node>();
        Node node = new Node()
        {
            ID = "node1",
            Height = 100,
            Width = 100,
            OffsetX = 100,
            OffsetY = 100,
        };
        NodeCollection.Add(node);
    }
}
```

>* Note: Element should be in selected state, then only Rotator, UserHandle and Resizer thumbs will be visible.

The following another code example shows how to disable the userhandle functionality for the selected item.

```csharp
//Enable userhandle constraint for the selected item.
selectedItems.Constraints = SelectorConstraints.All &~ SelectorConstraints.UserHandle;
```

For more information about selector constraints, refer to the `SelectorConstraints`

## Snap constraints

Snap constraints control the visibility of gridlines and enable or disable snapping. Snap constraints allow to set the following behaviors.

* Show only horizontal or vertical gridlines.
* Show both horizontal and vertical gridlines.
* Snap to either horizontal or vertical gridlines.
* Snap to both horizontal and vertical gridlines.

By default, `ShowLines`, `SnapToLines` constraints are enabled for the snap functionality in the diagram.

The following list of snapping constraints are used to Enables or Disables certain features of snapping.

| Constraints | Description |
| -------- | -------- |
|None|Disable to snapping the nodes/connectors in diagram|
|ShowHorizontalLines|Displays only the horizontal gridlines in diagram|
|ShowVerticalLines|Displays only the Vertical gridlines in diagram|
|ShowLines|Display both Horizontal and Vertical gridlines|
|SnapToHorizontalLines|Enables the object to snap only with horizontal gridlines|
|SnapToVerticalLines|Enables the object to snap only with Vertical gridlines|
|SnapToLines|Enables the object to snap with both horizontal and Vertical gridlines|
|SnapToObject|Enables the object to snap with the other objects in the diagram|
|All|Shows gridlines and enables snapping|

The following code shows how to show only horizontal gridlines.

```csharp
@using Syncfusion.Blazor.Diagram

<SfDiagramComponent Height="600px" Nodes="@NodeCollection">
    @* Initialize the snapsettings with constraints *@
    <SnapSettings Constraints="@snapconstraints"></SnapSettings>
</SfDiagramComponent>
@code{
    DiagramObjectCollection<Node> NodeCollection;
    SnapConstraints snapconstraints;
    protected override void OnInitialized()
    {
        //Initialize the NodeCollection.
        NodeCollection = new DiagramObjectCollection<Node>();
        snapconstraints = SnapConstraints.ShowHorizontalLines;
        Node node = new Node()
        {
            ID = "node1",
            Height = 100,
            Width = 100,
            OffsetX = 100,
            OffsetY = 100,
        };
        NodeCollection.Add(node);
    }
}
```

The snap constraints are provided as flagged enumerations, so that multiple behaviors can be added or removed from the default constraints using the [`Bitwise Operations`](#bitwise-operations).

```csharp
snapconstraints = SnapConstraints.ShowHorizontalLines | SnapConstraints.ShowVerticalLines | SnapConstraints.ShowLines;
```

For more information about snap constraints, refer to the `SnapConstraints`.

## Boundary constraints

Boundary constraints defines a boundary for the diagram inside that the interaction should be done. By default, Diagram constraint is enabled for the boundary constraints in the diagram.

The following list of constraints are used to Enables or Disables certain features of boundary interactions of the diagram.

| Constraints | Description |
| -------- | -------- |
|Infinity|Allow the interactions to take place at the infinite height and width|
|Diagram|Allow the interactions to take place around the diagram height and width|
|Page|Allow the interactions to take place around the page height and width|

The following code shows how to limit the interaction done inside a diagram within a page.

```csharp
@using Syncfusion.Blazor.Diagram

<SfDiagramComponent Height="600px" Nodes="@NodeCollection">
    @* Initialize the pagesettings with boundary constraints *@
    <PageSettings Width="600" Height="500" BoundaryConstraints="BoundaryConstraints.Page"></PageSettings>
</SfDiagramComponent>

@code{
    DiagramObjectCollection<Node> NodeCollection;
    protected override void OnInitialized()
    {
        //Initialize the NodeCollection.
        NodeCollection = new DiagramObjectCollection<Node>();
        Node node = new Node()
        {
            ID = "node1",
            Height = 100,
            Width = 100,
            OffsetX = 100,
            OffsetY = 100,
        };
        NodeCollection.Add(node);
    }
}
```

For more information about selector constraints, refer to the `BoundaryConstraints`

## Inherit behaviors

Some of the behaviors can be defined through both the specific object (node or connector) and diagram. When the behaviors are contradictorily defined through both, the actual behavior is set through inherit options.

The following code example shows how to inherit the line bridging behavior from the diagram.

```csharp
@using Syncfusion.Blazor.Diagram

@* Initialize the diagram with constraints *@
<SfDiagramComponent Height="600px" Connectors="@ConnectorCollection" Constraints="@DiagramConstraints">
</SfDiagramComponent>

@code{
    //Sets the diagram constraints
    DiagramConstraints DiagramConstraints = DiagramConstraints.Default | DiagramConstraints.Bridging;
    DiagramObjectCollection<Connector> ConnectorCollection;
    protected override void OnInitialized()
    {
        ConnectorCollection = new DiagramObjectCollection<Connector>();
        Connector connector = new Connector()
        {
            ID = "connector1",
            SourcePoint = new Point() { X = 100, Y = 100 },
            TargetPoint = new Point() { X = 200, Y = 200 },
            //sets the ConnectorConstraints...
            Constraints = ConnectorConstraints.Default | ConnectorConstraints.InheritBridging
        };
        Connector connector1 = new Connector()
        {
            ID = "connector2",
            SourcePoint = new Point() { X = 200, Y = 100 },
            TargetPoint = new Point() { X = 100, Y = 200 },
        };
        ConnectorCollection.Add(connector);
        ConnectorCollection.Add(connector1);
    }
}
```

## Bitwise operations

Bitwise operations are used to manipulate the flagged enumerations `enum`. In this section, Bitwise operations are shown by using the node constraints. The same is applicable when working with node constraints, connector constraints, or port constraints.

## Add operation

You can add or enable multiple values at a time by using the Bitwise ‘|’ (OR) operator.

The following code shows to add bridging constraints into the default diagram constraints to enable bridging functionality into the diagram.

```csharp
@using Syncfusion.Blazor.Diagram

<SfDiagramComponent Height="600px" Constraints="@DiagramConstraint">
</SfDiagramComponent>

@code{
//To adding line routing constraint with default contraints.
DiagramConstraints DiagramConstraint = DiagramConstraints.Default | DiagramConstraints.Bridging;
}
```

## Remove Operation

You can remove or disable values by using the Bitwise ‘&~’ (XOR) operator.

The following code shows to remove zoom and pan constraints from the default constraints to disable zoom and panning functionality in the diagram.

```csharp
@using Syncfusion.Blazor.Diagram

<SfDiagramComponent Height="600px" Constraints="@DiagramConstraint">
</SfDiagramComponent>

@code{
//To removing zoom and panning constraints from the default contraints
//It has disabled zoom and panning funcationality for the diagram.
DiagramConstraints DiagramConstraint = DiagramConstraints.Default &~ (DiagramConstraints.Zoom | DiagramConstraints.Pan);
}
```

## Check operation

You can check any value by using the Bitwise ‘&’ (AND) operator.

```csharp
if ((node.constraints & (NodeConstraints.Rotate)) == (NodeConstraints.Rotate));
```

In the previous example, check whether the rotate constraints are enabled in a node. When node constraints have rotated constraints, the expression returns a rotate constraint.