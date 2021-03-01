---
title: "Restrict Editing"
component: "Word processor"
description: "Learn how to find a text in Blazor Word processor and replace it with another text."
---

# Restrict editing

This Word processor control (DocumentEditor) provides 2 types of restriction for editing:
* Read-only: Allows all the users to view the document contents but not make changes to it.
* Allows changes to certain portion of the document: Allows the users to edit to certain portion of the document.

## Read only

The following code example shows how to restrict or protect editing for the entire content (show as read-only).

```csharp
@using Syncfusion.Blazor.DocumentEditor

<button @onclick="ReadOnly">Read Only</button>
<SfDocumentEditorContainer @ref="container" EnableToolbar=true></SfDocumentEditorContainer>

@code {
    SfDocumentEditorContainer container;

    public void ReadOnly(object args)
    {
        container.RestrictEditing = true;
    }
}
```

## Allows changes to certain portion of the document

Also, at some situations, you might need to allow changes for a certain portion of the document alone. Microsoft Word allows you to [make changes to parts of a Word document](https://support.office.com/en-gb/article/allow-changes-to-parts-of-a-protected-document-187ed01c-8795-43e1-9fd0-c9fca419dadf). Likewise, the document editor control allows the users to make changes to certain parts of a document using similar user interface.

![Restrict Editing](./images/protection-enforced.png)

![Restrict Editing Enabled](./images/protection-not-enforced.png)
