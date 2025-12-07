--- 来源：https://developer.apple.com/documentation/SwiftUI/Preview(_:traits:body:cameras:)

抓取时间：2025-12-02T17:45:51Z

---

# Preview(_:traits:body:cameras:)

**Macro**

使用指定的 traits 和自定义视点创建 SwiftUI 视图的预览。

## 声明

```swift
@freestanding(declaration) macro Preview(_ name: String? = nil, traits: PreviewTrait<Preview.ViewTraits>..., @ViewBuilder body: @escaping @MainActor () -> any View, @PreviewCameraBuilder cameras: () -> [PreviewCamera])
```

## 参数

- **name**：预览的可选显示名称。如果未指定名称，画布将使用预览在源代码中出现的行号来标记预览。

- **traits**：[doc://com.apple.documentation/documentation/DeveloperToolsSupport/PreviewTrait] 实例的可选列表，用于自定义预览的外观。

- **body**：一个用于生成 SwiftUI 视图以进行预览的 [ViewBuilder](ViewBuilder.zh-Hans.md)。您通常指定应用程序的自定义视图之一，并可选择性地指定该自定义视图正常运行所需的任何输入、模型数据、修饰符和外层视图。

- **cameras**：一个或多个预览相机，用于指示您希望能够从中查看预览的自定义固定视角。第一个预览相机将替换默认的正面视角。

## 概述

此宏的行为与 [Preview(_:traits:_:body:)](Preview___traits___body.zh-Hans.md) 类似，但它还允许您指定一个或多个 [doc://com.apple.documentation/documentation/DeveloperToolsSupport/PreviewCamera] 实例，这些实例定义了用于查看预览的自定义固定视角：

```swift
#Preview {
    ContentView()
} cameras: {
    PreviewCamera(from: .bottomLeadingBack, name: "Corner 1")
    PreviewCamera(from: .topTrailingFront, name: "Corner 2")
}
```

如果您使用的预览宏不包含 `cameras` 闭包，则画布默认从正面显示预览。它还提供了一个相机选择器，用于选择其他标准固定视角，例如顶部或背面。当您指定一个或多个预览相机时，画布会在相机选择器中添加一个子菜单，其中列出了您定义的视角，例如上例中的“角 1”和“角 2”。画布在加载预览时，默认也会从这些自定义视角中的第一个视角显示预览。

其他预览宏提供不同的自定义选项。例如，如果您想预览视图在特定场景中的显示效果，可以使用 [Preview(_:immersionStyle:traits:body:cameras:)](Preview___immersionStyle_traits_body_cameras.zh-Hans.md) 或 [Preview(_:windowStyle:traits:body:cameras:)](Preview___windowStyle_traits_body_cameras.zh-Hans.md)。

## 创建预览

- **Preview(_:body:)**：创建 SwiftUI 视图的预览。

- **Preview(_:traits:_:body:)**：使用指定的 traits 创建 SwiftUI 视图的预览。


---
source: https://developer.apple.com/documentation/SwiftUI/Preview(_:traits:body:cameras:)
crawled: 2025-12-02T17:45:51Z
---

# Preview(_:traits:body:cameras:)

**Macro**

Creates a preview of a SwiftUI view using the specified traits and custom viewpoints.

## Declaration

```swift
@freestanding(declaration) macro Preview(_ name: String? = nil, traits: PreviewTrait<Preview.ViewTraits>..., @ViewBuilder body: @escaping @MainActor () -> any View, @PreviewCameraBuilder cameras: () -> [PreviewCamera])
```

## Parameters

- **name**: An optional display name for the preview. If you don’t specify a name, the canvas labels the preview using the line number where the preview appears in source.
- **traits**: An optional list of [doc://com.apple.documentation/documentation/DeveloperToolsSupport/PreviewTrait] instances that customize the appearance of the preview.
- **body**: A [ViewBuilder](ViewBuilder.zh-Hans.md) that produces a SwiftUI view to preview. You typically specify one of your app’s custom views and optionally any inputs, model data, modifiers, and enclosing views that the custom view needs for normal operation.
- **cameras**: One or more preview cameras that indicate the custom, fixed viewpoints that you want to be able to view the preview from. The first of these replaces the front viewpoint as the default.

## Overview

This macro behaves like [Preview(_:traits:_:body:)](Preview___traits___body.zh-Hans.md) except that it also enables you to specify one or more [doc://com.apple.documentation/documentation/DeveloperToolsSupport/PreviewCamera] instances that define custom, fixed viewpoints from which to view the preview:

```swift
#Preview {
    ContentView()
} cameras: {
    PreviewCamera(from: .bottomLeadingBack, name: "Corner 1")
    PreviewCamera(from: .topTrailingFront, name: "Corner 2")
}
```

If you use one of the preview macros that doesn’t include a `cameras` closure, the canvas displays the preview from the front by default. It also provides a camera picker to choose other standard, fixed viewpoints — like the top or the back. When you do specify one or more preview cameras, the canvas adds a submenu to the camera picker that lists the viewpoints that you define, like Corner 1 and Corner 2 in the above example. The canvas also displays the preview from the first of these custom viewpoints by default when it loads the preview.



Other preview macros provide different customization options. For example, if you want to preview the view as it would appear in a particular kind of scene, you can use [Preview(_:immersionStyle:traits:body:cameras:)](Preview___immersionStyle_traits_body_cameras.zh-Hans.md) or [Preview(_:windowStyle:traits:body:cameras:)](Preview___windowStyle_traits_body_cameras.zh-Hans.md).

## Creating a preview

- **Preview(_:body:)**: Creates a preview of a SwiftUI view.
- **Preview(_:traits:_:body:)**: Creates a preview of a SwiftUI view using the specified traits.

