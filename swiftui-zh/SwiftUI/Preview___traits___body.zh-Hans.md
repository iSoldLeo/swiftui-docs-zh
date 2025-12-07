--- 来源：https://developer.apple.com/documentation/SwiftUI/Preview(_:traits:_:body:)

抓取时间：2025-11-30T21:30:48Z

---

# Preview(_:traits:_:body:)

**Macro**

使用指定的 traits 创建 SwiftUI 视图的预览。

## 声明

```swift
@freestanding(declaration) macro Preview(_ name: String? = nil, traits: PreviewTrait<Preview.ViewTraits>, _ additionalTraits: PreviewTrait<Preview.ViewTraits>..., @ViewBuilder body: @escaping @MainActor () -> any View)
```

## 参数

- **name**：预览的可选显示名称。如果未指定名称，画布将使用预览在源代码中出现的行号来标记预览。

- **traits**：一个 [doc://com.apple.documentation/documentation/DeveloperToolsSupport/PreviewTrait] 实例，用于自定义预览的外观。

- **additionalTraits**：可选的附加特性，用于进一步自定义预览。

- **body**：一个 [ViewBuilder](ViewBuilder.zh-Hans.md)，用于生成一个 SwiftUI 视图进行预览。您通常指定应用程序的自定义视图之一，并可选择性地指定自定义视图正常运行所需的任何输入、模型数据、修饰符和外层视图。

## 概述

此宏的行为类似于 [Preview(_:body:)](Preview___body.zh-Hans.md)，但它还允许您通过添加一个或多个特性（即 [doc://com.apple.documentation/documentation/DeveloperToolsSupport/PreviewTrait] 的实例）来自定义预览的外观。例如，您可以使用 [doc://com.apple.documentation/documentation/DeveloperToolsSupport/PreviewTrait/fixedLayout(width:height:)] 特性以固定大小显示预览：

```swift
#Preview(
    "Content",
    traits: .fixedLayout(width: 100, height: 100)
) {
    ContentView()
}
```

此宏会忽略不适用于当前上下文的特性。例如，[doc://com.apple.documentation/documentation/DeveloperToolsSupport/PreviewTrait/portrait] 特性对 visionOS 预览没有影响。

其他预览宏提供不同的自定义选项。例如，如果您想为预览指定自定义视点，请使用 [Preview(_:traits:body:cameras:)](Preview___traits_body_cameras.zh-Hans.md)。

## 创建预览

- **Preview(_:body:)**：创建 SwiftUI 视图的预览。

- **Preview(_:traits:body:cameras:)**：使用指定的特性和自定义视点创建 SwiftUI 视图的预览。


---
source: https://developer.apple.com/documentation/SwiftUI/Preview(_:traits:_:body:)
crawled: 2025-11-30T21:30:48Z
---

# Preview(_:traits:_:body:)

**Macro**

Creates a preview of a SwiftUI view using the specified traits.

## Declaration

```swift
@freestanding(declaration) macro Preview(_ name: String? = nil, traits: PreviewTrait<Preview.ViewTraits>, _ additionalTraits: PreviewTrait<Preview.ViewTraits>..., @ViewBuilder body: @escaping @MainActor () -> any View)
```

## Parameters

- **name**: An optional display name for the preview. If you don’t specify a name, the canvas labels the preview using the line number where the preview appears in source.
- **traits**: A [doc://com.apple.documentation/documentation/DeveloperToolsSupport/PreviewTrait] instance that customizes the appearance of the preview.
- **additionalTraits**: Optional additional traits that further customize the preview.
- **body**: A [ViewBuilder](ViewBuilder.zh-Hans.md) that produces a SwiftUI view to preview. You typically specify one of your app’s custom views and optionally any inputs, model data, modifiers, and enclosing views that the custom view needs for normal operation.

## Overview

This macro behaves like [Preview(_:body:)](Preview___body.zh-Hans.md) except that it also enables you to customize the appearance of the preview by adding one or more traits, which are instances of [doc://com.apple.documentation/documentation/DeveloperToolsSupport/PreviewTrait]. For example, you can display a preview at a fixed size using the [doc://com.apple.documentation/documentation/DeveloperToolsSupport/PreviewTrait/fixedLayout(width:height:)] trait:

```swift
#Preview(
    "Content",
    traits: .fixedLayout(width: 100, height: 100)
) {
    ContentView()
}
```

The macro ignores traits that don’t apply to the current context. For example, the [doc://com.apple.documentation/documentation/DeveloperToolsSupport/PreviewTrait/portrait] trait has no impact on a visionOS preview.

Other preview macros provide different customization options. For example, if you want to specify a custom viewpoint for the preview, use [Preview(_:traits:body:cameras:)](Preview___traits_body_cameras.zh-Hans.md).

## Creating a preview

- **Preview(_:body:)**: Creates a preview of a SwiftUI view.
- **Preview(_:traits:body:cameras:)**: Creates a preview of a SwiftUI view using the specified traits and custom viewpoints.

