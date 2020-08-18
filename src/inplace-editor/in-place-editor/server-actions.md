---
title: "Blazor In-place Editor | Server actions through AJAX"
component: "In-place Editor"
description: "This section explains how to handle server actions (save the modified value in server) by handling success and failure events in the Blazor In-place Editor."
---

# Server actions

By passing In-place Editor component value to the server, the `PrimaryKey` property value must require, otherwise action not performed for remote data.

If the `URL` property value is empty, data passing will handled at local and also the `OnActionSuccess` event will trigger with `null` as argument value.

> The following arguments are passed to the server when the submit actions are performed.

| Arguments  | Explanations                                              |
|------------|-----------------------------------------------------------|
| Value      | For processing edited value, like DB value updating.      |
| PrimaryKey | For value mapping to the server, like selecting DB.            |
| Name       | For field mapping to the server, like DB column field mapping. |

Find the following sample server codes for defining models and controller functions to configure processing data.

```csharp
    public class SubmitModel
    {
        public string Name { get; set; }
        public string PrimaryKey { get; set; }
        public string Value { get; set; }
    }
```

```csharp

    public IEnumerable<SubmitModel> UpdateData([FromBody]SubmitModel value)
    {
        // User can process data
        return value;
    }

```

* Server actions successfully done, the `OnActionSuccess` event will be fired with returned server data.

* If the server is not responding, the `OnActionFailure` event will be fired with data, but value not updated in the Editor.

In the following sample, the `OnActionSuccess` event will trigger once the value submitted successfully into the server.

```csharp

@using Syncfusion.Blazor.DropDowns
@using Syncfusion.Blazor.InPlaceEditor

<table class="table-section">
    <tr>
        <td class="sample-td"> Enter your name: </td>
        <td class="sample-td">
            <SfInPlaceEditor Name="Skill" Url="https://ej2services.syncfusion.com/production/web-services/api/Editor/UpdateData" PrimaryKey="FrameWork" Adaptor="AdaptorType.UrlAdaptor" Mode="RenderMode.Inline" EnableEditMode="true" Type="InputType.MultiSelect" Value="MultiSelectValue" SubmitOnEnter="true" Model="MultiSelectData">
                <InPlaceEditorEvents OnActionSuccess="OnSuccess" TValue="string"></InPlaceEditorEvents>
            </SfInPlaceEditor>
        </td>
    </tr>
</table>

<style>
    .table-section {
        margin: 0 auto;
    }

    tr td:first-child {
        text-align: right;
        padding-right: 20px;
    }

    .sample-td {
        padding-top: 10px;
        min-width: 230px;
        height: 100px;
    }
</style>

@code {
    public string[] MultiSelectValue = new string[] { "JavaScript", "jQuery" };

    public Syncfusion.Blazor.InPlaceEditor.MultiSelectModel<string> MultiSelectData = new Syncfusion.Blazor.InPlaceEditor.MultiSelectModel<string>()
    {
        Placeholder = "Select skill",
        Mode = VisualMode.Box,
        DataSource = new string[] { "Android", "JavaScript", "jQuery", "TypeScript", "Angular", "React", "Vue", "Ionic" }
    };

    public void OnSuccess(ActionEventArgs args)
    {
        Console.WriteLine("Event is triggered");
    }
}

```