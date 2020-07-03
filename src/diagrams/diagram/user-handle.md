---
title: "UserHandle"
component: "Diagram"
description: "Learn how to add or remove userhandles, userhandles customization, and its event handle in the diagram blazor component"
---

# User Handles

User handles are customizable handles that can be used to perform custom actions and default clipboard actions.

## Initialization an userhandle

The user handle can enables for the selected nodes/connectors by setting a [`SelectorConstraints`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Diagrams.SelectorConstraints.html) as `UserHandle` and then use the [`DiagramUserHandle`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Diagrams.DiagramUserHandle_members.html) class to create an object for the user handles. The following code example used to enable and create an user handles for the diagram nodes/connectors.

```csharp
@using Syncfusion.Blazor.Diagrams
@using System.Collections.ObjectModel

<SfDiagram Height="600px"
           Nodes="@NodeCollection"
           SelectedItems="@SelectedModel">
</SfDiagram>

@code{
    // Defines diagram's nodes collection
    public ObservableCollection<DiagramNode> NodeCollection { get; set; }
    // Defines diagram's SelectedItems
    public Syncfusion.Blazor.Diagrams.DiagramSelectedItems SelectedModel { get; set; }
    ObservableCollection<DiagramUserHandle> UserHandles { get; set; }
    protected override void OnInitialized()
    {
        //Creating the userhandle for cloning the objects
        DiagramUserHandle cloneHandle = new DiagramUserHandle()
        {
            //Name of the user handle
            Name = "clone",
            //Set pathdata for userhandle
            PathData = "M60.3,18H27.5c-3,0-5.5,2.4-5.5,5.5v38.2h5.5V23.5h32.7V18z M68.5,28.9h-30c-3,0-5.5,2.4-5.5,5.5v38.2c0,3,2.4,5.5,5.5,5.5h30c3,0,5.5-2.4,5.5-5.5V34.4C73.9,31.4,71.5,28.9,68.5,28.9z M68.5,72.5h-30V34.4h30V72.5z",
            //Set visibility for the user handle
            Visible = true,
            //Set the position for the user handle
            Offset = 0,
            //Set side based on the given offset
            Side = Side.Bottom,
            //set margin for the user handle
            Margin = new DiagramUserHandleMargin() { Top = 0, Bottom = 0, Left = 0, Right = 0 }
        };
        //Add user handle to the collection...
        UserHandles = new ObservableCollection<DiagramUserHandle>()
        {
            cloneHandle
        };
        SelectedModel = new Syncfusion.Blazor.Diagrams.DiagramSelectedItems()
        {
            //Enable userhandle for selected items...
            Constraints = SelectorConstraints.UserHandle,
            UserHandles = this.UserHandles
        };

        NodeCollection = new ObservableCollection<DiagramNode>();

        DiagramNode diagramNode = new DiagramNode()
        {
            Id = "node1",
            OffsetX = 100,
            OffsetY = 100,
            Width = 100,
            Height = 100,
            Style = new NodeShapeStyle() { Fill = "#659be5", StrokeColor = "none" },
            Annotations = new ObservableCollection<DiagramNodeAnnotation>() { new DiagramNodeAnnotation() { Content = "Node" } }
        };

        NodeCollection.Add(diagramNode);
    }
}
```

![User handle for node](images/userhandle1.png)

## Customization

If set `false` to the [`DisableConnectors`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Diagrams.DiagramUserHandle~DisableConnectors.html) property in userhandle, the userhandle prevents to rendering for the connectors. The following code example is used to show userhandle for the nodes alone.

```csharp
@using Syncfusion.Blazor.Diagrams
@using System.Collections.ObjectModel

<SfDiagram @ref="@Diagram" Height="600px"
           Nodes="@NodeCollection"
           Connectors="@ConnectorCollection"
           SelectedItems="@SelectedModel">
</SfDiagram>

@code {
    // Reference to diagram
    SfDiagram Diagram;
    // Defines diagram's nodes collection
    public ObservableCollection<DiagramNode> NodeCollection { get; set; }
    // Defines diagram's connector collection
    public ObservableCollection<DiagramConnector> ConnectorCollection { get; set; }
    // Defines diagram's SelectedItems
    public Syncfusion.Blazor.Diagrams.DiagramSelectedItems SelectedModel { get; set; }
    ObservableCollection<DiagramUserHandle> UserHandles { get; set; }
    protected override void OnInitialized()
    {
        //Creating the userhandle for cloning the objects
        DiagramUserHandle cloneHandle = new DiagramUserHandle()
        {
            //Name of the user handle
            Name = "clone",
            //Set pathdata for userhandle
            PathData = "M60.3,18H27.5c-3,0-5.5,2.4-5.5,5.5v38.2h5.5V23.5h32.7V18z M68.5,28.9h-30c-3,0-5.5,2.4-5.5,5.5v38.2c0,3,2.4,5.5,5.5,5.5h30c3,0,5.5-2.4,5.5-5.5V34.4C73.9,31.4,71.5,28.9,68.5,28.9z M68.5,72.5h-30V34.4h30V72.5z",
            //Set visibility for the user handle
            Visible = true,
            //Set the position for the user handle
            Offset = 0,
            //Set side based on the given offset
            Side = Side.Bottom,
            //Disable to render this userhandle for connectors
            DisableConnectors = true,
            //set margin for the user handle
            Margin = new DiagramUserHandleMargin() { Top = 0, Bottom = 0, Left = 0, Right = 0 }
        };

        //Add user handle to the collection...
        UserHandles = new ObservableCollection<DiagramUserHandle>()
        {
            cloneHandle
        };
        SelectedModel = new Syncfusion.Blazor.Diagrams.DiagramSelectedItems()
        {
            //Enable userhandle for selected items...
            Constraints = SelectorConstraints.UserHandle,
            UserHandles = this.UserHandles
        };

        NodeCollection = new ObservableCollection<DiagramNode>();

        DiagramNode diagramNode = new DiagramNode()
        {
            Id = "node1",
            OffsetX = 100,
            OffsetY = 100,
            Width = 100,
            Height = 100,
            Style = new NodeShapeStyle() { Fill = "#659be5", StrokeColor = "none" },
            Annotations = new ObservableCollection<DiagramNodeAnnotation>() { new DiagramNodeAnnotation() { Content = "Node" } }
        };

        NodeCollection.Add(diagramNode);

        ConnectorCollection = new ObservableCollection<DiagramConnector>();

        DiagramConnector diagramConnector = new DiagramConnector()
        {
            SourcePoint = new ConnectorSourcePoint() { X= 300, Y=100},
            TargetPoint = new ConnectorTargetPoint() { X= 300, Y=300}
        };

        ConnectorCollection.Add(diagramConnector);
    }
}
```

>**Note**: Also you can disable the [`DisableNodes`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Diagrams.DiagramUserHandle~DisableNodes.html) property in userhandle, the userhandle prevent to rendering for the nodes.

### Position

The [`Offset`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Diagrams.DiagramUserHandle~Offset.html) property of userhandle is used to align the userhandles based on fractions. 0 represents Top-Left corner, 1 represents Bottom-Right corner, and 0.5 represents half of Width or Height.

The [`Side`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Diagrams.DiagramUserHandle~Side.html) property is used to set how the userhandle is aligned based on the given [`Offset`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Diagrams.DiagramUserHandle~Offset.html).

The following table shows all the possible alignments visually shows the userhandle positions.

| Offset | Side | Output |
| -------- | -------- | -------- |
|0|Left|![User handle for node](images/userhandle2.png)|
|0|Right|![User handle for node](images/userhandle3.png)|
|0|Top|![User handle for node](images/userhandle4.png)|
|0|Bottom|![User handle for node](images/userhandle5.png)|
|1|Left|![User handle for node](images/userhandle6.png)|
|1|Right|![User handle for node](images/userhandle7.png)|
|1|Top|![User handle for node](images/userhandle8.png)|
|1|Bottom|![User handle for node](images/userhandle9.png)|

### Size

Diagram allows you set size for userhandles by using the [`Size`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Diagrams.DiagramUserHandle~Size.html) property. The default value of the [`Size`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Diagrams.DiagramUserHandle~Offset.html) property is 25.

### Style

* You can change the style of the userhandles with the specific properties of PathColor, BorderColor, BackgroundColor and BorderWidth. The following code explains how to customize the appearance of the userhandles.

* The userhandle's [`PathColor`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Diagrams.DiagramUserHandle~PathColor.html) property used to change the color of the given [`PathData`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Diagrams.DiagramUserHandle~PathData.html) of the userhandle.

* The userhandle [`BorderColor`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Diagrams.DiagramUserHandle~BorderColor.html), [`BackgroundColor`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Diagrams.DiagramUserHandle~BackgroundColor.html) properties are used to define the background color and border color of the userhandle and the [`BorderWidth`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Diagrams.DiagramUserHandle~BorderWidth.html) property is used to define the border width of the userhandles.

*The [`Visible`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Diagrams.DiagramUserHandle~Visible.html) property of the userhandle enables or disables the visibility of userhandle.

The following code explains how to customize the appearance of the userhandle.

```csharp
//Creating the userhandle for cloning the objects
DiagramUserHandle cloneHandle = new DiagramUserHandle()
{
    //Name of the user handle
    Name = "clone",
    //Set pathdata for userhandle
    PathData = "M60.3,18H27.5c-3,0-5.5,2.4-5.5,5.5v38.2h5.5V23.5h32.7V18z M68.5,28.9h-30c-3,0-5.5,2.4-5.5,5.5v38.2c0,3,2.4,5.5,5.5,5.5h30c3,0,5.5-2.4,5.5-5.5V34.4C73.9,31.4,71.5,28.9,68.5,28.9z M68.5,72.5h-30V34.4h30V72.5z",
    //Set visibility for the user handle
    Visible = true,
    //Set the position for the user handle
    Offset = 1,
    //Set side based on the given offset
    Side = Side.Bottom,
    //Disable to render this userhandle for connectors
    DisableConnectors = true,
    //set margin for the user handle
    Margin = new DiagramUserHandleMargin() { Top = 0, Bottom = 0, Left = 0, Right = 0 },
    //Set size of the user handle
    Size = 50,
    //Set pathcolor for given pathdata
    PathColor = "yellow",
    //Set Border color of the user handle
    BorderColor = "red",
    //Set Background Color of the user handle
    BackgroundColor = "green",
    //Set Border Width Color of the user handle
    BorderWidth = 3,
};
```

![Customized appearance of Userhandle](images/userhandle10.png)

## Events

The Diagram control provides following list of events for the userhandle.

| Event Name | Event Type | Description |
| -------- | -------- | -------- |
| [`OnUserHandleMouseDown`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Diagrams.DiagramEvents~OnUserHandleMouseDown.html) | [`UserHandleEventsArgs`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Diagrams.UserHandleEventsArgs_members.html) | Triggered when the mouse pointer is over the userhandle and mouse button is down. |
| [`OnUserHandleMouseUp`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Diagrams.DiagramEvents~OnUserHandleMouseUp.html) | [`UserHandleEventsArgs`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Diagrams.UserHandleEventsArgs_members.html) | Triggered when the mouse pointer is over the userhandle and mouse button is released. |
| [`OnUserHandleMouseEnter`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Diagrams.DiagramEvents~OnUserHandleMouseEnter.html) | [`UserHandleEventsArgs`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Diagrams.UserHandleEventsArgs_members.html) | Triggered when mouse enter into the userhandle. |
| [`OnUserHandleMouseLeave`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Diagrams.DiagramEvents~OnUserHandleMouseLeave.html) | [`UserHandleEventsArgs`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Diagrams.UserHandleEventsArgs_members.html) | Triggered when mouse leaves the userhandle. |

The following code explains how to use the `OnUserHandleMouseUp` event for an userhandle.

```csharp
@using Syncfusion.Blazor.Diagrams
@using System.Collections.ObjectModel

<SfDiagram @ref="@Diagram" Height="600px"
           Nodes="@NodeCollection"
           Connectors="@ConnectorCollection"
           SelectedItems="@SelectedModel">
    <DiagramEvents OnUserHandleMouseUp="@OnUserHandleMouseUp"></DiagramEvents>
</SfDiagram>

@code {
    // Reference to diagram
    SfDiagram Diagram;

    // Defines diagram's nodes collection
    public ObservableCollection<DiagramNode> NodeCollection { get; set; }
    // Defines diagram's connector collection
    public ObservableCollection<DiagramConnector> ConnectorCollection { get; set; }

    // Defines diagram's SelectedItems
    public Syncfusion.Blazor.Diagrams.DiagramSelectedItems SelectedModel { get; set; }

    ObservableCollection<DiagramUserHandle> UserHandles { get; set; }

    protected override void OnInitialized()
    {
        //Creating the userhandle for cloning the objects
        DiagramUserHandle cloneHandle = new DiagramUserHandle()
        {
            //Name of the user handle
            Name = "clone",
            //Set pathdata for userhandle
            PathData = "M60.3,18H27.5c-3,0-5.5,2.4-5.5,5.5v38.2h5.5V23.5h32.7V18z M68.5,28.9h-30c-3,0-5.5,2.4-5.5,5.5v38.2c0,3,2.4,5.5,5.5,5.5h30c3,0,5.5-2.4,5.5-5.5V34.4C73.9,31.4,71.5,28.9,68.5,28.9z M68.5,72.5h-30V34.4h30V72.5z",
            //Set visibility for the user handle
            Visible = true,
            //Set the position for the user handle
            Offset = 0,
            //Set side based on the given offset
            Side = Side.Bottom,
            //Disable to render this userhandle for connectors
            DisableConnectors = true,
            //set margin for the user handle
            Margin = new DiagramUserHandleMargin() { Top = 0, Bottom = 0, Left = 0, Right = 0 }
        };

        //Add user handle to the collection...
        UserHandles = new ObservableCollection<DiagramUserHandle>()
        {
            cloneHandle
        };
        SelectedModel = new Syncfusion.Blazor.Diagrams.DiagramSelectedItems()
        {
            //Enable userhandle for selected items...
            Constraints = SelectorConstraints.UserHandle,
            UserHandles = this.UserHandles
        };

        NodeCollection = new ObservableCollection<DiagramNode>();

        DiagramNode diagramNode = new DiagramNode()
        {
            Id = "node1",
            OffsetX = 100,
            OffsetY = 100,
            Width = 100,
            Height = 100,
            Style = new NodeShapeStyle() { Fill = "#659be5", StrokeColor = "none" },
            Annotations = new ObservableCollection<DiagramNodeAnnotation>() { new DiagramNodeAnnotation() { Content = "Node" } }
        };

        NodeCollection.Add(diagramNode);

        ConnectorCollection = new ObservableCollection<DiagramConnector>();

        DiagramConnector diagramConnector = new DiagramConnector()
        {
            SourcePoint = new ConnectorSourcePoint() { X= 300, Y=100},
            TargetPoint = new ConnectorTargetPoint() { X=300,Y=300}
        };

        ConnectorCollection.Add(diagramConnector);
    }
    /// <summary>
    /// mouse up event for the userhandles...
    /// </summary>
    public async Task OnUserHandleMouseUp(UserHandleEventsArgs args)
    {
        if (Diagram.SelectedItems.Nodes.Count > 0)
        {
            await Diagram.Copy();
            await Diagram.Paste();
        }
    }
}
```
