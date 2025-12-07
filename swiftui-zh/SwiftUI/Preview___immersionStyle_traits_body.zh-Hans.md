---
来源：https://developer.apple.com/documentation/SwiftUI/Preview(_:immersionStyle:traits:body:)
抓取时间：2025-11-30T21:30:50Z
---

# Preview(_:immersionStyle:traits:body:)

**Macro**

在沉浸式空间中创建 SwiftUI 视图的预览。

## 声明

```swift
@freestanding(declaration) macro Preview<Style>(_ name: String? = nil, immersionStyle: Style, traits: PreviewTrait<Preview.ViewTraits>..., @ViewBuilder body: @escaping @MainActor () -> any View) where Style : ImmersionStyle
```

## 参数

- **name**：预览的可选显示名称。如果不指定名称，canvas 会使用预览在源文件中出现的行号来标注预览。
- **immersionStyle**：用于预览的[ImmersionStyle](ImmersionStyle.zh-Hans.md)。使用此输入可将视图显示为具有指定样式的沉浸式空间中的视图。
- **traits**：自定义预览外观的[doc://com.apple.documentation/documentation/DeveloperToolsSupport/PreviewTrait] 实例的可选列表。
- **body**：用于生成 SwiftUI 视图以进行预览的[ViewBuilder](ViewBuilder.zh-Hans.md)。您通常会指定应用程序的一个自定义视图，并可选择指定自定义视图正常运行所需的任何输入、模型数据、修改器和外层视图。

### 概览

此预览宏的行为与[Preview(_:traits:_:body:)](Preview___traits___body.zh-Hans.md)相似，但它还能让您为视图定义场景上下文。具体来说，它会将视图放置在一个具有指定沉浸样式的沉浸空间中，就像[mixed](ImmersionStyle/mixed.zh-Hans.md)样式一样：

```swift
#Preview("Mixed immersive space", immersionStyle: .mixed) {
   ContentView()
}
```样式

当视图需要场景上下文才能像应用程序正常运行时那样运行时，请使用此预览宏。

其他预览宏提供不同的自定义选项。例如，如果您想查看视图在窗口而非沉浸式空间中的显示效果，可以使用 [Preview(_:windowStyle:traits:body:)](Preview___windowStyle_traits_body.zh-Hans.md)。如果想在沉浸式空间预览中添加自定义的固定视点，请使用 [Preview(_:immersionStyle:traits:body:cameras:)](Preview___immersionStyle_traits_body_cameras.zh-Hans.md)。

## 在场景中创建预览

- **Preview(_:immersionStyle:traits:body:cameras:)**：在具有自定义视点的沉浸式空间中创建 SwiftUI 视图预览。
- **Preview(_:windowStyle:traits:body:)**：在窗口中创建 SwiftUI 视图的预览。
- **Preview(_:windowStyle:traits:body:cameras:)**：在带有自定义视点的窗口中创建 SwiftUI 视图的预览。


---
source: https://developer.apple.com/documentation/SwiftUI/Preview(_:immersionStyle:traits:body:)
crawled: 2025-11-30T21:30:50Z
---

# Preview(_:immersionStyle:traits:body:)

**Macro**

Creates a preview of a SwiftUI view in an immersive space.

## Declaration

```swift
@freestanding(declaration) macro Preview<Style>(_ name: String? = nil, immersionStyle: Style, traits: PreviewTrait<Preview.ViewTraits>..., @ViewBuilder body: @escaping @MainActor () -> any View) where Style : ImmersionStyle
```

## Parameters

- **name**: An optional display name for the preview. If you don’t specify a name, the canvas labels the preview using the line number where the preview appears in source.
- **immersionStyle**: The [ImmersionStyle](ImmersionStyle.zh-Hans.md) to use for the preview. Use this input to display the view as if it appears in an immersive space that has the specified style.
- **traits**: An optional list of [doc://com.apple.documentation/documentation/DeveloperToolsSupport/PreviewTrait] instances that customize the appearance of the preview.
- **body**: A [ViewBuilder](ViewBuilder.zh-Hans.md) that produces a SwiftUI view to preview. You typically specify one of your app’s custom views and optionally any inputs, model data, modifiers, and enclosing views that the custom view needs for normal operation.

## Overview

This preview macro behaves like [Preview(_:traits:_:body:)](Preview___traits___body.zh-Hans.md), except that it also enables you to define a scene context for the view. Specifically, it places the view in an immersive space with the specified immersion style, like the [mixed](ImmersionStyle/mixed.zh-Hans.md) style:

```swift
#Preview("Mixed immersive space", immersionStyle: .mixed) {
   ContentView()
}
```

Use this preview macro when the view needs scene context to behave as it would during normal operation of your app.

Other preview macros provide different customization options. For example, if you want to see how the view appears in a window rather than an immersive space, you can use [Preview(_:windowStyle:traits:body:)](Preview___windowStyle_traits_body.zh-Hans.md). If you want to add custom, fixed viewpoints to an immersive space preview, use [Preview(_:immersionStyle:traits:body:cameras:)](Preview___immersionStyle_traits_body_cameras.zh-Hans.md).

## Creating a preview in the context of a scene

- **Preview(_:immersionStyle:traits:body:cameras:)**: Creates a preview of a SwiftUI view in an immersive space with custom viewpoints.
- **Preview(_:windowStyle:traits:body:)**: Creates a preview of a SwiftUI view in a window.
- **Preview(_:windowStyle:traits:body:cameras:)**: Creates a preview of a SwiftUI view in a window with custom viewpoints.

