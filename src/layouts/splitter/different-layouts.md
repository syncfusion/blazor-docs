---
title: "Blazor Collapsible Splitter | Different layouts"
component: "Splitter"
description: "This section explains how to construct different layouts using mulitple and nested panes."
---

# Different layouts

By using splitter control, you can create the different layouts with multiple and nested panes.

## Code editor style layout

**Step 1**:
Create the element with two child to render the outer splitter.

```csharp

<SfSplitter Height="400px" Orientation="Orientation.Vertical">
    <SplitterPanes>
        <SplitterPane Size="53%" Min="30%">
            <SfSplitter Height="220px" Width="100%">
                <SplitterPanes>
                    <SplitterPane Size="29%" Min="23%">
                    </SplitterPane>
                    <SplitterPane Size="20%" Min="15%">
                    </SplitterPane>
                    <SplitterPane Size="35%" Min="35%">
                    </SplitterPane>
                </SplitterPanes>
            </SfSplitter>
        </SplitterPane>
        <SplitterPane Size="53%" Min="30%">
            <ContentTemplate>
                <div class="code-editor-content">
                    <h3 class="h3">Preview of sample</h3>
                    <div class="splitter-image">
                        <img class="img1" src="https://blazor.syncfusion.com/demos/images/Splitter/albert.png" style="width: 20%;margin: 0 auto;">
                    </div>
                </div>
            </ContentTemplate>
        </SplitterPane>
    </SplitterPanes>
</SfSplitter>

```

**Step 2** :

Render the first pane of vertical splitter as a horizontal splitter.

```csharp

@using Syncfusion.Blazor
@using Syncfusion.Blazor.Layouts

<SfSplitter Height="400px" Orientation="Orientation.Vertical">
    <SplitterPanes>
        <SplitterPane Size="53%" Min="30%">
            <SfSplitter Height="220px" Width="100%">
                <SplitterPanes>
                    <SplitterPane Size="29%" Min="23%">
                        <ContentTemplate>
                            <div class="code-editor-content">
                                <h3 class="h3">HTML</h3>
                                <div class="code-preview">
                                    &lt;<span>!DOCTYPE html></span>
                                    <div>&lt;<span>html></span></div>
                                    <div>&lt;<span>body></span></div>
                                    &lt;<span>div</span> id="custom-image">
                                    <div style="margin-left: 5px">&lt;<span>img</span> src="src/albert.png"></div>
                                    <div>&lt;<span>div</span>&gt;</div>
                                    <div>&lt;<span>/body></span></div>
                                    <div>&lt;<span>/html></span></div>
                                </div>
                            </div>
                        </ContentTemplate>
                    </SplitterPane>
                    <SplitterPane Size="20%" Min="15%">
                        <ContentTemplate>
                            <div class="code-editor-content">
                                <h3 class="h3">CSS</h3>
                                <div class="code-preview">
                                    <span>img {</span>
                                    <div id="code-text">margin:<span>0 auto;</span></div>
                                    <div id="code-text">display:<span>flex;</span></div>
                                    <div id="code-text">height:<span>70px;</span></div>
                                    <span>   }</span>
                                </div>
                            </div>
                        </ContentTemplate>
                    </SplitterPane>
                    <SplitterPane Size="35%" Min="35%">
                        <ContentTemplate>
                            <div class="code-editor-content">
                                <h3 class="h3">JavaScript</h3>
                                <div class="code-preview">
                                    <span>var</span> image = document.getElementById("custom-image");
                                    <div>image.addEventListener("click", function() {</div>
                                    <div style="padding-left: 20px;">// Code block for click action</div>
                                    <span> }</span>
                                </div>
                            </div>
                        </ContentTemplate>
                    </SplitterPane>
                </SplitterPanes>
            </SfSplitter>
        </SplitterPane>
        <SplitterPane Size="53%" Min="30%">
            <ContentTemplate>
                <div class="code-editor-content">
                    <h3 class="h3">Preview of sample</h3>
                    <div class="splitter-image">
                        <img class="img1" src="https://blazor.syncfusion.com/demos/images/Splitter/albert.png" style="width: 20%;margin: 0 auto;">
                    </div>
                </div>
            </ContentTemplate>
        </SplitterPane>
    </SplitterPanes>
</SfSplitter>

```

```bash

<style>
    .code-preview {
        margin-top: 15px;
        font-size: 12px;
    }
    .content {
        padding: 12px;
    }
    .splitter-image {
        margin: 0 auto;
        display: flex;
        height: 115px;
        margin-top: 10px;
    }
    .h3 {
        font-size: 14px;
        margin: 4px;
        padding: 5px;
    }
</style>

```

Once the above configurations has been completed, you will get the output like [this](https://blazor.syncfusion.com/demos/splitter/code-editor-layout?theme=bootstrap4)

## Outlook style layout

**Step 1**:

Create the element with three panes and place the elements within the pane to render `Treeview`, `Listview` and `RichTextEditor`.

```csharp

@using Syncfusion.Blazor
@using Syncfusion.Blazor.Layouts
@using Syncfusion.Blazor.Lists
@using Syncfusion.Blazor.Navigations
@using Syncfusion.Blazor.Buttons
@using Syncfusion.Blazor.RichTextEditor
@using Syncfusion.Blazor.Inputs

<SfSplitter Height="493px" Width="100%" CssClass="splitter-layout">
    <SplitterEvents OnResizeStop="resizeStop"></SplitterEvents>
        <SplitterPanes>
        <SplitterPane Size="28%" Min="27%">
            <ContentTemplate>
                <div class="outlook-layout-content">
                    <SfTreeView ModelType="@ModelType" TValue="TreeData">
                        <TreeViewFieldsSettings Id="Id" TValue="TreeData" Text="Name" ParentID="Pid" HasChildren="HasChild" Selected="Selected" Expanded="Expanded" DataSource="@localData"></TreeViewFieldsSettings>
                    </SfTreeView>
                </div>
            </ContentTemplate>
        </SplitterPane>
        <SplitterPane Size="33%" Min="23%">
            <ContentTemplate>
                <div class="outlook-layout-content">
                    <SfListView CssClass="grouped-list" DataSource="@dataSource" ModelType="@model" CssClass="e-list-template">
                        <ListViewFieldSettings Text="Name" GroupBy="Order"></ListViewFieldSettings>
                        <ListViewTemplates>
                            <Template>
                                @{
                                    DataModel ContextData = context as DataModel;
                                    <div class="settings e-list-wrapper e-list-multi-line e-list-avatar">
                                        <span class="e-list-item-header">@ContextData.Name</span>
                                        <div class="e-list-content">
                                            <div class="status">@ContextData.Content1</div><div id="list-message">@ContextData.Content2</div>
                                        </div>
                                    </div>
                                }
                            </Template>
                            <GroupTemplate>
                                <div class="e-list-wrapper"><span class="e-list-item-content"></span></div>
                            </GroupTemplate>
                        </ListViewTemplates>
                    </SfListView>
                </div>
            </ContentTemplate>
        </SplitterPane>
        <SplitterPane Size="37%" Min="30%">
            <ContentTemplate>
                <div class="outlook-layout-content">
                    <div style="width: 100%; padding: 15px;">
                        <table>
                            <tr>
                                <td><button class="e-btn e-flat e-outline">To...</button></td>
                                <td><SfTextBox></SfTextBox></td>
                            </tr>
                            <tr>
                                <td><button class="e-btn e-flat e-outline">Cc...</button></td>
                                <td><SfTextBox></SfTextBox></td>
                            </tr>
                            <tr>
                                <td><div id="subject-text">Subject</div></td>
                                <td><SfTextBox></SfTextBox></td>
                            </tr>
                        </table>
                    </div>
                    <div class="forum">
                        <div id="createpostholder">
                            <SfRichTextEditor @ref="RichTextEditorObj" Height="262px">
                                <RichTextEditorEvents Created="Created"></RichTextEditorEvents>
                            </SfRichTextEditor>
                            <div id="buttonSection">
                                <SfButton IsPrimary="true">Send</SfButton>
                                <SfButton>Discard</SfButton>
                            </div>
                        </div>
                    </div>
                </div>
            </ContentTemplate>
        </SplitterPane>
    </SplitterPanes>
</SfSplitter>

```

**Step 2** :

Place the `TreeViewTemplates` inside the `SfTreeView` to render the treeview template.

```csharp

<TreeViewTemplates>
    <NodeTemplate>
        <div>
            <div class="treeviewdiv">
                <div style="float:left">
                    <span class="treeName">@((context as TreeData).Name)</span>
                </div>
                @{
                    @if (((context as TreeData).Count) != 0)
                    {
                        <div style="margin-right: 5px; float:right">
                            <span class="treeCount e-badge e-badge-primary">@((context as TreeData).Count)</span>
                        </div>
                    }
                }
            </div>
        </div>
    </NodeTemplate>
</TreeViewTemplates>

```

**Step 3** :

Define the components DataSource in `@code` section.

```csharp

@code {
    private SfRichTextEditor RichTextEditorObj;
    private List<TreeData> localData = new List<TreeData>() {
        new TreeData { Id = 1, Name = "Favorites",  HasChild = true, },
        new TreeData { Id = 2, Pid = 1,  Name = "Sales Reports",  Count = 4 },
        new TreeData { Id = 3, Pid = 1, Name = "Sent Items" },
        new TreeData { Id = 4, Pid = 1, Name = "Marketing Reports", Count = 6 },
        new TreeData { Id = 5, HasChild = true, Name = "Andrew Fuller", Expanded = true },
        new TreeData { Id = 6, Pid = 5, Name = "Inbox", Selected = true, Count = 20 },
        new TreeData { Id = 7, Pid = 5, Name = "Drafts", Count = 5 },
        new TreeData { Id = 8, Pid = 5, Name = "Deleted Items" },
        new TreeData { Id = 9, Pid = 5, Name = "Sent Items"  },
        new TreeData { Id = 10, Pid = 5, Name = "Sales Reports", Count = 4 },
        new TreeData { Id = 11, Pid = 5, Name = "Marketing Reports", Count = 6 },
        new TreeData { Id = 12, Pid = 5, Name = "Outbox" },
        new TreeData { Id = 13, Pid = 5, Name = "Junk Email" },
        new TreeData { Id = 14, Pid = 5, Name = "RSS Feed" },
        new TreeData { Id = 15, Pid = 5, Name = "Trash" }
    };
    public TreeData ModelType = new TreeData();

    private List<DataModel> dataSource = new List<DataModel>()
    {
         new DataModel { Name= "Selma Tally", Content1="Apology marketing email", Content2="Hello Ananya Singleton", Id = "1", Order = 0},
        new DataModel { Name= "Illa Russo", Content1="Annual conference", Content2="Hi jeani Moresa", Id = "4", Order = 0},
        new DataModel { Name= "Camden Macmellon", Content1="Reference request- Camden hester", Content2="Hello Kerry Best", Id = "3", Order = 0},
        new DataModel { Name= "Garth Owen", Content1="Application for job Title", Content2="Hello Illa Russo", Id = "2", Order = 0},
        new DataModel { Name= "Ursula Patterson", Content1="Programmaer Position Applicant", Content2="Hello Kerry best", Id = "5", Order = 0},
    };

    private DataModel model = new DataModel();

    public class DataModel
    {
        public string Name { get; set; }
        public string Content1 { get; set; }
        public string Content2 { get; set; }
        public string Id { get; set; }
        public int Order { get; set; }
    }
    public class TreeData
    {
        public int Id { get; set; }
        public int? Pid { get; set; }
        public string Name { get; set; }
        public bool HasChild { get; set; }
        public bool Expanded { get; set; }
        public int Count { get; set; }
        public bool Selected { get; set; }
    }
    public void resizeStop()
    {
        this.RichTextEditorObj.Refresh();
    }
    public void Created()
    {
        this.RichTextEditorObj.Refresh();
    }
}

```

```bash

<style>
    #target {
        margin: 20px auto;
        max-width: 820px;
    }
    .e-treeview .e-list-text {
        width: 100%;
    }
    .grouped-list.e-listview .e-list-group-item {
        height: 0;
    }
    .splitter-layout .settings.e-list-wrapper.e-list-multi-line.e-list-avatar {
        padding: 15px;
    }
    #buttonSection {
        padding: 7px;
    }
</style>

```

Once the above configurations has been completed, you will get the output like [this](https://blazor.syncfusion.com/demos/splitter/outlook?theme=bootstrap4).

## See Also

* [Multiple panes in Splitter](./split-panes/)
