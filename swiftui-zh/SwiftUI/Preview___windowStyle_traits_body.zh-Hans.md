--- 来源：https://developer.apple.com/documentation/SwiftUI/Preview(_:windowStyle:traits:body:)

抓取时间：2025-12-02T17:45:54Z

---

# Preview(_:windowStyle:traits:body:)

**Macro**

在窗口中创建 SwiftUI 视图的预览。

## 声明

```swift
@freestanding(declaration) macro Preview<Style>(_ name: String? = nil, windowStyle: Style, traits: PreviewTrait<Preview.ViewTraits>..., @ViewBuilder body: @escaping @MainActor () -> any View) where Style : WindowStyle
```

## 参数

- **name**：预览的可选显示名称。如果未指定名称，画布将使用预览在源代码中出现的行号来标记预览。

- **windowStyle**：用于预览的 [WindowStyle](WindowStyle.zh-Hans.md)。使用此输入可将视图显示为如同在具有指定样式的窗口中显示一样。

- **traits**：一个可选的 [doc://com.apple.documentation/documentation/DeveloperToolsSupport/PreviewTrait] 实例列表，用于自定义预览的外观。

- **body**：一个 [ViewBuilder](ViewBuilder.zh-Hans.md)，用于生成要预览的 SwiftUI 视图。您通常指定应用程序的自定义视图之一，并可选择性地指定自定义视图正常运行所需的任何输入、模型数据、修饰符和外层视图。

## 概述

此预览宏的行为类似于 [Preview(_:traits:_:body:)](Preview___traits___body.zh-Hans.md)，但它还允许您为视图定义场景上下文。具体来说，它会将视图放置在具有指定窗口样式的窗口中，例如 [volumetric](WindowStyle/volumetric.zh-Hans.md) 样式：

```swift
#Preview("Volume", windowStyle: .volumetric) {
   ContentView()
}
```

当视图需要场景上下文才能像在应用程序正常运行期间那样工作时，请使用此预览宏。

其他预览宏提供不同的自定义选项。例如，如果您想查看视图在沉浸式空间而非窗口中的显示效果，可以使用 [Preview(_:immersionStyle:traits:body:)](Preview___immersionStyle_traits_body.zh-Hans.md)。如果您想向基于窗口的预览添加自定义的固定视点，请使用 [Preview(_:windowStyle:traits:body:cameras:)](Preview___windowStyle_traits_body_cameras.zh-Hans.md)。

## 在场景上下文中创建预览

- **Preview(_:immersionStyle:traits:body:)**：在沉浸式空间中创建 SwiftUI 视图的预览。

- **Preview(_:immersionStyle:traits:body:cameras:)**：在具有自定义视点的沉浸式空间中创建 SwiftUI 视图的预览。

- **Preview(_:windowStyle:traits:body:cameras:)**：在具有自定义视点的窗口中创建 SwiftUI 视图的预览。


---
source: https://developer.apple.com/documentation/SwiftUI/Preview(_:windowStyle:traits:body:)
crawled: 2025-12-02T17:45:54Z
---

# Preview(_:windowStyle:traits:body:)

**Macro**

Creates a preview of a SwiftUI view in a window.

## Declaration

```swift
@freestanding(declaration) macro Preview<Style>(_ name: String? = nil, windowStyle: Style, traits: PreviewTrait<Preview.ViewTraits>..., @ViewBuilder body: @escaping @MainActor () -> any View) where Style : WindowStyle
```

## Parameters

- **name**: An optional display name for the preview. If you don’t specify a name, the canvas labels the preview using the line number where the preview appears in source.
- **windowStyle**: The [WindowStyle](WindowStyle.zh-Hans.md) to use for the preview. Use this input to display the view as if it appears in a window that has the specified style.
- **traits**: An optional list of [doc://com.apple.documentation/documentation/DeveloperToolsSupport/PreviewTrait] instances that customize the appearance of the preview.
- **body**: A [ViewBuilder](ViewBuilder.zh-Hans.md) that produces a SwiftUI view to preview. You typically specify one of your app’s custom views and optionally any inputs, model data, modifiers, and enclosing views that the custom view needs for normal operation.

## Overview

This preview macro behaves like [Preview(_:traits:_:body:)](Preview___traits___body.zh-Hans.md), except that it also enables you to define a scene context for the view. Specifically, it places the view in a window with the specified window style, like the [volumetric](WindowStyle/volumetric.zh-Hans.md) style:

```swift
#Preview("Volume", windowStyle: .volumetric) {
   ContentView()
}
```

Use this preview macro when the view needs scene context to behave as it would during normal operation of your app.

Other preview macros provide different customization options. For example, if you want to see how the view appears in an immersive space rather than a window, you can use [Preview(_:immersionStyle:traits:body:)](Preview___immersionStyle_traits_body.zh-Hans.md). If you want to add custom, fixed viewpoints to a window-based preview, use [Preview(_:windowStyle:traits:body:cameras:)](Preview___windowStyle_traits_body_cameras.zh-Hans.md).

## Creating a preview in the context of a scene

- **Preview(_:immersionStyle:traits:body:)**: Creates a preview of a SwiftUI view in an immersive space.
- **Preview(_:immersionStyle:traits:body:cameras:)**: Creates a preview of a SwiftUI view in an immersive space with custom viewpoints.
- **Preview(_:windowStyle:traits:body:cameras:)**: Creates a preview of a SwiftUI view in a window with custom viewpoints.

