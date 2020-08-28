---
title: " Rich text editor restricts the image uploading while uploading with large size"
component: "Rich Text Editor"
description: "This section for Syncfusion Blazor Rich Text Editor control explains about, how to restrict the image to upload, when the given image size is greater than the allowed size"
---

# Restrict the image uploading while uploading with large size

By using the Rich text editor's `OnImageUploading` event, you can get the image size before uploading and restrict the image to upload, when the given image size is greater than the allowed size.

In the following, we have validated the image size before uploading and determined whether the image has been uploaded or not.

 ```csharp

@using Syncfusion.Blazor.RichTextEditor

<SfRichTextEditor>
    <RichTextEditorImageSettings SaveUrl="https://aspnetmvc.syncfusion.com/services/api/uploadbox/Save" Path="./Images/"></RichTextEditorImageSettings>
    <RichTextEditorEvents OnImageUploading="@ImageUploading"> </RichTextEditorEvents>
</SfRichTextEditor>

@code {

    private void ImageUploading(ImageUploadingEventArgs args)
    {
        var sizeInBytes = args.FileData[0].Size;
        var imgSize = 500000;
        if (imgSize < sizeInBytes) {
            args.Cancel = true;
        }

}
}