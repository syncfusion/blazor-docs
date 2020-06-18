# Custom Resource Generator

Syncfusion provides an option to generate a selective control script (JavaScript ES5) and styles using the [`Custom Resource Generator`](https://crg.syncfusion.com/) (CRG) web tool.

![ej2 Custom resource generator preview](images/custom-resource-generator-preview.png)

## Search and select the control list

Search and select the required Syncfusion controls from CRG to generate specific set of control resources.

The Syncfusion Blazor UI controls can be categorized based on the following characteristics:

* Injectable module supported controls
* Injectable module non-supported controls

The `Injectable module supported controls` are rendered as tree view with check box format, and the `Injectable module non-supported controls` are rendered as normal check box format in CRG application.

![ej2 Control categorization](images/controls-categorization.png)

Refer to the following steps to search and select the controls in CRG:

1. Navigate to the Custom Resource Generator (CRG) application at [`CRG`](https://crg.syncfusion.com/).

2. Type the required control name in the search bar and select the check box. The dependency of the selected control is resolved in the application itself, so you do not need to choose each dependent control manually.

   ![ej2 Search and select non-injectable module controls](images/search- non-injectable.png)

3. Click the expand icon and select the required features for the injectable module supported controls.

   ![ej2 Select injectable module supported controls](images/select-injectable-module.png)

4. If the entire modules of the controls are needed, then click the specific control's check box to select all injectable modules.

   ![ej2 Select all injectable modules](images/select-all-injectable.png)

5. Select the required built-in themes from the **Select Themes** option. This provides an option to select more than one theme.

   ![ej2 Select the built-in themes](images/select-inbuilt-themes.png)

## Download the selected control resources

After selecting the required control resources, download the custom script and styles from CRG.

Refer to the following steps to download the custom resources in CRG:

1. Click the **DOWNLOAD** button at the bottom of the page. Select the **Minified** option to generate the minified file output for production.

   ![ej2 Download option](images/download-option.png)

2. Change the file name as needed, and click **GENERATE** button in the pop-up.

   ![ej2 Export popup for generation custom resources](images/export-popup.png)

3. Now, the bundling process for the selected controls will be started, and the output will be downloaded as a zip file.

   ![ej2 Bundle custom resources](images/bundling-custom-resources.png)

4. The final output contains the script and styles for the selected controls and a **settings.json** file, which stores the current settings.

   ![ej2 Final output of customized resources](images/customized-resources.png)

## Import previously generated settings into CRG

To add more controls or upgrade the latest Syncfusion Blazor library resources, it is not necessary to generate it from the scratch in the CRG. Just import the old **settings.json** file, make the changes, and then download it again from the CRG application.

Refer to the following steps to import previous settings in CRG:

1. Click the **IMPORT SETTINGS** button at the bottom of the page.

   ![ej2 Import option in CRG](images/import-option.png)

2. Upload the **settings.json** file, so that the previously stored data will be restored in the CRG application. Now, add more controls and export the resources again.

   ![ej2 Previous chages restored](images/previous-changes-restored.png)
