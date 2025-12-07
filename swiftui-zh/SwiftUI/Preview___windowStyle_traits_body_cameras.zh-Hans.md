---
源：https://developer.apple.com/documentation/SwiftUI/Preview(_:windowStyle:traits:body:cameras:)
抓取时间：2025-12-02T17:45:55Z
---

# Preview(_:windowStyle:traits:body:cameras:)

**Macro**

在带有自定义视点的窗口中创建 SwiftUI 视图的预览。

## 声明

```swift
@freestanding(declaration) macro Preview<Style>(_ name: String? = nil, windowStyle: Style, traits: PreviewTrait<Preview.ViewTraits>..., @ViewBuilder body: @escaping @MainActor () -> any View, @PreviewCameraBuilder cameras: () -> [PreviewCamera]) where Style : WindowStyle
```

## 参数

- **name**：预览的可选显示名称。如果不指定名称，canvas 会使用预览在源文件中出现的行号来标注预览。
- **windowStyle**：用于预览的[WindowStyle](WindowStyle.zh-Hans.md)。使用此输入可将视图显示为具有指定样式的窗口。
- **traits**：自定义预览外观的[doc://com.apple.documentation/documentation/DeveloperToolsSupport/PreviewTrait] 实例的可选列表。
- **body**：用于生成 SwiftUI 视图以进行预览的[ViewBuilder](ViewBuilder.zh-Hans.md)。您通常会指定应用程序的一个自定义视图，并可选择指定自定义视图正常运行所需的任何输入、模型数据、修改器和外层视图。
- **cameras**：一个或多个预览摄像机，表示您希望能够查看预览的自定义固定视点。其中第一个视点将取代前视点作为默认视点。

### 概览

此预览宏与[Preview(_:windowStyle:traits:body:)](Preview___windowStyle_traits_body.zh-Hans.md) 和[Preview(_:traits:body:cameras:)](Preview___traits_body_cameras.zh-Hans.md) 的作用类似：它可以让您为视图定义窗口场景上下文，也可以为预览定义自定义的固定视点：

```swift
#Preview("Volume", windowStyle: .volumetric) {
   ContentView()
} cameras: {
   PreviewCamera(from: .front)
   PreviewCamera(from: .top, zoom: 2)
   PreviewCamera(from: .leading, zoom: 0.5, name: "close up")
}
```

有关在预览中使用场景和摄像机的更多信息，请参阅其他预览宏。如果您想在身临其境的空间而非窗口中预览，请使用 [Preview(_:immersionStyle:traits:body:cameras:)](Preview___immersionStyle_traits_body_cameras.zh-Hans.md)。

## 在场景中创建预览

- **Preview(_:immersionStyle:traits:body:)**：在沉浸式空间中创建 SwiftUI 视图预览。
- **Preview(_:immersionStyle:traits:body:cameras:)**：在具有自定义视点的沉浸式空间中创建 SwiftUI 视图的预览。
- **Preview(_:windowStyle:traits:body:)**：在窗口中创建 SwiftUI 视图的预览。


---
source: https://developer.apple.com/documentation/SwiftUI/Preview(_:windowStyle:traits:body:cameras:)
crawled: 2025-12-02T17:45:55Z
---

# Preview(_:windowStyle:traits:body:cameras:)

**Macro**

Creates a preview of a SwiftUI view in a window with custom viewpoints.

## Declaration

```swift
@freestanding(declaration) macro Preview<Style>(_ name: String? = nil, windowStyle: Style, traits: PreviewTrait<Preview.ViewTraits>..., @ViewBuilder body: @escaping @MainActor () -> any View, @PreviewCameraBuilder cameras: () -> [PreviewCamera]) where Style : WindowStyle
```

## Parameters

- **name**: An optional display name for the preview. If you don’t specify a name, the canvas labels the preview using the line number where the preview appears in source.
- **windowStyle**: The [WindowStyle](WindowStyle.zh-Hans.md) to use for the preview. Use this input to display the view as if it appears in a window that has the specified style.
- **traits**: An optional list of [doc://com.apple.documentation/documentation/DeveloperToolsSupport/PreviewTrait] instances that customize the appearance of the preview.
- **body**: A [ViewBuilder](ViewBuilder.zh-Hans.md) that produces a SwiftUI view to preview. You typically specify one of your app’s custom views and optionally any inputs, model data, modifiers, and enclosing views that the custom view needs for normal operation.
- **cameras**: One or more preview cameras that indicate the custom, fixed viewpoints that you want to be able to view the preview from. The first of these replaces the front viewpoint as the default.

## Overview

This preview macro behaves like [Preview(_:windowStyle:traits:body:)](Preview___windowStyle_traits_body.zh-Hans.md) combined with [Preview(_:traits:body:cameras:)](Preview___traits_body_cameras.zh-Hans.md): it enables you to define a window scene context for the view, and also to define custom, fixed viewpoints for the preview:

```swift
#Preview("Volume", windowStyle: .volumetric) {
   ContentView()
} cameras: {
   PreviewCamera(from: .front)
   PreviewCamera(from: .top, zoom: 2)
   PreviewCamera(from: .leading, zoom: 0.5, name: "close up")
}
```

See those other preview macros for more information about using scenes and cameras in your preview. If you want to preview in an immersive space rather than a window, use [Preview(_:immersionStyle:traits:body:cameras:)](Preview___immersionStyle_traits_body_cameras.zh-Hans.md).

## Creating a preview in the context of a scene

- **Preview(_:immersionStyle:traits:body:)**: Creates a preview of a SwiftUI view in an immersive space.
- **Preview(_:immersionStyle:traits:body:cameras:)**: Creates a preview of a SwiftUI view in an immersive space with custom viewpoints.
- **Preview(_:windowStyle:traits:body:)**: Creates a preview of a SwiftUI view in a window.

