---
来源： https://developer.apple.com/documentation/SwiftUI/Xcode-library-customization
抓取时间： 2025-12-02T17:46:06Z
---

# Xcode 库定制

在 Xcode 库中公开自定义视图和修改器。

## 概览

您可以将自定义 SwiftUI 视图和视图修改器添加到 Xcode 库中。这样，开发您的应用程序或采用您的框架的任何人都可以通过单击 Xcode 工具栏中的库按钮 (+) 来访问它们。您可以选择并拖动自定义库项目到代码中，就像您选择系统提供的项目一样。



要向库中添加项目，请创建一个符合[doc://com.apple.documentation/documentation/DeveloperToolsSupport/LibraryContentProvider] 协议的结构，并将您要添加的任何项目封装为[doc://com.apple.documentation/documentation/DeveloperToolsSupport/LibraryItem] 实例。实现[doc://com.apple.documentation/documentation/DeveloperToolsSupport/LibraryContentProvider/views] 计算属性，以添加包含视图的库项。实施[doc://com.apple.documentation/documentation/DeveloperToolsSupport/LibraryContentProvider/modifiers(base:)] 方法来添加包含视图修改器的项。当您工作时，Xcode 会从您项目中的所有库内容提供者中获取项，并将它们放在库中供您使用。

## 创建库项

- **LibraryContentProvider**：Xcode 库和代码完成内容的来源。
- **LibraryItem**：添加到 Xcode 库的单个项目。

## 工具支持

- Xcode 中的**预览**：为您的自定义视图生成动态、交互式预览。
- 性能分析**：测量并改进应用程序的响应速度。


---
source: https://developer.apple.com/documentation/SwiftUI/Xcode-library-customization
crawled: 2025-12-02T17:46:06Z
---

# Xcode library customization

Expose custom views and modifiers in the Xcode library.

## Overview

You can add your custom SwiftUI views and view modifiers to Xcode’s library. This allows anyone developing your app or adopting your framework to access them by clicking the Library button (+) in Xcode’s toolbar. You can select and drag the custom library items into code, just like you would for system-provided items.



To add items to the library, create a structure that conforms to the [doc://com.apple.documentation/documentation/DeveloperToolsSupport/LibraryContentProvider] protocol and encapsulate any items you want to add as [doc://com.apple.documentation/documentation/DeveloperToolsSupport/LibraryItem] instances. Implement the [doc://com.apple.documentation/documentation/DeveloperToolsSupport/LibraryContentProvider/views] computed property to add library items containing views. Implement the [doc://com.apple.documentation/documentation/DeveloperToolsSupport/LibraryContentProvider/modifiers(base:)] method to add items containing view modifiers. Xcode harvests items from all of the library content providers in your project as you work, and makes them available to you in its library.

## Creating library items

- **LibraryContentProvider**: A source of Xcode library and code completion content.
- **LibraryItem**: A single item to add to the Xcode library.

## Tool support

- **Previews in Xcode**: Generate dynamic, interactive previews of your custom views.
- **Performance analysis**: Measure and improve your app’s responsiveness.

