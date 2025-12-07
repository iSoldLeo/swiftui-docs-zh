--- 来源：https://developer.apple.com/documentation/SwiftUI/ImageRenderer
抓取时间：2025-12-02T17:35:58Z

---

# ImageRenderer

**Class**

一个用于从 SwiftUI 视图创建图像的对象。

## 声明

```swift
final class ImageRenderer<Content> where Content : View
```

## 概述

使用 `ImageRenderer` 从 SwiftUI 视图导出位图图像数据。您可以使用视图初始化渲染器，然后按需渲染图像，方法是调用 [render(rasterizationScale:renderer:)](ImageRenderer/render_rasterizationScale_renderer.zh-Hans.md) 方法，或者使用渲染器的属性创建 [doc://com.apple.documentation/documentation/CoreGraphics/CGImage]、[doc://com.apple.documentation/documentation/AppKit/NSImage] 或 [doc://com.apple.documentation/documentation/UIKit/UIImage]。

通过绘制到 [Canvas](Canvas.zh-Hans.md) 并使用 `ImageRenderer` 导出，您可以从任何程序渲染的内容（例如路径、形状、渐变等）生成图像。您还可以渲染标准的 SwiftUI 视图，例如 [Text](Text.zh-Hans.md) 视图，或包含多种视图类型的容器。

以下示例使用私有方法 `createAwardView(forUser:date:)` 创建游戏应用中奖杯图标的视图，其中包含用户名和日期。此视图将应用阴影滤镜的 [Canvas](Canvas.zh-Hans.md) 与两个 [Text](Text.zh-Hans.md) 视图合并到 [VStack](VStack.zh-Hans.md) 中。[Button](Button.zh-Hans.md) 允许用户保存此视图。按钮的操作使用 `ImageRenderer` 对 `CGImage` 进行栅格化，然后调用私有方法 `uploadAchievementImage(_:)` 对图像进行编码并上传。

```swift
var body: some View {
    let trophyAndDate = createAwardView(forUser: playerName,
                                         date: achievementDate)
    VStack {
        trophyAndDate
        Button("Save Achievement") {
            let renderer = ImageRenderer(content: trophyAndDate)
            if let image = renderer.cgImage {
                uploadAchievementImage(image)
            }
        }
    }
}

private func createAwardView(forUser: String, date: Date) -> some View {
    VStack {
        Image(systemName: "trophy")
            .resizable()
            .frame(width: 200, height: 200)
            .frame(maxWidth: .infinity, maxHeight: .infinity)
            .shadow(color: .mint, radius: 5)
        Text(playerName)
            .font(.largeTitle)
        Text(achievementDate.formatted())
    }
    .multilineTextAlignment(.center)
    .frame(width: 200, height: 290)
}
```

由于 `ImageRenderer` 符合 [doc://com.apple.documentation/documentation/Combine/ObservableObject] 规范，因此您可以利用它在属性更改时生成图像流。订阅渲染器的 [objectWillChange](ImageRenderer/objectWillChange.zh-Hans.md) 发布者，然后在订阅者每次收到更新时，使用渲染器栅格化新图像。

### 渲染到 PDF 上下文

[render(rasterizationScale:renderer:)](ImageRenderer/render_rasterizationScale_renderer.zh-Hans.md) 方法将指定的视图渲染到任何 [doc://com.apple.documentation/documentation/CoreGraphics/CGContext] 上下文。这意味着您不仅限于创建栅格化的 `CGImage`。例如，您可以通过渲染到 PDF 上下文来生成 PDF 数据。生成的 PDF 文件对于视图层次结构中受支持的成员（例如文本、符号图像、线条、形状和填充）保持分辨率无关性。

以下示例使用上一个示例中的 `createAwardView(forUser:date:)` 方法，并将其内容导出为 800 x 600 点的 PDF 文件，文件 URL 为 `renderURL`。它使用发送到渲染闭包的 `size` 参数，将 `trophyAndDate` 视图在页面上垂直和水平居中。

```swift
var body: some View {
    let trophyAndDate = createAwardView(forUser: playerName,
                                        date: achievementDate)
    VStack {
        trophyAndDate
        Button("Save Achievement") {
            let renderer = ImageRenderer(content: trophyAndDate)
            renderer.render { size, renderer in
                var mediaBox = CGRect(origin: .zero,
                                      size: CGSize(width: 800, height: 600))
                guard let consumer = CGDataConsumer(url: renderURL as CFURL),
                      let pdfContext =  CGContext(consumer: consumer,
                                                  mediaBox: &mediaBox, nil)
                else {
                    return
                }
                pdfContext.beginPDFPage(nil)
                pdfContext.translateBy(x: mediaBox.size.width / 2 - size.width / 2,
                                       y: mediaBox.size.height / 2 - size.height / 2)
                renderer(pdfContext)
                pdfContext.endPDFPage()
                pdfContext.closePDF()
            }
        }
    }
}
```

### 根据绘图指令创建图像

`ImageRenderer` 允许您通过在 [Canvas](Canvas.zh-Hans.md) 中绘制图形来创建自定义图像，然后从中渲染 `CGImage`，并使用该渲染结果初始化 [Image](Image.zh-Hans.md)。为了简化此过程，请使用 `Image` 初始化器 [init(size:label:opaque:colorMode:renderer:)](Image/init_size_label_opaque_colorMode_renderer.zh-Hans.md)，它接受一个闭包，该闭包的参数是一个 [GraphicsContext](GraphicsContext.zh-Hans.md)，您可以直接在其中绘制图形。

## 创建图像渲染器

- **init(content:)**：创建一个带有源内容视图的渲染器对象。

## 提供源视图

- **content**：此图像渲染器渲染的根视图。

## 访问渲染器属性

- **proposedSize**：建议根视图的大小。

- **scale**：图像的渲染比例。

- **isOpaque**：一个布尔值，指示图像的 Alpha 通道是否完全不透明。

- **colorMode**：图像的工作色彩空间和存储格式。

- **allowedDynamicRange**：图像允许的动态范围，如果设置为 nil 则表示图像的动态范围不受限制。此属性默认为 `sdr`，即 HDR 内容将被色调映射到 SDR。

## 渲染图像

- **render(rasterizationScale:renderer:)**：将渲染器的当前内容绘制到任意 Core Graphics 上下文中。

- **cgImage**：视图的当前内容，以 Core Graphics 图像格式栅格化。

- **nsImage**：视图的当前内容，以 AppKit 图像格式栅格化。

- **uiImage**：视图的当前内容，以 UIKit 图像格式栅格化。

## 生成图像流

- **objectWillChange**：用于通知订阅者图像更改的发布者。

- **isObservationEnabled**：是否应在生成的图像更改时通知此被观察对象的观察者。

## 符合以下标准

- Copyable

- Observable

- ObservableObject


---
source: https://developer.apple.com/documentation/SwiftUI/ImageRenderer
crawled: 2025-12-02T17:35:58Z
---

# ImageRenderer

**Class**

An object that creates images from SwiftUI views.

## Declaration

```swift
final class ImageRenderer<Content> where Content : View
```

## Overview

Use `ImageRenderer` to export bitmap image data from a SwiftUI view. You initialize the renderer with a view, then render images on demand, either by calling the [render(rasterizationScale:renderer:)](ImageRenderer/render_rasterizationScale_renderer.zh-Hans.md) method, or by using the renderer’s properties to create a [doc://com.apple.documentation/documentation/CoreGraphics/CGImage], [doc://com.apple.documentation/documentation/AppKit/NSImage], or [doc://com.apple.documentation/documentation/UIKit/UIImage].

By drawing to a [Canvas](Canvas.zh-Hans.md) and exporting with an `ImageRenderer`, you can generate images from any progammatically-rendered content, like paths, shapes, gradients, and more. You can also render standard SwiftUI views like [Text](Text.zh-Hans.md) views, or containers of multiple view types.

The following example uses a private `createAwardView(forUser:date:)` method to create a game app’s view of a trophy symbol with a user name and date. This view combines a [Canvas](Canvas.zh-Hans.md) that applies a shadow filter with two [Text](Text.zh-Hans.md) views into a [VStack](VStack.zh-Hans.md). A [Button](Button.zh-Hans.md) allows the person to save this view. The button’s action uses an `ImageRenderer` to rasterize a `CGImage` and then calls a private `uploadAchievementImage(_:)` method to encode and upload the image.

```swift
var body: some View {
    let trophyAndDate = createAwardView(forUser: playerName,
                                         date: achievementDate)
    VStack {
        trophyAndDate
        Button("Save Achievement") {
            let renderer = ImageRenderer(content: trophyAndDate)
            if let image = renderer.cgImage {
                uploadAchievementImage(image)
            }
        }
    }
}

private func createAwardView(forUser: String, date: Date) -> some View {
    VStack {
        Image(systemName: "trophy")
            .resizable()
            .frame(width: 200, height: 200)
            .frame(maxWidth: .infinity, maxHeight: .infinity)
            .shadow(color: .mint, radius: 5)
        Text(playerName)
            .font(.largeTitle)
        Text(achievementDate.formatted())
    }
    .multilineTextAlignment(.center)
    .frame(width: 200, height: 290)
}
```



Because `ImageRenderer` conforms to [doc://com.apple.documentation/documentation/Combine/ObservableObject], you can use it to produce a stream of images as its properties change. Subscribe to the renderer’s [objectWillChange](ImageRenderer/objectWillChange.zh-Hans.md) publisher, then use the renderer to rasterize a new image each time the subscriber receives an update.



### Rendering to a PDF context

The [render(rasterizationScale:renderer:)](ImageRenderer/render_rasterizationScale_renderer.zh-Hans.md) method renders the specified view to any [doc://com.apple.documentation/documentation/CoreGraphics/CGContext]. That means you aren’t limited to creating a rasterized `CGImage`. For example, you can generate PDF data by rendering to a PDF context. The resulting PDF maintains resolution-independence for supported members of the view hierarchy, such as text, symbol images, lines, shapes, and fills.

The following example uses the `createAwardView(forUser:date:)` method from the previous example, and exports its contents as an 800-by-600 point PDF to the file URL `renderURL`. It uses the `size` parameter sent to the rendering closure to center the `trophyAndDate` view vertically and horizontally on the page.

```swift
var body: some View {
    let trophyAndDate = createAwardView(forUser: playerName,
                                        date: achievementDate)
    VStack {
        trophyAndDate
        Button("Save Achievement") {
            let renderer = ImageRenderer(content: trophyAndDate)
            renderer.render { size, renderer in
                var mediaBox = CGRect(origin: .zero,
                                      size: CGSize(width: 800, height: 600))
                guard let consumer = CGDataConsumer(url: renderURL as CFURL),
                      let pdfContext =  CGContext(consumer: consumer,
                                                  mediaBox: &mediaBox, nil)
                else {
                    return
                }
                pdfContext.beginPDFPage(nil)
                pdfContext.translateBy(x: mediaBox.size.width / 2 - size.width / 2,
                                       y: mediaBox.size.height / 2 - size.height / 2)
                renderer(pdfContext)
                pdfContext.endPDFPage()
                pdfContext.closePDF()
            }
        }
    }
}
```

### Creating an image from drawing instructions

`ImageRenderer` makes it possible to create a custom image by drawing into a [Canvas](Canvas.zh-Hans.md), rendering a `CGImage` from it, and using that to initialize an [Image](Image.zh-Hans.md). To simplify this process, use the `Image` initializer [init(size:label:opaque:colorMode:renderer:)](Image/init_size_label_opaque_colorMode_renderer.zh-Hans.md), which takes a closure whose argument is a [GraphicsContext](GraphicsContext.zh-Hans.md) that you can directly draw into.

## Creating an image renderer

- **init(content:)**: Creates a renderer object with a source content view.

## Providing the source view

- **content**: The root view rendered by this image renderer.

## Accessing renderer properties

- **proposedSize**: The size proposed to the root view.
- **scale**: The scale at which to render the image.
- **isOpaque**: A Boolean value that indicates whether the alpha channel of the image is fully opaque.
- **colorMode**: The working color space and storage format of the image.
- **allowedDynamicRange**: The allowed dynamic range of the image, or nil to mark that the dynamic range of the image should be unrestricted. This property defaults to `sdr`, i.e. HDR content will be tone mapped to SDR.

## Rendering images

- **render(rasterizationScale:renderer:)**: Draws the renderer’s current contents to an arbitrary Core Graphics context.
- **cgImage**: The current contents of the view, rasterized as a Core Graphics image.
- **nsImage**: The current contents of the view, rasterized as an AppKit image.
- **uiImage**: The current contents of the view, rasterized as a UIKit image.

## Producing a stream of images

- **objectWillChange**: A publisher that informs subscribers of changes to the image.
- **isObservationEnabled**: If observers of this observed object should be notified when the produced image changes.

## Conforms To

- Copyable
- Observable
- ObservableObject

