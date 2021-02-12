---
component: "PDF Viewer"
---

# Measurement annotation

The PDF Viewer provides the options to add measurement annotations. You can measure the page annotations with the help of measurement annotation. The supported measurement annotations in the PDF Viewer control are:

* Distance
* Perimeter
* Area
* Radius
* Volume

![CalibrateAnnotation](../../pdfviewer/images/calibrate_annotatio.png)

## Adding measurement annotations to the PDF document

The measurement annotations can be added to the PDF document using the annotation toolbar.

* Click the **Edit Annotation** button in the PDF Viewer toolbar. A toolbar appears below it.
* Click the **measurement Annotation** dropdown button. A dropdown pop-up will appear and shows the measurement annotations to be added.
* Select the measurement type to be added to the page in the dropdown pop-up. It enables the selected measurement annotation mode.
* You can measure and add the annotation over the pages of the PDF document.

In the pan mode, if the measurement annotation mode is entered, the PDF Viewer control will switch to text select mode.

![CalibrateTool](../../pdfviewer/images/calibrate_tool.png)

Refer to the following code snippet to switch to distance annotation mode.

```csharp
@using Syncfusion.Blazor.PdfViewerServer
@using Syncfusion.Blazor.Buttons
@using Syncfusion.Blazor.PdfViewer

<SfButton OnClick="OnClick">Click Here</SfButton>
<SfPdfViewerServer DocumentPath="@DocumentPath" @ref="viewer" Width="1060px" Height="500px">
</SfPdfViewerServer>

@code{
    SfPdfViewerServer viewer;

    public void OnClick(MouseEventArgs args)
    {
        viewer.SetAnnotationMode(AnnotationType.Distance);
    }
    private string DocumentPath { get; set; } = "wwwroot/Data/PDF_Succinctly.pdf";
}
```

## Editing the properties of measurement annotation

The fill color, stroke color, thickness, and opacity of the measurement annotation can be edited using the Edit Color tool, Edit Stroke Color tool, Edit Thickness tool, and Edit Opacity tool in the annotation toolbar.

### Editing fill color

The fill color of the annotation can be edited using the color palette provided in the Edit Color tool.

![CalibrateFillColor](../../pdfviewer/images/calibrate_fillcolor.png)

### Editing stroke color

The stroke color of the annotation can be edited using the color palette provided in the Edit Stroke Color tool.

![CalibrateStrokeColor](../../pdfviewer/images/calibrate_stroke.png)

### Editing thickness

The thickness of the border of the annotation can be edited using the range slider provided in the Edit thickness tool.

![CalibrateThickness](../../pdfviewer/images/calibrate_thickness.png)

### Editing opacity

The opacity of the annotation can be edited using the range slider provided in the Edit Opacity tool.

![CalibrateOpacity](../../pdfviewer/images/calibarte_opacity.png)

### Editing the line properties

The properties of the line shapes such as distance and perimeter annotations can be edited using the Line properties window. It can be opened by selecting the Properties option in the context menu that appears on right-clicking the distance and perimeter annotations.

![CalibrateProperty](../../pdfviewer/images/calibrate_lineprop.png)

## Setting default properties during control initialization

The properties of the shape annotations can be set before creating the control using distanceSettings, perimeterSettings, areaSettings, radiusSettings and volumeSettings.
Refer to the following code snippet to set the default annotation settings.

```csharp
@using Syncfusion.Blazor
@using Syncfusion.Blazor.PdfViewerServer
<SfPdfViewerServer @ref="@viewer" DocumentPath="@DocumentPath" DistanceSettings="@DistanceSettings" PerimeterSettings="@PerimeterSettings" AreaSettings="@AreaSettings" RadiusSettings="@RadiusSettings" VolumeSettings="@VolumeSettings">
</SfPdfViewerServer>
@code{
    SfPdfViewerServer viewer;
    private string DocumentPath { get; set; } = "wwwroot/Data/PDF_Succinctly.pdf";
    PdfViewerDistanceSettings DistanceSettings = new PdfViewerDistanceSettings { FillColor="blue", Opacity = 0.6 ,StrokeColor="green",LineHeadEndStyle=LineHeadStyle.Closed,LineHeadStartStyle=LineHeadStyle.Round};
    PdfViewerPerimeterSettings PerimeterSettings = new PdfViewerPerimeterSettings { FillColor="green", Opacity = 0.6 ,StrokeColor="blue"};
    PdfViewerAreaSettings AreaSettings = new PdfViewerAreaSettings { FillColor="yellow", Opacity = 0.6 ,StrokeColor="orange" };
    PdfViewerVolumeSettings VolumeSettings = new PdfViewerVolumeSettings { FillColor = "orange", Opacity = 0.6, StrokeColor = "pink" };
    PdfViewerRadiusSettings RadiusSettings = new PdfViewerRadiusSettings {FillColor="pink", Opacity = 0.6 ,StrokeColor="yellow" };
}
```

## Editing scale ratio and unit of the measurement annotation

The scale ratio and unit of measurement can be modified using the scale ratio option provided in the context menu of the PDF Viewer control.

![CalibrateScaleRatio](../../pdfviewer/images/calibrate_scaleratio.png)

The Units of measurements support for the measurement annotations in the PDF Viewer are

* Inch
* Millimeter
* Centimeter
* Point
* Pica
* Feet

![CalibrateScaleDialog](../../pdfviewer/images/calibrate_scaledialog.png)

## Setting default scale ratio settings during control initialization

The properties of scale ratio for measurement annotation can be set before creating the control using ScaleRatioSettings as shown in the following code snippet,

```csharp
@using Syncfusion.Blazor
@using Syncfusion.Blazor.PdfViewerServer
<SfPdfViewerServer @ref="@viewer" DocumentPath="@DocumentPath" MeasurementSettings="@MeasurementSettings" >
</SfPdfViewerServer>
@code{
    SfPdfViewerServer viewer;
    private string DocumentPath { get; set; } = "wwwroot/Data/PDF_Succinctly.pdf";
    PdfViewerMeasurementSettings MeasurementSettings = new PdfViewerMeasurementSettings { ScaleRatio=2,ConversionUnit=CalibrationUnit.Cm};
}
```
