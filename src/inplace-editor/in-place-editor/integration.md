# Integrate HTML5 components (Template)

The In-place Editor supports adding HTML5 input components using the `InPlaceEditorTemplate` property. The Template property can be given as follows.

```bash
 <InPlaceEditorTemplate>
    <input id="date" type="text" />
</InPlaceEditorTemplate>

```

In Template mode, the `Value` property cannot be handled by the In-place Editor component. So, before sending a value to the server, you need to modify the `OnActionSuccess` event, otherwise, an empty string will be passed.

In the following template sample, before submitting data to the server, the event argument and `Value` property contents are updated in the `OnActionSuccess` event handler.

```csharp

@using Syncfusion.Blazor.InPlaceEditor

<div id='container'>
    <span class="content-title"> Select date: </span>
    <SfInPlaceEditor @ref="InplaceditorObj" EmptyText="Value" TValue="string" @bind-Value="@inplaceValue" Mode="RenderMode.Inline" Type="InputType.Template">
        <InPlaceEditorTemplate>
            <input @bind-value="@inplaceValue" id="date" type="text" />
        </InPlaceEditorTemplate>
        <InPlaceEditorEvents TValue="string" OnActionSuccess="OnSuccess"></InPlaceEditorEvents>
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

    public string inplaceValue { get; set; } = "syncfusion";

    private void OnSuccess(ActionEventArgs<string> args)
    {
        inplaceValue = args.Value;
    }
}

```

The output will be as follows.

![html-template](./images/html-template.png)

## See Also

* [Built-in Controls](./controls/)
