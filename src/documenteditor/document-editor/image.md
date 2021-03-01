---
title: "Images"
component: "Word processor"
description: "Learn the supported image types in Blazor Word processor and how to insert, resize, format images."
---

# Images

Document editor supports common raster format images like PNG, BMP, JPEG, and GIF. You can insert an image file or online image in the document using the `InsertImage()` method.

```javascript
documentEditor.GetEditor().InsertImage("<<base64String>>");
```

Image files will be internally converted to base64 string. Whereas, online images are preserved as URL.

## Image resizing

Document editor provides built-in image resizer that can be injected into your application based on the requirements. This allows you to resize the image by dragging the resizing points using mouse or touch interactions. This resizer appears as follows.

![Image](images/image.jpeg)

## Changing size

Document editor expose API to get or resize the selected image. Refer to the following sample code.

```javascript
int height = await documentEditor.GetSelection().GetImageFormat().GetHeight();
int width = await documentEditor.GetSelection().GetImageFormat().GetWidth();
documentEditor.GetSelection().GetImageFormat().Resize(width + 10, height + 10);
```
