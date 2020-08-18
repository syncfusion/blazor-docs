---
title: "Blazor In-place Editor | Integrate HTML5 components"
component: "In-place Editor"
description: "This section describes how to integrate native HTML5 components (input, date, and more) to the Blazor In-place Editor through a selector and HTML element."
---

# Integrate HTML5 components (Template)

The In-place Editor supports adding HTML5 input components using the `Template` property. The Template property can be given as follows.

```bash
<InPlaceEditorTemplates>
    <Template>
        <input id="date" type="date" />
    </Template>
</InPlaceEditorTemplates>

```

Template mode, the `Value` property not handled by the In-place Editor component. So, before sending a value to the server, you need to modify the `OnActionSuccess` event, otherwise, an empty string will pass. In the following template sample, before submitting a data to the server, event argument and `Value` property content updated in the `OnActionSuccess` event handler.

```csharp

@using Syncfusion.Blazor.InPlaceEditor

<div id='container'>
    <span class="content-title"> Select date: </span>
    <SfInPlaceEditor @ref="InplaceditorObj" EmptyText="Value" TValue="string" Mode="RenderMode.Inline" Type="InputType.Date">
        <InPlaceEditorEvents TValue="string" OnActionSuccess="OnSuccess"></InPlaceEditorEvents>
        <InPlaceEditorTemplates>
            <Template>
                <input @bind="Value" id="date" type="text" />
            </Template>
        </InPlaceEditorTemplates>
    </SfInPlaceEditor>
</div>

<style>
    #container {
        display: flex;
        justify-content: center;
    }

    #InplaceDate {
        width: 150px;
    }

    .content-title {
        font-weight: 500;
        margin-right: 20px;
        display: flex;
        align-items: center;
    }
</style>

@code {
    SfInPlaceEditor<string> InplaceditorObj;

    public string Value { get; set; } = "2018-05-23";

    private void OnSuccess(ActionEventArgs arg)
    {
        this.InplaceditorObj.Value = Value;
        arg.Value = Value;
    }
}

```

The output will be as follows.

![html-template](./images/html-template.png)

## See Also

* [Built-in Controls](./controls/)