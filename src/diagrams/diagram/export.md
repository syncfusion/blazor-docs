---
title: "Export"
component: "Diagram"
description: "Diagram exporting supports to export the diagram content as image/svg."
---

# Exporting

Diagram provides support to export its content as image/svg files.
The server-side method [`ExportDiagram`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Diagrams.SfDiagram~ExportDiagram.html) helps to export the diagram. The following code illustrates how to export the diagram as image.

<!-- markdownlint-disable MD033 -->

```csharp
@using Syncfusion.Blazor.Diagrams

<input type="button" value="Export" @onclick="@OnExport" />
<SfDiagram ID="diagram" Height="600px" @ref="@diagram">
</SfDiagram>

@code{
     SfDiagram diagram;
     private void OnExport()
     {
          //Sets the export option for diagram
          IExportOptions options = new IExportOptions()
          {
               //Sets the Mode for diagram export
               Mode = ExportModes.Data,
          };
          diagram.ExportDiagram(options);
     }
}
```

## Exporting options

Diagram provides support to export the desired region of the diagram to desired formats.

## File Name

[`FileName`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Diagrams.IExportOptions~FileName.html) is the name of the file to be downloaded. By default, the file name is set to **Diagram**.

## Format

[`Format`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Diagrams.IExportOptions~Format.html) is to specify the type/format of the exported file. By default, the diagram is exported as .jpg format. You can export diagram to the following formats:

* JPG
* PNG
* BMP
* SVG

```csharp
@using Syncfusion.Blazor.Diagrams

<input type="button" value="Export" @onclick="@OnExport" />
<SfDiagram ID="diagram" Height="600px" @ref="@diagram">
</SfDiagram>

@code{
     SfDiagram diagram;
     private void OnExport()
     {
          //Sets the export option for diagram
          IExportOptions options = new IExportOptions()
          {
               Mode = ExportModes.Data,
               //Sets the format for diagram export
               Format = FileFormats.SVG
          };
          diagram.ExportDiagram(options);
     }
}
```

## Margin

[`Margin`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Diagrams.IExportOptions~Margin.html) specifies the amount of space that has to be left around the diagram.

<!-- markdownlint-disable MD033 -->

```csharp
@using Syncfusion.Blazor.Diagrams

<input type="button" value="Export" @onclick="@OnExport" />
<SfDiagram ID="diagram" Height="600px" @ref="@diagram">
</SfDiagram>

@code{
     SfDiagram diagram;
     private void OnExport()
     {
          //Sets the export option for diagram
          IExportOptions options = new IExportOptions()
          {
               Mode = ExportModes.Data,
               FileName = "diagram",
               Stretch = Stretch.None,
               //Sets the margin for diagram export
               Margin = new DiagramMargin { Left = 10, Right = 10, Bottom = 10, Top = 10 },
               Format = FileFormats.SVG
          };
          diagram.ExportDiagram(options);
     }
}

```

## Mode

[`Mode`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Diagrams.IExportOptions~Mode.html) specifies whether the diagram is to be exported as files or as data (ImageURL/SVG). The exporting options are as follows:

* Data: Exports and downloads the diagram as image.
* Download: Exports the diagram as data of formats ImageURL/SVG.

For more information about the exporting modes, refer to Exporting Modes.

The following code example illustrates how to export the diagram as raw data.

```csharp
@using Syncfusion.Blazor.Diagrams

<input type="button" value="Export" @onclick="@OnExport" />
<SfDiagram ID="diagram" Height="600px" @ref="@diagram">
</SfDiagram>

@code{
     SfDiagram diagram;
     private void OnExport()
     {
          //Sets the export option for diagram
          IExportOptions options = new IExportOptions()
          {
               //Sets the mode for diagram export
               Mode = ExportModes.Data,
               FileName = "diagram",
               Stretch = Stretch.None,
               Margin = new Syncfusion.Blazor.Diagrams.MarginModel() { Left = 10, Right = 10, Bottom = 10, Top = 10 },
               Format = FileFormats.SVG
          };
          diagram.ExportDiagram(options);
     }
}
```

## Region

You can export any particular [`Region`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Diagrams.IExportOptions~Region.html) of the diagram and the region is categorized as follows.

* Region that fits all nodes and connectors that are added to model.
* Region that fits all pages (single or multiple pages based on page settings).

For more information about region, refer to Regions.

The following code example illustrates how to export the region occupied by the diagram elements.

```csharp
@using Syncfusion.Blazor.Diagrams

<input type="button" value="Export" @onclick="@OnExport" />

<SfDiagram ID="diagram" Height="600px" @ref="@diagram">
</SfDiagram>

@code{
     SfDiagram diagram;
     private void OnExport()
     {
          //Sets the export option for diagram
          IExportOptions options = new IExportOptions()
          {
               Mode = ExportModes.Data,
               FileName = "format",
               Stretch = Stretch.None,
               //Sets the region for diagram export
               Region = DiagramRegions.Content,
               Margin = new Syncfusion.Blazor.Diagrams.MarginModel() { Left = 10, Right = 10, Bottom = 10, Top = 10 },
               Format = FileFormats.SVG
          };
          diagram.ExportDiagram(options);
     }
}
```

## Custom bounds

Diagram provides support to export any specific region of the diagram by using [`Bounds`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Diagrams.IExportOptions~Region.html).

The following code example illustrates how to export the region occupied by the diagram elements.

```csharp
@using Syncfusion.Blazor.Diagrams

<input type="button" value="Export" @onclick="@OnExport" />
<SfDiagram ID="diagram" Height="600px" @ref="@diagram">
</SfDiagram>

@code{
     SfDiagram diagram;
     //Define bounds class for export the diagram
     public class exportBounds
     {
          public double x { get; set; }
          public double y { get; set; }
          public double width { get; set; }
          public double height { get; set; }
     }
     private void OnExport()
     {
          //Sets the export option for diagram
          IExportOptions options = new IExportOptions()
          {
               Mode = ExportModes.Download,
               FileName = "format",
               PageHeight = 400,
               PageWidth = 400,
               Stretch = Stretch.None,
               Region = DiagramRegions.CustomBounds,
               //Sets the custom bound for diagram export
               Bounds = new exportBounds() { x = 10, y = 10, width = 100, height = 100 },
               Margin = new Syncfusion.Blazor.Diagrams.MarginModel() { Left = 10, Right = 10, Bottom = 10, Top = 10 },
               Format = FileFormats.SVG
          };
          diagram.ExportDiagram(options);
     }
}
```

## Export diagram with stretch option

Diagram provides support to export the diagram as image for [`Stretch`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Diagrams.IExportOptions~Stretch.html) option. The exported images will be clearer but larger in file size.

The following code example illustrates how to export the region occupied by the diagram elements.

```csharp
@using Syncfusion.Blazor.Diagrams

<input type="button" value="Export" @onclick="@OnExport" />
<SfDiagram ID="diagram" Height="600px" @ref="@diagram">
</SfDiagram>

@code{
     SfDiagram diagram;
     private void OnExport()
     {
          //Sets the export option for diagram
          IExportOptions options = new IExportOptions()
          {
               Mode = ExportModes.Data,
               FileName = "region",
               Stretch = Stretch.Stretch,
               Region = DiagramRegions.Content,
               Margin = new Syncfusion.Blazor.Diagrams.MarginModel() { Left = 10, Right = 10, Bottom = 10, Top = 10 },
               Format = FileFormats.SVG
          };
          diagram.ExportDiagram(options);
     }
}
```

## Print

The server-side method [`Print`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Diagrams.SfDiagram~Print.html) helps to print the diagram as image.

| Name | Type | Description|
|-------- | -------- | -------- |
| region | enum | Sets the region of the diagram to be printed. |
| bounds | object | Prints any custom region of diagram. |
| stretch| enum | Resizes the diagram content to fill its allocated space and printed.|
| multiplePage | boolean | Prints the diagram into multiple pages. |
| pageWidth | number | Sets the page width of the diagram while printing the diagram into multiple pages. |
| pageHeight| number | Sets the page height of the diagram while printing the diagram into multiple pages.|
| pageOrientation | enum | Sets the orientation of the page. |

The following code example illustrates how to export the region occupied by the diagram elements.

```csharp
@using Syncfusion.Blazor.Diagrams

<input type="button" value="Print" @onclick="@OnPrint" />
<SfDiagram ID="diagram" Height="600px" @ref="@diagram">
</SfDiagram>

@code{
     SfDiagram diagram;
     private void OnPrint()
     {
          //Sets the print option for diagram
          IPrintOptions options = new IPrintOptions()
          {
               MultiplePage = true,
               PageHeight = 400,
               PageWidth = 400,
               Region = DiagramRegions.PageSettings,
          };
          diagram.Print(options);
     }
}
```