---
来源： https://developer.apple.com/documentation/swiftui/image
抓取时间： 2025-12-04T03:35:41Z
---

# 图像

**Structure**

显示图像的视图。

## 声明

```swift
@frozen struct Image
```

## 概览

要在 SwiftUI 应用程序中添加图片时，请使用 `Image` 实例。您可以从多种来源创建图片：

- 应用程序资产库或捆绑包中的图像文件。支持的类型包括 PNG、JPEG、HEIC 等。
- 平台特定图像类型的实例，如 [doc://com.apple.documentation/documentation/UIKit/UIImage] 和 [doc://com.apple.documentation/documentation/AppKit/NSImage]。
- 存储在 Core Graphics [doc://com.apple.documentation/documentation/CoreGraphics/CGImage] 实例中的位图。
- SF 符号集中的系统图形。

下面的示例显示了如何从应用程序的资产库或捆绑包中加载图像，并将其缩放以适合其容器：

```swift
Image("Landscape_4")
    .resizable()
    .aspectRatio(contentMode: .fit)
Text("Water wheel")
```



您可以使用`Image` 类型上的方法以及标准视图修改器来调整图片大小，以适应您应用程序的界面。在这里，`Image` 类型的[resizable(capInsets:resizingMode:)](Image/resizable_capInsets_resizingMode.zh-Hans.md) 方法会缩放图像以适应当前视图。然后，[aspectRatio(_:contentMode:)](View/aspectRatio___contentMode.zh-Hans.md) 视图修改器会调整这种大小调整行为，以保持图像的原始纵横比，而不是独立缩放 x 轴和 y 轴以填充视图的所有四边。文章[Fitting-Images-into-Available-Space](Fitting-Images-into-Available-Space.zh-Hans.md) 展示了如何对不同大小的`Image` 实例应用缩放、剪切和平铺。

`Image`是一个后期绑定标记；系统只有在即将在环境中使用图像时才会解析其实际值。

### 获取图像

要将图像用作控件，请使用其中一个包含`label`参数的初始化程序。这样，对于使用 VoiceOver 等功能的用户，系统的辅助功能框架就可以使用标签作为控件的名称。如果图像只是为了美观而出现，则使用带有`decorative`参数的初始化器；辅助功能系统会忽略这些图像。

## 创建图像

- **init(_:bundle:)**：创建带标签的图像，用作控件的内容。
- **init(_:variableValue:bundle:)**：创建带标签的图像，您可以将其用作控件的内容，并带有一个可变值。
- **init(_:)**：使用图像资源初始化`Image`。

## 创建用作控件的图像

- **init(_:bundle:label:)**：创建带标签的图像，您可以将其用作控件的内容，并带有指定的标签。
- **init(_:variableValue:bundle:label:)**：创建一个带标签的图像，可用作控件的内容，并带有指定的标签和变量值。
- **init(_:scale:orientation:label:)**：根据 Core Graphics 图像实例创建标签图像，可用作控件的内容。

## 创建装饰用图像

- **init(decorative:bundle:)**：创建一个无标记的装饰性图像。
- **init(decorative:variableValue:bundle:)**：创建一个无标记的装饰图像，图像值可变。
- **init(decorative:scale:orientation:)**：根据 Core Graphics 图像实例创建无标记的装饰图像。

## 创建系统符号图像

- **init(systemName:)**：创建系统符号图像。
- **init(systemName:variableValue:)**：创建带有变量值的系统符号图像。

## 从另一个图像创建图像

- **init(uiImage:)**：从 UIKit 图像实例创建 SwiftUI 图像。
- **init(nsImage:)**：从 AppKit 图像实例创建 SwiftUI 图像。

## 从绘图指令创建图像

- **init(size:label:opaque:colorMode:renderer:)**：初始化指定大小的图像，图像内容由自定义渲染闭包提供。

## 调整图像大小

- **resizable(capInsets:resizingMode:)**：设置 SwiftUI 调整图像大小以适应其空间的模式。

## 指定渲染行为

- **antialiased(_:)**：指定 SwiftUI 在渲染图像时是否应用抗锯齿。
- **symbolRenderingMode(_:)**：设置此视图中符号图像的渲染模式。
- **renderingMode(_:)**：表示 SwiftUI 是按原样还是使用其他模式渲染图像。
- **interpolation(_:)**：指定渲染需要插值的图像时的当前质量级别。
- **Image.TemplateRenderingMode**：表示 SwiftUI 如何渲染图像的类型。
- **Image.Interpolation**：用于渲染需要插值的图像（如缩放图像）的质量级别。

## 指定动态范围

- **allowedDynamicRange(_:)**：以指定的允许动态范围返回新配置的图像。
- **allowedDynamicRange**：视图允许的动态范围，或为零。
- **Image.DynamicRange**：视图的允许动态范围。

## 实例方法

- **symbolColorRenderingMode(_:)**：设置图像的色彩渲染模式。
- **symbolVariableValueMode(_:)**：设置此视图中符号图像的变值模式模式。
- **widgetAccentedRenderingMode(_:)**：指定使用`Image` 模式时如何渲染`WidgetKit/WidgetRenderingMode/accented`。

## 枚举

- **Image.Orientation**：图像的方向。
- **Image.ResizingMode**：SwiftUI 用来调整图像大小以适合其包含的视图的模式。
- **Image.Scale**：相对于文本应用于矢量图像的比例。

## 符合

- 可复制
- 等价
- 日志建议资产
- 可发送
- 可发送元类型
- 可转移
- 查看


---
source: https://developer.apple.com/documentation/swiftui/image
crawled: 2025-12-04T03:35:41Z
---

# Image

**Structure**

A view that displays an image.

## Declaration

```swift
@frozen struct Image
```

## Overview

Use an `Image` instance when you want to add images to your SwiftUI app. You can create images from many sources:

- Image files in your app’s asset library or bundle. Supported types include PNG, JPEG, HEIC, and more.
- Instances of platform-specific image types, like [doc://com.apple.documentation/documentation/UIKit/UIImage] and [doc://com.apple.documentation/documentation/AppKit/NSImage].
- A bitmap stored in a Core Graphics [doc://com.apple.documentation/documentation/CoreGraphics/CGImage] instance.
- System graphics from the SF Symbols set.

The following example shows how to load an image from the app’s asset library or bundle and scale it to fit within its container:

```swift
Image("Landscape_4")
    .resizable()
    .aspectRatio(contentMode: .fit)
Text("Water wheel")
```



You can use methods on the `Image` type as well as standard view modifiers to adjust the size of the image to fit your app’s interface. Here, the `Image` type’s [resizable(capInsets:resizingMode:)](Image/resizable_capInsets_resizingMode.zh-Hans.md) method scales the image to fit the current view. Then, the [aspectRatio(_:contentMode:)](View/aspectRatio___contentMode.zh-Hans.md) view modifier adjusts this resizing behavior to maintain the image’s original aspect ratio, rather than scaling the x- and y-axes independently to fill all four sides of the view. The article [Fitting-Images-into-Available-Space](Fitting-Images-into-Available-Space.zh-Hans.md) shows how to apply scaling, clipping, and tiling to `Image` instances of different sizes.

An `Image` is a late-binding token; the system resolves its actual value only when it’s about to use the image in an environment.

### Making images accessible

To use an image as a control, use one of the initializers that takes a `label` parameter. This allows the system’s accessibility frameworks to use the label as the name of the control for users who use features like VoiceOver. For images that are only present for aesthetic reasons, use an initializer with the `decorative` parameter; the accessibility systems ignore these images.

## Creating an image

- **init(_:bundle:)**: Creates a labeled image that you can use as content for controls.
- **init(_:variableValue:bundle:)**: Creates a labeled image that you can use as content for controls, with a variable value.
- **init(_:)**: Initialize an `Image` with an image resource.

## Creating an image for use as a control

- **init(_:bundle:label:)**: Creates a labeled image that you can use as content for controls, with the specified label.
- **init(_:variableValue:bundle:label:)**: Creates a labeled image that you can use as content for controls, with the specified label and variable value.
- **init(_:scale:orientation:label:)**: Creates a labeled image based on a Core Graphics image instance, usable as content for controls.

## Creating an image for decorative use

- **init(decorative:bundle:)**: Creates an unlabeled, decorative image.
- **init(decorative:variableValue:bundle:)**: Creates an unlabeled, decorative image, with a variable value.
- **init(decorative:scale:orientation:)**: Creates an unlabeled, decorative image based on a Core Graphics image instance.

## Creating a system symbol image

- **init(systemName:)**: Creates a system symbol image.
- **init(systemName:variableValue:)**: Creates a system symbol image with a variable value.

## Creating an image from another image

- **init(uiImage:)**: Creates a SwiftUI image from a UIKit image instance.
- **init(nsImage:)**: Creates a SwiftUI image from an AppKit image instance.

## Creating an image from drawing instructions

- **init(size:label:opaque:colorMode:renderer:)**: Initializes an image of the given size, with contents provided by a custom rendering closure.

## Resizing images

- **resizable(capInsets:resizingMode:)**: Sets the mode by which SwiftUI resizes an image to fit its space.

## Specifying rendering behavior

- **antialiased(_:)**: Specifies whether SwiftUI applies antialiasing when rendering the image.
- **symbolRenderingMode(_:)**: Sets the rendering mode for symbol images within this view.
- **renderingMode(_:)**: Indicates whether SwiftUI renders an image as-is, or by using a different mode.
- **interpolation(_:)**: Specifies the current level of quality for rendering an image that requires interpolation.
- **Image.TemplateRenderingMode**: A type that indicates how SwiftUI renders images.
- **Image.Interpolation**: The level of quality for rendering an image that requires interpolation, such as a scaled image.

## Specifying dynamic range

- **allowedDynamicRange(_:)**: Returns a new image configured with the specified allowed dynamic range.
- **allowedDynamicRange**: The allowed dynamic range for the view, or nil.
- **Image.DynamicRange**

## Instance Methods

- **symbolColorRenderingMode(_:)**: Sets the color rendering mode of the image.
- **symbolVariableValueMode(_:)**: Sets the variable value mode mode for symbol images within this view.
- **widgetAccentedRenderingMode(_:)**: Specifies the how to render an `Image` when using the `WidgetKit/WidgetRenderingMode/accented` mode.

## Enumerations

- **Image.Orientation**: The orientation of an image.
- **Image.ResizingMode**: The modes that SwiftUI uses to resize an image to fit within its containing view.
- **Image.Scale**: A scale to apply to vector images relative to text.

## Conforms To

- Copyable
- Equatable
- JournalingSuggestionAsset
- Sendable
- SendableMetatype
- Transferable
- View

