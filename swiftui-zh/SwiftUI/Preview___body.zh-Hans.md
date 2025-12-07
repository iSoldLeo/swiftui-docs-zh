--- 来源：https://developer.apple.com/documentation/SwiftUI/Preview(_:body:)

抓取时间：2025-12-02T17:45:49Z

---

# Preview(_:body:)

**Macro**

创建 SwiftUI 视图的预览。

## 声明

```swift
@freestanding(declaration) macro Preview(_ name: String? = nil, @ViewBuilder body: @escaping @MainActor () -> any View)
```

## 参数

- **name**：预览的可选显示名称。如果未指定名称，画布将使用预览在源代码中出现的行号来标记预览。

- **body**：一个用于生成 SwiftUI 视图以进行预览的 [ViewBuilder](ViewBuilder.zh-Hans.md)。您通常会指定应用程序的自定义视图之一，并可选择性地指定该自定义视图正常运行所需的任何输入、模型数据、修饰符和外层视图。

## 概述

使用此宏可在画布中显示 SwiftUI 预览。通常，您需要为应用程序定义的每个视图（[View](View.zh-Hans.md)）指定至少一个预览宏，以帮助您开发、测试和调试视图：

```swift
struct ContentView: View {
    var body: some View {
        // ...
    }
}

#Preview {
    ContentView()
}
```

如果源文件中包含多个预览，画布会提供控件，使您能够在源文件处于活动状态时选择要显示的预览。画布会使用预览在源文件中出现的行号来标记不同的预览。为了更好地识别画布中的预览，您可以为它们命名。例如，如果您的 `ContentView` 接受布尔输入，您可以为每个输入状态创建命名预览：

```swift
#Preview("Input true") {
    ContentView(someInput: true)
}

#Preview("Input false") {
    ContentView(someInput: false)
}
```

在预览中，您可以提供视图正常运行所需的各种输入、模型数据和其他基础架构。例如，如果您的应用需要将自定义视图作为侧边栏显示在 [NavigationSplitView](NavigationSplitView.zh-Hans.md) 中，则可以这样做。

其他预览宏提供不同的自定义选项。例如，如果您需要使用一个或多个 [doc://com.apple.documentation/documentation/DeveloperToolsSupport/PreviewTrait] 实例来修改预览的外观，请使用 [Preview(_:traits:_:body:)](Preview___traits___body.zh-Hans.md) 宏。

## 创建预览

- **Preview(_:traits:_:body:)**：使用指定的 traits 创建 SwiftUI 视图的预览。

- **Preview(_:traits:body:cameras:)**：使用指定的特性和自定义视点创建 SwiftUI 视图的预览。


---
source: https://developer.apple.com/documentation/SwiftUI/Preview(_:body:)
crawled: 2025-12-02T17:45:49Z
---

# Preview(_:body:)

**Macro**

Creates a preview of a SwiftUI view.

## Declaration

```swift
@freestanding(declaration) macro Preview(_ name: String? = nil, @ViewBuilder body: @escaping @MainActor () -> any View)
```

## Parameters

- **name**: An optional display name for the preview. If you don’t specify a name, the canvas labels the preview using the line number where the preview appears in source.
- **body**: A [ViewBuilder](ViewBuilder.zh-Hans.md) that produces a SwiftUI view to preview. You typically specify one of your app’s custom views and optionally any inputs, model data, modifiers, and enclosing views that the custom view needs for normal operation.

## Overview

Use this macro to display a SwiftUI preview in the canvas. You typically specify at least one preview macro for every [View](View.zh-Hans.md) that your app defines to help you develop, test, and debug the view:

```swift
struct ContentView: View {
    var body: some View {
        // ...
    }
}

#Preview {
    ContentView()
}
```

If you include more than one preview in a source file, the canvas provides controls that enable you to select which to display when that source file is active. The canvas labels the different previews with the line number where the preview appears in source. To better identify the previews in the canvas, you can give them names. For example if your `ContentView` takes a Boolean input, you can create named previews for each input state:

```swift
#Preview("Input true") {
    ContentView(someInput: true)
}

#Preview("Input false") {
    ContentView(someInput: false)
}
```

Inside the preview, you can provide different inputs, model data, and other infrastructure that the view needs for normal operation. For example, you can present a custom view as the sidebar inside a [NavigationSplitView](NavigationSplitView.zh-Hans.md) if that’s how your app uses the view.

Other preview macros provide different customization options. For example, if you need to modify the appearance of a preview using one or more [doc://com.apple.documentation/documentation/DeveloperToolsSupport/PreviewTrait], instances, use the [Preview(_:traits:_:body:)](Preview___traits___body.zh-Hans.md) macro.

## Creating a preview

- **Preview(_:traits:_:body:)**: Creates a preview of a SwiftUI view using the specified traits.
- **Preview(_:traits:body:cameras:)**: Creates a preview of a SwiftUI view using the specified traits and custom viewpoints.

