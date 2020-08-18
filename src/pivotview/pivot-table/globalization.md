---
title: "Globalization"
component: "Pivot Table"
description: "Learn about how to globalize the pivot table and how to localize the culture related content."
---

# Globalization

Add **UseRequestLocalization** middle-ware in Configure method in **Startup.cs** file to get browser Culture Info.

Refer the following code to add configuration in Startup.cs file

```csharp
using Microsoft.AspNetCore.Builder;
using Microsoft.AspNetCore.Localization;

namespace BlazorApplication
{
    public class Startup
    {
        ....
        ....

        public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
        {
            app.UseRequestLocalization();
            ....
            ....
        }
    }
}
```

## Localization

Localization library allows you to localize default text content of the pivot table. The pivot table component has static text of some features (like drop and drop region, pivot field list, etc...) that can be changed to other cultures (Arabic, Deutsch, French, etc...).The static local texts in the pivot table component can be changed to other culture by referring the Resource file. You can refer more details about localization [here](https://blazor.syncfusion.com/documentation/common/localization/).

### Blazor Server Side

In the following example, we have demonstrate how to enable **Localization** for pivot table in server side Blazor sample. Here, we have used Resource file to translate the static text of the pivot table.

The Resource file is an XML file which contains the strings(key and value pairs) that you want to translate into different language. You can also refer [`Localization`](https://docs.microsoft.com/en-us/aspnet/core/fundamentals/localization?view=aspnetcore-3.0) link to know more about how to configure and use localization in the ASP.NET Core application framework.

* Open the **Startup.cs** file and add the below configuration in the **ConfigureServices** function as follows.

```csharp
using Syncfusion.Blazor;
using System.Globalization;
using Microsoft.AspNetCore.Localization;

namespace BlazorApplication
{
    public class Startup
    {
        ....
        ....
        public void ConfigureServices(IServiceCollection services)
        {
            ....
            ....
            services.AddSyncfusionBlazor();
            services.AddLocalization(options => options.ResourcesPath = "Resources");
            services.Configure<RequestLocalizationOptions>(options =>
            {
                // define the list of cultures your app will support
                var supportedCultures = new List<CultureInfo>()
                {
                    new CultureInfo("de")
                };
                // set the default culture
                options.DefaultRequestCulture = new RequestCulture("de");
                options.SupportedCultures = supportedCultures;
                options.SupportedUICultures = supportedCultures;
                options.RequestCultureProviders = new List<IRequestCultureProvider>() {
                 new QueryStringRequestCultureProvider() // Here, You can also use other localization provider
                };
            });
            services.AddSingleton(typeof(ISyncfusionStringLocalizer), typeof(SampleLocalizer));
        }
    }
}
```

> Add [`UseRequestLocalization()`](https://docs.microsoft.com/en-us/aspnet/core/fundamentals/localization?view=aspnetcore-3.0#localization-middleware) middle-ware in Configure method in **Startup.cs** file to get browser Culture Information.

* Then, write a **class** by inheriting **ISyncfusionStringLocalizer** interface and override the Manager property to get the resource file details from the application end.

```csharp
using Syncfusion.Blazor;

namespace BlazorApplication
{
     public class SampleLocalizer : ISyncfusionStringLocalizer
    {

        public string Get(string key)
        {
            return this.Manager.GetString(key);
        }

        public System.Resources.ResourceManager Manager
        {
            get
            {
                return BlazorApplication.Resources.SyncfusionBlazorLocale.ResourceManager;
            }
        }
    }
}
```

* Add **.resx** file to [`Resource`](https://docs.microsoft.com/en-us/aspnet/core/fundamentals/localization?view=aspnetcore-3.0#resource-files) folder and enter the key value (Locale Keywords) in the **Name** column and the translated string in the **Value** column as follows.

```csharp
<Component_Name>_<Feature_Name>_<Locale_Key>
```

The following are the list of properties and its values used in the pivot table.

Name |Value (in Deutsch culture)
----|-----
PivotView_AddCondition | Bedingung hinzufügen
PivotView_AddToColumn | Zur Spalte hinzufügen
PivotView_AddToFilter | Zum Filter hinzufügen
PivotView_AddToRow | Zur Zeile hinzufügen
PivotView_AddToValue | Zum Wert hinzufügen
PivotView_After | Nach
PivotView_AfterOrEqualTo | Nach oder gleich
PivotView_Aggregate | Aggregat
PivotView_Alert | Warnen
PivotView_All | Alle
PivotView_All Fields | Alle Felder
PivotView_AllValues | Alle Werte
PivotView_And | und
PivotView_Apply | ANWENDEN
PivotView_Area | Bereich
PivotView_Ascending | Aufsteigend
PivotView_Avg | durchschnittlich
PivotView_Bar | Bar
PivotView_BaseField | Basisfeld
PivotView_BaseItem | Basisgegenstand
PivotView_Before | Vor
PivotView_BeforeOrEqualTo | Vorher oder gleich
PivotView_BeginWith | Beginnt mit
PivotView_Between | Zwischen
PivotView_Blank | (Leer)
PivotView_By | durch
PivotView_CalculatedField | Berechnetes Feld
PivotView_CalculatedField_ConfirmMessage | In diesem Namen ist bereits ein Berechnungsfeld vorhanden. Möchten Sie es ersetzen?
PivotView_CalculatedField_DragDropMessage | Ziehen Sie Felder in die Formel und legen Sie sie dort ab
PivotView_CalculatedField_DragMessage | Ziehen Sie das Feld in die Formel
PivotView_CalculatedField_DropMessage | Das berechnete Feld kann nur in der Werteachse in einem anderen Bereich platziert werden.
PivotView_CalculatedField_ExampleWatermark | Beispiel: ('Sum(Order_Count)' + 'Sum(In_Stock)') * 250
PivotView_CalculatedField_ExistMessage | In diesem Namen ist bereits ein Feld vorhanden. Bitte geben Sie einen anderen Namen ein.
PivotView_CalculatedField_MobileWatermark | Fügen Sie hier Felder hinzu und bearbeiten Sie die Formel.
PivotView_CalculatedField_NameWatermark | Geben Sie den Feldnamen ein
PivotView_CalculatedField_OLAPExampleWatermark | Beispiel: [Measures].[Order Quantity] + ([Measures].[Order Quantity] * 0.10)
PivotView_CalculatedField_Tooltip | Ziehen Sie Felder per Drag &amp; Drop, um einen Ausdruck zu erstellen. Und wenn Sie die vorhandenen die berechneten Felder bearbeiten möchten! Dann können Sie dies erreichen, indem Sie einfach das Feld unter 'Berechnete Mitglieder' auswählen.
PivotView_Cancel | Stornieren
PivotView_Chart | Diagramm
PivotView_Clear | Klar
PivotView_ClearFilter | Klar
PivotView_Close | Schließen
PivotView_Collapse | Zusammenbruch
PivotView_Column | Säule
PivotView_ColumnAxisWatermark | Spalte hier ablegen
PivotView_Columns | Säulen
PivotView_ConditionalFormating | Bedingte Formatierung
PivotView_ConditionalFormatting | Bedingte formatierung
PivotView_Contains | Enthält
PivotView_Copy | Kopieren
PivotView_Count | Anzahl
PivotView_CreateCalculatedField | Berechnetes Feld erstellen
PivotView_CSV | CSV
PivotView_Currency | Währung
PivotView_CurrencySymbol | Währungszeichen
PivotView_Custom | Benutzerdefiniert
PivotView_CustomFormat | Benutzerdefiniertes Format
PivotView_CustomFormatMessage | Geben Sie eine benutzerdefinierte Formatzeichenfolge ein
PivotView_Date | Datum
PivotView_DateTextMessage | Zeigen Sie die Elemente an, für die das Datum gilt
PivotView_Days | Tage
PivotView_DecimalPlaces | Nachkommastellen
PivotView_Delete | Löschen
PivotView_DeleteReport | Löschen Sie einen aktuellen Bericht
PivotView_Descending | Absteigend
PivotView_Details | Einzelheiten
PivotView_DifferenceFrom | Unterschied von
PivotView_Dimension | Abmessungen
PivotView_DistinctCount | Deutliche Anzahl
PivotView_DoesNotBeginWith | Beginnt nicht mit
PivotView_DoesNotContains | Beinhaltet nicht
PivotView_DoesNotEndsWith | Endet nicht mit
PivotView_DoesNotEquals | Ist nicht gleich
PivotView_DoNotShowGrandTotals | Keine Gesamtsummen anzeigen
PivotView_DoNotShowSubtotals | Zwischensummen nicht anzeigen
PivotView_Drag | Ziehen
PivotView_DrillThrough | Durchbohren
PivotView_DrillThroughErrorMessage | Die Rohelemente berechneter Felder können nicht angezeigt werden.
PivotView_Edit | Bearbeiten
PivotView_EmptyRecordsMessage | Keine Datensätze zum Anzeigen
PivotView_EmptyReportMessage | Keine Berichte gefunden !!
PivotView_EndAt | Endet bei
PivotView_EndsWith | Endet mit
PivotView_EnterDate | Datum eingeben
PivotView_EnterReportNameMessage | Geben Sie einen Berichtsnamen ein
PivotView_EnterValue | Wert eingeben
PivotView_Equals | Gleich
PivotView_Error | Error
PivotView_Example | z.B:
PivotView_Excel | Excel
PivotView_Expand | Erweitern
PivotView_Export | Export
PivotView_Expression | Ausdruck
PivotView_False | Falsch
PivotView_FieldCaption | Feldbeschriftung
PivotView_FieldCaptionMessage | Feldbeschriftung
PivotView_FieldDropErrorMessage | Das Feld, das Sie verschieben, kann nicht in diesem Bereich des Berichts platziert werden
PivotView_FieldName | Feldname
PivotView_FieldNameMessage | Feldname :
PivotView_FieldType | Feldtyp
PivotView_Filter | Filter
PivotView_FilterAxisWatermark | Filter hier ablegen
PivotView_Filtered | Gefiltert
PivotView_Filters | Filter
PivotView_Format | Format
PivotView_FormatString | Zeichenfolge formatieren
PivotView_FormatType | Formattyp
PivotView_Formula | Formel
PivotView_GrandTotal | Gesamtsumme
PivotView_GrandTotals | Gesamtsummen
PivotView_GreaterThan | Größer als
PivotView_GreaterThanOrEqualTo | Größer als oder gleich wie
PivotView_Group | Gruppe
PivotView_GroupCaptionMessage | Geben Sie die Beschriftung ein, die in der Kopfzeile angezeigt werden soll
PivotView_GroupFieldCaption | Feldbeschriftung
PivotView_GroupFieldCaptionMessage | Geben Sie die Beschriftung für das Gruppenfeld ein
PivotView_Grouping | Gruppierung
PivotView_GroupName | Gruppenname
PivotView_Hours | Std
PivotView_Index | Index
PivotView_IntervalBy | Intervall von
PivotView_InvalidFormat | Ungültiges Format.
PivotView_InvalidFormula | Ungültige Formel.
PivotView_InvalidGroupSelectionMessage | Diese Auswahl kann nicht gruppiert werden.
PivotView_JPEG | JPEG
PivotView_Label | Etikette
PivotView_LabelTextMessage | Zeigen Sie die Elemente an, für die das Etikett
PivotView_Left | Links
PivotView_LessThan | Weniger als
PivotView_LessThanOrEqualTo | Gleich oder kleiner als
PivotView_Line | Linie
PivotView_LoadReport | Belastung
PivotView_ManageRecords | Datensätze verwalten
PivotView_Max | Max
PivotView_MdxQuery | MDX-Abfrage
PivotView_Measure | Messen
PivotView_Member | Mitglied
PivotView_MemberLimitMessage | weitere Artikel. Suche, um weiter zu verfeinern.
PivotView_Min | Min
PivotView_Minutes | Protokoll
PivotView_Months | Monate
PivotView_MoreOption | Mehr...
PivotView_MultipleItems | Mehrere Elemente
PivotView_NewReport | Erstellen Sie einen neuen Bericht
PivotView_NewReportConfirmMessage | Möchten Sie Änderungen speichern, um sie zu melden?
PivotView_NoFormatMessage | Kein Format gefunden !!!
PivotView_NoInputMessage | Geben Sie einen Wert ein
PivotView_NoMatchesMessage | Keine Treffer
PivotView_NotBetween | Nicht zwischen
PivotView_NotEquals | Nicht gleich
PivotView_NoValue | Kein Wert
PivotView_Null | Null
PivotView_Number | Nummer
PivotView_NumberFormatting | Zahlenformatierung
PivotView_Of | von
PivotView_OK | OK
PivotView_OutOfRange | Außer Reichweite
PivotView_ParentHierarchy | Übergeordnete Hierarchie
PivotView_PDF | PDF
PivotView_Percent | Prozent
PivotView_Percentage | Prozentsatz
PivotView_PercentageOfColumnTotal | % der Spalte insgesamt
PivotView_PercentageOfDifferenceFrom | % des Unterschieds von
PivotView_PercentageOfGrandTotal | % der Gesamtsumme
PivotView_PercentageOfParentColumnTotal | % der übergeordneten Spalte insgesamt
PivotView_PercentageOfParentRowTotal | % der Gesamtzahl der übergeordneten Zeilen
PivotView_PercentageOfParentTotal | % der Elternsumme
PivotView_PercentageOfRowTotal | % der Zeilensumme
PivotView_PNG | PNG
PivotView_Polar | Polar
PivotView_PopulationStDev | Bevölkerungsstandardabweichung
PivotView_PopulationVar | Populationsvarianz
PivotView_Product | Produkt
PivotView_Quarter | Qtr
PivotView_Quarters | Viertel
PivotView_QuarterYear | Vierteljahr
PivotView_Remove | Entfernen
PivotView_RemoveReportConfirmMessage | Möchten Sie diesen Bericht wirklich löschen?
PivotView_RenameReport | Benennen Sie einen aktuellen Bericht um
PivotView_ReportList | Berichtsliste
PivotView_ReportNameMessage | Berichtsname:
PivotView_Right | Recht
PivotView_Row | Reihe
PivotView_RowAxisWatermark | Hier eine Zeile ablegen
PivotView_Rows | Reihen
PivotView_RunningTotals | Laufende Summen
PivotView_SampleReport | Beispielbericht
PivotView_SampleStDev | Standardabweichung der Probe
PivotView_SampleVar | Stichprobenvarianz
PivotView_SaveAsReport | Als aktuellen Bericht speichern
PivotView_SaveReport | Speichern Sie einen Bericht
PivotView_Scatter | Streuen
PivotView_Search | Suche
PivotView_Seconds | Sekunden
PivotView_SelectedItems | Ausgewählte Artikel
PivotView_SelectGroups | Wählen Sie Gruppen aus
PivotView_ShowColumnGrandTotalsOnly | Nur Gesamtsummenspalten anzeigen
PivotView_ShowColumnSubtotalsOnly | Nur Zwischensummenspalten anzeigen
PivotView_ShowFieldList | Feldliste anzeigen
PivotView_ShowGrandTotals | Gesamtsummen anzeigen
PivotView_ShowRowGrandTotalsOnly | Nur Gesamtsummenzeilen anzeigen
PivotView_ShowRowSubtotalsOnly | Nur Zwischensummenzeilen anzeigen
PivotView_ShowSubtotals | Zwischensummen anzeigen
PivotView_ShowTable | Tabelle anzeigen
PivotView_Sort | Sortieren
PivotView_Standard | Standard
PivotView_StartAt | Beginnt um
PivotView_Subtotals | Zwischensummen
PivotView_Sum | Summe
PivotView_Summaries | Werte zusammenfassen mit
PivotView_SummarizeValuesBy | Werte zusammenfassen mit
PivotView_SVG | SVG
PivotView_SymbolPosition | Symbolposition
PivotView_Total | Gesamt
PivotView_True | Wahr
PivotView_Undefined | nicht definiert
PivotView_Ungroup | Gruppierung aufheben
PivotView_ValidReportNameMessage | Bitte geben Sie einen gültigen Datensatznamen ein !!!
PivotView_Value | Wert
PivotView_ValueAxisWatermark | Wert hier ablegen
PivotView_ValueFieldSettings | Wertefeldeinstellungen
PivotView_Values | Werte
PivotView_ValueTextMessage | Zeigen Sie die Elemente an, für die
PivotView_Warning | Warnung
PivotView_Years | Jahre
PivotView_MultipleAxes | Mehrere Achsen
PivotView_ChartTypeSettings | Configuración de tipo de gráfico
PivotView_ChartType | Tipo de carta
PivotView_Yes | si
PivotView_No | No
PivotView_NumberFormatMenu | Formato de número ...
PivotView_ConditionalFormatingMenu | formato condicional ...
PivotView_CalculatedField_RemoveMessage | Está seguro de que desea eliminar este campo calculado?
PivotView_StackedArea | Área apilada
PivotView_StackedColumn | Columna apilada
PivotView_StackedBar | Barra apilada
PivotView_StepLine | Línea de paso
PivotView_StepArea | Área de paso
PivotView_SplineArea | Área de spline
PivotView_Spline | Ranura
PivotView_StackedColumn100 | Columna 100% apilada
PivotView_StackedBar100 | Barra 100% apilada
PivotView_StackedArea100 | Área 100% apilada
PivotView_Bubble | Burbuja
PivotView_Pareto | Pareto
PivotView_Radar | Radar
PivotView_CalculatedField_ClearTooltipMessage | Bearbeiten Sie die bearbeiteten Feldinformationen
PivotView_CalculatedField_EditTooltipMessage | Berechnetes Feld bearbeiten

The following are the list of properties and its values used in the field list.

Name |Value (in Deutsch culture)
----|-----
PivotFieldList_PercentageOfDifferenceFrom |% des Unterschieds von
PivotFieldList_Add | hinzufügen
PivotFieldList_AddFieldMessage | Feld hier hinzufügen
PivotFieldList_After | Nach
PivotFieldList_AfterOrEqualTo | Nach oder gleich
PivotFieldList_Alert | warnen
PivotFieldList_All | Alle
PivotFieldList_AllFields | alle Felder
PivotFieldList_And | und
PivotFieldList_Apply | ANWENDEN
PivotFieldList_Avg | Durchschn
PivotFieldList_BaseField | Basisfeld
PivotFieldList_BaseItem | Basisgegenstand
PivotFieldList_Before | Vor
PivotFieldList_BeforeOrEqualTo | Vorher oder gleich
PivotFieldList_BeginWith | Beginnt mit
PivotFieldList_Between | Zwischen
PivotFieldList_Blank | (Leer)
PivotFieldList_By | durch
PivotFieldList_CalculatedField | Berechnetes Feld
PivotFieldList_CalculatedField_ConfirmMessage | In diesem Namen ist bereits ein Berechnungsfeld vorhanden. Möchten Sie es ersetzen?
PivotFieldList_CalculatedField_DragDropMessage | Ziehen Sie Felder in die Formel und legen Sie sie dort ab
PivotFieldList_CalculatedField_DragMessage | Ziehen Sie das Feld in die Formel
PivotFieldList_CalculatedField_DropMessage | Das berechnete Feld kann nur in der Werteachse in einem anderen Bereich platziert werden.
PivotFieldList_CalculatedField_ExampleWatermark | Beispiel: ('Sum(Order_Count)' + 'Sum(In_Stock)'') * 250
PivotFieldList_CalculatedField_ExistMessage | In diesem Namen ist bereits ein Feld vorhanden. Bitte geben Sie einen anderen Namen ein.
PivotFieldList_CalculatedField_MobileWatermark | Fügen Sie hier Felder hinzu und bearbeiten Sie die Formel.
PivotFieldList_CalculatedField_NameWatermark | Geben Sie den Feldnamen ein
PivotFieldList_CalculatedField_OLAPExampleWatermark | Beispiel: [Measures].[Order Quantity] + ([Measures].[Order Quantity] * 0.10)
PivotFieldList_CalculatedField_Tooltip | Ziehen Sie Felder per Drag &amp; Drop, um einen Ausdruck zu erstellen. Und wenn Sie die vorhandenen die berechneten Felder bearbeiten möchten! Sie können dies erreichen, indem Sie einfach das Feld unter 'Berechnete Mitglieder' auswählen.
PivotFieldList_Cancel | Stornieren
PivotFieldList_ChooseFieldMessage | Feld auswählen
PivotFieldList_Clear | klar
PivotFieldList_ClearFilter | klar
PivotFieldList_Close | Schließen
PivotFieldList_ColumnAxisWatermark | Spalte hier ablegen
PivotFieldList_Columns | Säulen
PivotFieldList_Contains | Enthält
PivotFieldList_Copy | Kopieren
PivotFieldList_Count | Anzahl
PivotFieldList_CreateCalculatedField | Berechnetes Feld erstellen
PivotFieldList_Currency | Währung
PivotFieldList_Custom | Benutzerdefiniert
PivotFieldList_CustomFormat | Geben Sie eine benutzerdefinierte Formatzeichenfolge ein
PivotFieldList_Date | Datum
PivotFieldList_DateTextMessage | Zeigen Sie die Elemente an, für die das Datum gilt
PivotFieldList_Days | Tage
PivotFieldList_DeferLayoutUpdate | Layoutaktualisierung verschieben
PivotFieldList_Delete | Löschen
PivotFieldList_DifferenceFrom | Unterschied von
PivotFieldList_Dimension | Abmessungen
PivotFieldList_DistinctCount | Deutliche Anzahl
PivotFieldList_DoesNotBeginWith | Beginnt nicht mit
PivotFieldList_DoesNotContains | Beinhaltet nicht
PivotFieldList_DoesNotEndsWith | Endet nicht mit
PivotFieldList_DoesNotEquals | Ist nicht gleich
PivotFieldList_Drag | Ziehen
PivotFieldList_DragFieldsMessage | Ziehen Sie Felder zwischen den folgenden Achsen:
PivotFieldList_Edit | Bearbeiten
PivotFieldList_EndsWith | Endet mit
PivotFieldList_EnterDate | Datum eingeben
PivotFieldList_EnterValue | Wert eingeben
PivotFieldList_Equals | Gleich
PivotFieldList_Error | Fehler
PivotFieldList_Example | z.B:
PivotFieldList_Expression | Ausdruck
PivotFieldList_FieldCaption | Feldbeschriftung
PivotFieldList_FieldCaptionMessage | Feldbeschriftung
PivotFieldList_FieldDropErrorMessage | Das Feld, das Sie verschieben, kann nicht in diesem Bereich des Berichts platziert werden
PivotFieldList_FieldList | Feldliste
PivotFieldList_FieldName | Feldname
PivotFieldList_FieldNameMessage | Feldname :
PivotFieldList_FieldType | Feldtyp
PivotFieldList_Filter | Filter
PivotFieldList_FilterAxisWatermark | Filter hier ablegen
PivotFieldList_Filtered | Gefiltert
PivotFieldList_Filters | Filter
PivotFieldList_FormatString | Zeichenfolge formatieren
PivotFieldList_Formula | Formel
PivotFieldList_GreaterThan | Größer als
PivotFieldList_GreaterThanOrEqualTo | Größer als oder gleich wie
PivotFieldList_Group | Gruppe
PivotFieldList_Hours | Std
PivotFieldList_Index | Index
PivotFieldList_InvalidFormula | Ungültige Formel.
PivotFieldList_Label | Etikette
PivotFieldList_LabelTextMessage | Zeigen Sie die Elemente an, für die das Etikett
PivotFieldList_LessThan | Weniger als
PivotFieldList_LessThanOrEqualTo | Gleich oder kleiner als
PivotFieldList_Max | Max
PivotFieldList_Measure | Messen
PivotFieldList_Member | Mitglied
PivotFieldList_MemberLimitMessage | weitere Artikel. Suche, um weiter zu verfeinern.
PivotFieldList_Min | Mindest
PivotFieldList_Minutes | Protokoll
PivotFieldList_Months | Monate
PivotFieldList_MoreOption | Mehr...
PivotFieldList_MultipleItems | Mehrere Elemente
PivotFieldList_NoMatchesMessage | Keine Treffer
PivotFieldList_NotBetween | Nicht zwischen
PivotFieldList_Null | Null
PivotFieldList_OK | okay
PivotFieldList_OutOfRange | Außer Reichweite
PivotFieldList_ParentHierarchy | Übergeordnete Hierarchie
PivotFieldList_Percent | Prozent
PivotFieldList_PercentageOfColumnTotal | % der Spalte insgesamt
PivotFieldList_PercentageOfGrandTotal | % der Gesamtsumme
PivotFieldList_PercentageOfParentColumnTotal | % der übergeordneten Spalte insgesamt
PivotFieldList_PercentageOfParentRowTotal | % der Gesamtzahl der übergeordneten Zeilen
PivotFieldList_PercentageOfParentTotal | % der Elternsumme
PivotFieldList_PercentageOfRowTotal | % der Zeilensumme
PivotFieldList_PopulationStDev | Population StDev
PivotFieldList_PopulationVar | Bevölkerung Var
PivotFieldList_Product | Produkt
PivotFieldList_Quarters | Viertel
PivotFieldList_QuarterYear | Vierteljahr
PivotFieldList_Remove | Entfernen
PivotFieldList_RowAxisWatermark | Hier eine Zeile ablegen
PivotFieldList_Rows | Reihen
PivotFieldList_RunningTotals | Laufende Summen
PivotFieldList_SampleStDev | Beispiel StDev
PivotFieldList_SampleVar | Stichprobenvarianz
PivotFieldList_Search | Suche
PivotFieldList_Seconds | Sekunden
PivotFieldList_Sort | Sortieren
PivotFieldList_Standard | Standard
PivotFieldList_StaticFieldList | Pivot-Feldliste
PivotFieldList_Sum | Summe
PivotFieldList_Summaries | Werte zusammenfassen mit
PivotFieldList_SummarizeValuesBy | Werte zusammenfassen mit
PivotFieldList_Undefined | nicht definiert
PivotFieldList_Value | Wert
PivotFieldList_ValueAxisWatermark | Wert hier ablegen
PivotFieldList_ValueFieldSettings | Wertefeldeinstellungen
PivotFieldList_Values | Werte
PivotFieldList_ValueTextMessage | Zeigen Sie die Elemente an, für die
PivotFieldList_Warning | Warnung
PivotFieldList_Years | Jahre
PivotFieldList_CalculatedField_RemoveMessage | Möchten Sie dieses berechnete Feld wirklich löschen?
PivotFieldList_Yes | Ja
PivotFieldList_No | Nein
PivotFieldList_Of | von
PivotFieldList_NumberFormat_ExampleWatermark | Beispiel: C, P, 0000 %, ###0.##0#, etc.
PivotFieldList_SortNone_TooltipMessage | Datenreihenfolge sortieren
PivotFieldList_SortAscending_TooltipMessage | Aufsteigende Reihenfolge sortieren
PivotFieldList_SortDescending_TooltipMessage | Absteigende Reihenfolge sortieren
PivotFieldList_CalculatedField_EditTooltipMessage | Berechnetes Feld bearbeiten
PivotFieldList_CalculatedField_ClearTooltipMessage | Bearbeiten Sie die bearbeiteten Feldinformationen
PivotFieldList_Format | Format

All locale files for different cultures are available in this [GitHub](https://github.com/syncfusion/blazor-locale/tree/master/src) location. You can get any resource file from there and utilize it in your application.

* Finally, Specify the culture for pivot table using [`locale`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.SfPivotView%601~Locale.html) property.

```csharp
    @using Syncfusion.Blazor.PivotView;
    @using Syncfusion.Blazor

    <SfPivotView TValue="ProductDetails" Locale="de">
        <PivotViewDataSourceSettings DataSource="@data">
            <PivotViewColumns>
                <PivotViewColumn Name="Year"></PivotViewColumn>
                <PivotViewColumn Name="Quarter"></PivotViewColumn>
            </PivotViewColumns>
            <PivotViewRows>
                <PivotViewRow Name="Country"></PivotViewRow>
                <PivotViewRow Name="Products"></PivotViewRow>
            </PivotViewRows>
            <PivotViewValues>
                <PivotViewValue Name="Sold" Caption="Unit Sold"></PivotViewValue>
                <PivotViewValue Name="Amount" Caption="Sold Amount"></PivotViewValue>
            </PivotViewValues>
            <PivotViewFormatSettings>
                <PivotViewFormatSetting Name="Amount" Format="C0" UseGrouping=true></PivotViewFormatSetting>
            </PivotViewFormatSettings>
        </PivotViewDataSourceSettings>
    </SfPivotView>
    @code{
        public List<ProductDetails> data { get; set; }
        protected override void OnInitialized()
        {
            this.data = ProductDetails.GetProductData().ToList();
           //Bind the data source collection here. Refer "Assigning sample data to the pivot table" section in  getting started for more details.
        }
    }

```

![output](images/localization.png)

### Blazor WebAssembly

The following example demonstrates the pivot table in **Deutsch** culture. Here we use **LoadLocaleData** method to load the **locale.json** file and **SetCulture** method to set the culture of the pivot table in Blazor WebAssembly sample.

For Blazor WebAssembly, we use **JSON** file which contains translated text of the culture. The following list of properties and its values are used in the pivot table.

Locale Keywords |Text
-----|-----
grandTotal | Grand Total
total | Total
value | Value
noValue | No value
row | Row
column | Column
collapse | Collapse
expand | Expand
rowAxisPrompt | Drop row here
columnAxisPrompt | Drop column here
valueAxisPrompt | Drop value here
filterAxisPrompt | Drop filter here
filter | Filter
filtered | Filtered
sort | Sort
filters | Filters
rows | Rows
columns | Columns
values | Values
close | Close
cancel | Cancel
delete | Delete
CalculatedField | Calculated Field
createCalculatedField | Create Calculated Field
fieldName | Enter the field name
error | Error
invalidFormula | Invalid formula.
dropText | Example: ('Sum(Order_Count)' + 'Sum(In_Stock)') * 250
dropTextMobile | Add fields and edit formula here.
dropAction | Calculated field cannot be place in any other region except value axis.
alert | Alert
warning | Warning
ok | OK
search | Search
drag | Drag
remove | Remove
allFields | All Fields
formula | Formula
addToRow | Add to Row
addToColumn | Add to Column
addToValue | Add to Value
addToFilter | Add to Filter
emptyData | No records to display
fieldExist | A field already exists in this name. Please enter a different name.
confirmText | A calculation field already exists in this name. Do you want to replace it?
noMatches | No matches
format | Summaries values by
edit | Edit
clear | Clear
formulaField | Drag and drop fields to formula
dragField | Drag field to formula
clearFilter | Clear
by | by
all | All
multipleItems | Multiple items
member | Member
label | Label
date | Date
enterValue | Enter value
chooseDate | Enter date
Before | Before
BeforeOrEqualTo | Before Or Equal To
After | After
AfterOrEqualTo | After Or Equal To
labelTextContent | Show the items for which the label
dateTextContent | Show the items for which the date
valueTextContent | Show the items for which
Equals | Equals
DoesNotEquals | Does Not Equal
BeginWith | Begins With
DoesNotBeginWith | Does Not Begin With
EndsWith | Ends With
DoesNotEndsWith | Does Not End With
Contains | Contains
DoesNotContains | Does Not Contain
GreaterThan | Greater Than
GreaterThanOrEqualTo | Greater Than Or Equal To
LessThan | Less Than
LessThanOrEqualTo | Less Than Or Equal To
Between | Between
NotBetween | Not Between
And | and
Sum | Sum
Count | Count
DistinctCount | Distinct Count
Product | Product
Avg | Avg
Min | Min
SampleVar | Sample Var
PopulationVar | Population Var
RunningTotals | Running Totals
Max | Max
Index | Index
SampleStDev | Sample StDev
PopulationStDev | Population StDev
PercentageOfRowTotal | % of Row Total
PercentageOfParentTotal | % of Parent Total
PercentageOfParentColumnTotal | % of Parent Column Total
PercentageOfParentRowTotal | % of Parent Row Total
DifferenceFrom | Difference From
PercentageOfDifferenceFrom | % of Difference From
PercentageOfGrandTotal | % of Grand Total
PercentageOfColumnTotal | % of Column Total
NotEquals | Not Equals
AllValues | All Values
conditionalFormating | Conditional Formatting
apply | Apply
condition | Add Condition
formatLabel | Format
valueFieldSettings | Value field settings
baseField | Base field
baseItem | Base item
summarizeValuesBy | Summarize values by
sourceName | Field name :
sourceCaption | Field caption
example | e.g:
editorDataLimitMsg |  more items. Search to refine further.
details | Details
manageRecords | Manage Records
Years | Years
Quarters | Quarters
Months | Months
Days | Days
Hours | Hours
Minutes | Minutes
Seconds | Seconds
save | Save a report
new | Create a new report
load | Load
saveAs | Save as current report
rename | Rename a current report
deleteReport | Delete a current report
export | Export
subTotals | Sub totals
grandTotals | Grand totals
reportName | Report Name :
pdf | PDF
excel | Excel
csv | CSV
png | PNG
jpeg | JPEG
svg | SVG
mdxQuery | MDX Query
showSubTotals | Show sub totals
doNotShowSubTotals | Do not show sub totals
showSubTotalsRowsOnly | Show sub totals rows only
showSubTotalsColumnsOnly | Show sub totals columns only
showGrandTotals | Show grand totals
doNotShowGrandTotals | Do not show grand totals
showGrandTotalsRowsOnly | Show grand totals rows only
showGrandTotalsColumnsOnly | Show grand totals columns only
fieldList | Show fieldlist
grid | Show table
toolbarFormatting | Conditional formatting
chart | Chart
reportMsg | Please enter valid report name!!!
reportList | Report list
removeConfirm | Are you sure you want to delete this report?
emptyReport | No reports found!!
bar | Bar
line | Line
area | Area
scatter | Scatter
polar | Polar
of | of
emptyFormat | No format found!!!
emptyInput | Enter a value
newReportConfirm | Do you want to save the changes to this report?
emptyReportName | Enter a report name
qtr | Qtr
null | null
undefined | undefined
groupOutOfRange | Out of Range
fieldDropErrorAction | The field you are moving cannot be placed in that area of the report
MoreOption | More...
aggregate | Aggregate
drillThrough | Drill Through
ascending | Ascending
descending | Descending
number | Number
currency | Currency
percentage | Percentage
formatType | Format Type
customText | Currency Symbol
symbolPosition | Symbol Position
left | Left
right | Right
grouping | Grouping
true | True
false | False
decimalPlaces | Decimal Places
numberFormat | Number Formatting
memberType | Field Type
formatString | Format
expressionField | Expression
customFormat | Enter custom format string
selectedHierarchy | Parent Hierarchy
olapDropText | Example: [Measures].[Order Quantity] + ([Measures].[Order Quantity] * 0.10)
Percent | Percent
Custom | Custom
Measure | Measure
Dimension | Dimension
Standard | Standard
blank | (Blank)
fieldTooltip | Drag and drop fields to create an expression. And, if you want to edit the existing calculated fields! Then you can achieve it by simply selecting the field under calculated Members'.
QuarterYear | Quarter Year
fieldTitle | Field Name
drillError | Cannot show the raw items of calculated fields.
caption | Field Caption
copy | Copy
defaultReport | Sample Report
customFormatString | Custom Format
invalidFormat | Invalid Format.
group | Group
unGroup | Ungroup
invalidSelection | Cannot group that selection.
groupName | Enter the caption to display in header
captionName | Enter the caption for group field
selectedItems | Selected items
groupFieldCaption | Field caption
groupTitle | Group name
startAt | Starting at
endAt | Ending at
groupBy | Interval by
selectGroup | Select groups
numberFormatString | Example: C, P, 0000 %, ###0.##0#, etc.
stackingcolumn | Stacked Column
stackingbar | Stacked Bar
stackingarea | Stacked Area
stepline | Step Line
steparea | Step Area
splinearea | Spline Area
spline | Spline
stackingcolumn100 | 100% Stacked Column
stackingbar100 | 100% Stacked Bar
stackingarea100 | 100% Stacked Area
bubble | bubble
pareto | Pareto
radar | Radar
chartTypeSettings | Chart type settings
multipleAxes | Multiple Axes
sortAscending | Sort ascending order
sortDescending | Sort descending order
sortNone | Sort data order
clearCalculatedField | Clear edited field info
editCalculatedField | Edit calculated field
ChartType | Chart Type
yes | Yes
no | No
numberFormatMenu | Number Formatting...
conditionalFormatingMenu | Conditional Formatting...
removeCalculatedField | Are you sure you want to delete this calculated field?
replaceConfirmBefore | A report named
replaceConfirmAfter |  already exists. Do you want to replace it?

The following are the list of properties and its values used in the field list.

Locale Keywords |Text
-----|-----
staticFieldList | Pivot Field List
fieldList | Field List
dropFilterPrompt | Drop filter here
dropColPrompt | Drop column here
dropRowPrompt | Drop row here
dropValPrompt | Drop value here
addPrompt | Add field here
adaptiveFieldHeader | Choose field
centerHeader | Drag fields between axes below:
add | add
drag | Drag
filter | Filter
filtered | Filtered
sort | Sort
remove | Remove
filters | Filters
rows | Rows
columns | Columns
values | Values
CalculatedField | Calculated Field
createCalculatedField | Create Calculated Field
fieldName | Enter the field name
error | Error
invalidFormula | Invalid formula.
dropText | Example: ('Sum(Order_Count)' + 'Sum(In_Stock)'') * 250
dropTextMobile | Add fields and edit formula here.
dropAction | Calculated field cannot be place in any other region except value axis.
search | Search
close | Close
cancel | Cancel
delete | Delete
alert | Alert
warning | Warning
ok | OK
allFields | All Fields
formula | Formula
fieldExist | A field already exists in this name. Please enter a different name.
confirmText | A calculation field already exists in this name. Do you want to replace it?
noMatches | No matches
format | Summaries values by
edit | Edit
clear | Clear
formulaField | Drag and drop fields to formula
dragField | Drag field to formula
clearFilter | Clear
by | by
enterValue | Enter value
chooseDate | Enter date
all | All
multipleItems | Multiple items
Equals | Equals
DoesNotEquals | Does Not Equal
BeginWith | Begins With
DoesNotBeginWith | Does Not Begin With
EndsWith | Ends With
DoesNotEndsWith | Does Not End With
Contains | Contains
DoesNotContains | Does Not Contain
GreaterThan | Greater Than
GreaterThanOrEqualTo | Greater Than Or Equal To
LessThan | Less Than
LessThanOrEqualTo | Less Than Or Equal To
Between | Between
NotBetween | Not Between
Before | Before
BeforeOrEqualTo | Before Or Equal To
After | After
AfterOrEqualTo | After Or Equal To
member | Member
label | Label
date | Date
value | Value
labelTextContent | Show the items for which the label
dateTextContent | Show the items for which the date
valueTextContent | Show the items for which
And | and
Sum | Sum
Count | Count
DistinctCount | Distinct Count
Product | Product
Avg | Avg
Min | Min
Max | Max
Index | Index
SampleStDev | Sample StDev
PopulationStDev | Population StDev
SampleVar | Sample Var
PopulationVar | Population Var
RunningTotals | Running Totals
DifferenceFrom | Difference From
PercentageOfDifferenceFrom | % of Difference From
PercentageOfGrandTotal | % of Grand Total
PercentageOfColumnTotal | % of Column Total
PercentageOfRowTotal | % of Row Total
PercentageOfParentTotal | % of Parent Total
PercentageOfParentColumnTotal | % of Parent Column Total
PercentageOfParentRowTotal | % of Parent Row Total
Years | Years
Quarters | Quarters
Months | Months
Days | Days
Hours | Hours
Minutes | Minutes
Seconds | Seconds
apply | Apply
valueFieldSettings | Value field settings
sourceName | Field name :
sourceCaption | Field caption
summarizeValuesBy | Summarize values by
baseField | Base field
baseItem | Base item
example | e.g:
editorDataLimitMsg |  more items. Search to refine further.
deferLayoutUpdate | Defer Layout Update
null | null
undefined | undefined
groupOutOfRange | Out of Range
fieldDropErrorAction | The field you are moving cannot be placed in that area of the report
MoreOption | More...
memberType | Field Type
selectedHierarchy | Parent Hierarchy
formatString | Format
expressionField | Expression
olapDropText | Example: [Measures].[Order Quantity] + ([Measures].[Order Quantity] * 0.10)
customFormat | Enter custom format string
Measure | Measure
Dimension | Dimension
Standard | Standard
Currency | Currency
Percent | Percent
Custom | Custom
blank | (Blank)
fieldTooltip | Drag and drop fields to create an expression. And, if you want to edit the existing calculated fields! You can achieve it by simply selecting the field under 'Calculated Members'.
fieldTitle | Field Name
QuarterYear | Quarter Year
caption | Field Caption
copy | Copy
group | Group
numberFormatString | Example: C, P, 0000 %, ###0.##0#, etc.
sortAscending | Sort ascending order
sortDescending | Sort descending order
sortNone | Sort data order
clearCalculatedField | Clear edited field info
editCalculatedField | Edit calculated field
selectGroup | Select groups
of | of
removeCalculatedField | Are you sure you want to delete this calculated field?

The following example demonstrates the pivot table in **Deutsch** culture. Here we have used `LoadLocaleData` method to load the **wwwroot/ej2-locale/src/de.json** file and `SetCulture` method to set the culture to `de`.

```csharp
    @using Syncfusion.Blazor.PivotView;
    @using Syncfusion.Blazor
    @using Microsoft.JSInterop;

    <SfPivotView TValue="ProductDetails">
        <PivotViewDataSourceSettings DataSource="@data">
            <PivotViewColumns>
                <PivotViewColumn Name="Year"></PivotViewColumn>
                <PivotViewColumn Name="Quarter"></PivotViewColumn>
            </PivotViewColumns>
            <PivotViewRows>
                <PivotViewRow Name="Country"></PivotViewRow>
                <PivotViewRow Name="Products"></PivotViewRow>
            </PivotViewRows>
            <PivotViewValues>
                <PivotViewValue Name="Sold" Caption="Unit Sold"></PivotViewValue>
                <PivotViewValue Name="Amount" Caption="Sold Amount"></PivotViewValue>
            </PivotViewValues>
            <PivotViewFormatSettings>
                <PivotViewFormatSetting Name="Amount" Format="C0" UseGrouping=true></PivotViewFormatSetting>
            </PivotViewFormatSettings>
        </PivotViewDataSourceSettings>
    </SfPivotView>
    @code{
        public List<ProductDetails> data { get; set; }
        protected override void OnInitialized()
        {
            this.data = ProductDetails.GetProductData().ToList();
           //Bind the data source collection here. Refer "Assigning sample data to the pivot table" section in  getting started for more details.
        }
        [Inject]
        protected IJSRuntime JsRuntime { get; set; }
        protected override void OnAfterRender()
        {
            this.JsRuntime.Sf().LoadLocaleData("wwwroot/ej2-locale/src/de.json").SetCulture("de");
        }
    }

```

![output](images/localization.png)

## Internationalization

Internationalization library is used to globalize number, date, and time values in pivot table component using format strings in the [`Format`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.PivotViewFormatSetting~Format.html). In the below sample we set the culture and currency using the `SetCulture` and `SetCurrencyCode` methods.

```csharp
    @using Syncfusion.Blazor.PivotView;
    @using Syncfusion.Blazor
    @using Microsoft.JSInterop;

    <SfPivotView TValue="ProductDetails">
        <PivotViewDataSourceSettings DataSource="@data">
            <PivotViewColumns>
                <PivotViewColumn Name="Year"></PivotViewColumn>
                <PivotViewColumn Name="Quarter"></PivotViewColumn>
            </PivotViewColumns>
            <PivotViewRows>
                <PivotViewRow Name="Country"></PivotViewRow>
                <PivotViewRow Name="Products"></PivotViewRow>
            </PivotViewRows>
            <PivotViewValues>
                <PivotViewValue Name="Sold" Caption="Unit Sold"></PivotViewValue>
                <PivotViewValue Name="Amount" Caption="Sold Amount"></PivotViewValue>
            </PivotViewValues>
            <PivotViewFormatSettings>
                <PivotViewFormatSetting Name="Amount" Format="C0" UseGrouping=true></PivotViewFormatSetting>
            </PivotViewFormatSettings>
        </PivotViewDataSourceSettings>
    </SfPivotView>

    @code{
        public List<PivotViewData.ProductDetails> data { get; set; }
        public List<ProductDetails> data { get; set; }
        protected override void OnInitialized()
        {
            this.data = ProductDetails.GetProductData().ToList();
           //Bind the data source collection here. Refer "Assigning sample data to the pivot table" section in  getting started for more details.
        }
        [Inject]
        protected IJSRuntime JsRuntime { get; set; }
        protected override void OnAfterRender()
        {
            if (firstRender)
            {
                this.JsRuntime.Sf().SetCulture("de-DE").SetCurrencyCode("EUR");
            }
        }
    }

```

> * In the above sample, **Amount** column is formatted by [`Format`](https://help.syncfusion.com/cr/cref_files/blazor/Syncfusion.Blazor~Syncfusion.Blazor.PivotView.PivotViewFormatSetting~Format.html).
> * Default culture is **en-US**. If you want to change the **en-US** culture to a different culture, you have to set accordingly in `SetCulture` method.
> * The decimal separators of pivot table values varies based on the culture applied to the component.

![output](images/pivot-globalization.png)

## Right-to-left (RTL)

Right-to-left (RTL) provides an option to switch the text direction and layout of the pivot table component from right to left. It improves user experiences and accessibility for users who use right-to-left languages (Arabic, Farsi, Urdu, etc...). In the below code sample `EnableRtl` method is used to enable RTL in the pivot table.

```csharp
@using Microsoft.JSInterop;
@using Syncfusion.Blazor.PivotView

   <SfPivotView TValue="ProductDetails" ShowFieldList="true">
         <PivotViewDataSourceSettings DataSource="@data">
            <PivotViewColumns>
                <PivotViewColumn Name="Year"></PivotViewColumn>
                <PivotViewColumn Name="Quarter"></PivotViewColumn>
            </PivotViewColumns>
            <PivotViewRows>
                <PivotViewRow Name="Country"></PivotViewRow>
                <PivotViewRow Name="Products"></PivotViewRow>
            </PivotViewRows>
            <PivotViewValues>
                <PivotViewValue Name="Sold" Caption="Unit Sold"></PivotViewValue>
                <PivotViewValue Name="Amount" Caption="Sold Amount"></PivotViewValue>
            </PivotViewValues>
            <PivotViewFormatSettings>
                <PivotViewFormatSetting Name="Amount" Format="C0" UseGrouping=true></PivotViewFormatSetting>
            </PivotViewFormatSettings>
        </PivotViewDataSourceSettings>
    </SfPivotView>

    @code{
        public List<ProductDetails> data { get; set; }
        protected override void OnInitialized()
        {
            this.data = ProductDetails.GetProductData().ToList();
           //Bind the data source collection here. Refer "Assigning sample data to the pivot table" section in getting started for more details.
        }
        [Inject]
        protected IJSRuntime JsRuntime { get; set; }
        protected override void OnAfterRender()
        {
            this.JsRuntime.Sf().EnableRtl(true);
        }
    }

```

![output](images/pivot-rtl.png)