---
来源： https://developer.apple.com/documentation/SwiftUI/Previews-in-Xcode
抓取时间： 2025-12-02T17:22:07Z
---

# 在 Xcode 中预览

** 应用程序集**

为您的自定义视图生成动态、交互式预览。

## 概览

当您使用 SwiftUI 创建自定义[View](View.zh-Hans.md) 时，Xcode 可以显示视图内容的预览，该预览会在您更改视图代码时保持更新。您可以使用其中一个预览宏（如[Preview(_:body:)](Preview___body.zh-Hans.md)）来告诉 Xcode 显示什么内容。Xcode 会将预览显示在代码旁边的画布中。



不同的预览宏支持不同的配置。例如，您可以使用 [Preview(_:traits:_:body:)](Preview___traits___body.zh-Hans.md) 宏添加影响预览外观的特征，或者使用 [Preview(_:traits:body:cameras:)](Preview___traits_body_cameras.zh-Hans.md) 宏为预览添加自定义视点。您还可以检查视图在特定场景类型中的表现。例如，在 visionOS 中，您可以使用 [Preview(_:immersionStyle:traits:body:)](Preview___immersionStyle_traits_body.zh-Hans.md) 宏来预览您在[ImmersiveSpace](ImmersiveSpace.zh-Hans.md) 中的视图。

您通常依靠预览宏在代码中创建预览。但是，如果使用预览宏无法获得所需的行为，则可以使用[PreviewProvider](PreviewProvider.zh-Hans.md) 协议及其相关的支持类型来定义和配置预览。

### 要点

- 在 Xcode 中预览应用程序的界面**：快速迭代设计并在不同的苹果设备上预览应用程序的显示效果。

## 创建预览

- **Preview(_:body:)**：创建 SwiftUI 视图的预览。
- **Preview(_:traits:_:body:)**：使用指定的特质创建 SwiftUI 视图的预览。
- **Preview(_:traits:body:cameras:)**：使用指定的特质和自定义视点创建 SwiftUI 视图的预览。

## 在场景上下文中创建预览

- **Preview(_:immersionStyle:traits:body:)**：在沉浸式空间中创建 SwiftUI 视图的预览。
- **Preview(_:immersionStyle:traits:body:cameras:)**：在具有自定义视点的沉浸式空间中创建 SwiftUI 视图的预览。
- **Preview(_:windowStyle:traits:body:)**：在窗口中创建 SwiftUI 视图的预览。
- **Preview(_:windowStyle:traits:body:cameras:)**：使用自定义视点在窗口中创建 SwiftUI 视图的预览。

## 定义预览

- **Previewable()**：允许动态属性在预览中内嵌显示的标签。
- **PreviewProvider**：在 Xcode 中生成视图预览的类型。
- **PreviewPlatform**：可以运行预览的平台。
- **previewDisplayName(_:)**：设置在预览画布中显示的用户可见名称。
- **PreviewModifier**：定义可显示预览的环境的类型。
- **PreviewModifierContent**：预览中经过类型擦除的内容。

## 自定义预览

- **previewDevice(_:)**：覆盖预览的设备。
- **PreviewDevice**：运行预览的模拟器设备。
- **previewLayout(_:)**：覆盖预览容器的大小。
- **previewInterfaceOrientation(_:)**：覆盖预览的方向。
- **InterfaceOrientation**：从用户角度看界面的方向。

## 设置上下文

- **previewContext(_:)**：声明预览的上下文。
- **PreviewContext**：与预览一起使用的上下文类型。
- **PreviewContextKey**：用于预览上下文的键类型。

## 在调试模式下创建

- **DebugReplaceableView**：在调试构建中删除视图不透明结果类型。

## 工具支持

- Xcode 库自定义**：在 Xcode 库中公开自定义视图和修改器。
- 性能分析**：测量并改进应用程序的响应速度。


---
source: https://developer.apple.com/documentation/SwiftUI/Previews-in-Xcode
crawled: 2025-12-02T17:22:07Z
---

# Previews in Xcode

**API Collection**

Generate dynamic, interactive previews of your custom views.

## Overview

When you create a custom [View](View.zh-Hans.md) with SwiftUI, Xcode can display a preview of the view’s content that stays up-to-date as you make changes to the view’s code. You use one of the preview macros — like [Preview(_:body:)](Preview___body.zh-Hans.md) — to tell Xcode what to display. Xcode shows the preview in a canvas beside your code.



Different preview macros enable different kinds of configuration. For example, you can add traits that affect the preview’s appearance using the [Preview(_:traits:_:body:)](Preview___traits___body.zh-Hans.md) macro or add custom viewpoints for the preview using the [Preview(_:traits:body:cameras:)](Preview___traits_body_cameras.zh-Hans.md) macro. You can also check how your view behaves inside a specific scene type. For example, in visionOS you can use the [Preview(_:immersionStyle:traits:body:)](Preview___immersionStyle_traits_body.zh-Hans.md) macro to preview your view inside an [ImmersiveSpace](ImmersiveSpace.zh-Hans.md).

You typically rely on preview macros to create previews in your code. However, if you can’t get the behavior you need using a preview macro, you can use the [PreviewProvider](PreviewProvider.zh-Hans.md) protocol and its associated supporting types to define and configure a preview.

## Essentials

- **Previewing your app’s interface in Xcode**: Iterate designs quickly and preview your apps’ displays across different Apple devices.

## Creating a preview

- **Preview(_:body:)**: Creates a preview of a SwiftUI view.
- **Preview(_:traits:_:body:)**: Creates a preview of a SwiftUI view using the specified traits.
- **Preview(_:traits:body:cameras:)**: Creates a preview of a SwiftUI view using the specified traits and custom viewpoints.

## Creating a preview in the context of a scene

- **Preview(_:immersionStyle:traits:body:)**: Creates a preview of a SwiftUI view in an immersive space.
- **Preview(_:immersionStyle:traits:body:cameras:)**: Creates a preview of a SwiftUI view in an immersive space with custom viewpoints.
- **Preview(_:windowStyle:traits:body:)**: Creates a preview of a SwiftUI view in a window.
- **Preview(_:windowStyle:traits:body:cameras:)**: Creates a preview of a SwiftUI view in a window with custom viewpoints.

## Defining a preview

- **Previewable()**: Tag allowing a dynamic property to appear inline in a preview.
- **PreviewProvider**: A type that produces view previews in Xcode.
- **PreviewPlatform**: Platforms that can run the preview.
- **previewDisplayName(_:)**: Sets a user visible name to show in the canvas for a preview.
- **PreviewModifier**: A type that defines an environment in which previews can appear.
- **PreviewModifierContent**: The type-erased content of a preview.

## Customizing a preview

- **previewDevice(_:)**: Overrides the device for a preview.
- **PreviewDevice**: A simulator device that runs a preview.
- **previewLayout(_:)**: Overrides the size of the container for the preview.
- **previewInterfaceOrientation(_:)**: Overrides the orientation of the preview.
- **InterfaceOrientation**: The orientation of the interface from the user’s perspective.

## Setting a context

- **previewContext(_:)**: Declares a context for the preview.
- **PreviewContext**: A context type for use with a preview.
- **PreviewContextKey**: A key type for a preview context.

## Building in debug mode

- **DebugReplaceableView**: Erases view opaque result types in debug builds.

## Tool support

- **Xcode library customization**: Expose custom views and modifiers in the Xcode library.
- **Performance analysis**: Measure and improve your app’s responsiveness.

