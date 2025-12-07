---
来源： https://developer.apple.com/documentation/SwiftUI/UIKit-integration
抓取时间： 2025-12-02T17:44:49Z
---

# 集成 UIKit

** 应用程序集**

在 SwiftUI 应用程序中添加 UIKit 视图，或在 UIKit 应用程序中使用 SwiftUI 视图。

## 概览

使用托管控制器将 SwiftUI 与应用程序的现有内容整合，从而将 SwiftUI 视图添加到 UIKit 界面中。托管控制器将一组 SwiftUI 视图封装在一个表单中，然后您就可以将其添加到基于 storyboard 的应用程序中。



您还可以在 SwiftUI 界面中添加 UIKit 视图和视图控制器。可表示对象会封装指定的视图或视图控制器，并促进被封装对象与 SwiftUI 视图之间的通信。

有关设计指导，请参阅《人机界面指南》中的以下章节：

- [doc://com.apple.documentation/design/Human-Interface-Guidelines/designing-for-ios]
- [doc://com.apple.documentation/design/Human-Interface-Guidelines/designing-for-ipados]
- [doc://com.apple.documentation/design/Human-Interface-Guidelines/designing-for-tvos]

## 在 UIKit 中显示 SwiftUI 视图

- 在 UIKit 中使用 SwiftUI**：了解如何将 SwiftUI 视图纳入 UIKit 应用程序。
- 统一应用程序的动画**：在 SwiftUI、UIKit 和 AppKit 中创建一致的 UI 动画体验。
- **UIHostingController**：管理 SwiftUI 视图层次结构的 UIKit 视图控制器。
- **UIHostingControllerSizingOptions**：托管控制器如何跟踪其内容大小的选项。
- **UIHostingConfiguration**：适合托管 SwiftUI 视图层次结构的内容配置。
- **UIHostingSceneDelegate**：扩展了 `UIKit/UISceneDelegate` 以桥接 SwiftUI 场景。

## 将 UIKit 视图添加到 SwiftUI 视图层次结构中

- **UIViewRepresentable**：UIKit 视图的封装器，用于将该视图集成到 SwiftUI 视图层次结构中。
- **UIViewRepresentableContext**：有关系统状态的上下文信息，用于创建和更新 UIKit 视图。
- **UIViewControllerRepresentable**：表示 UIKit 视图控制器的视图。
- **UIViewControllerRepresentableContext**：有关系统状态的上下文信息，用于创建和更新 UIKit 视图控制器。

## 在 SwiftUI 视图层次中添加 UIKit 手势识别器

- **UIGestureRecognizerRepresentable**：`UIGestureRecognizer`的封装器，用于将手势识别器集成到 SwiftUI 层次结构中。
- **UIGestureRecognizerRepresentableContext**：有关系统状态的上下文信息，用于创建和更新所代表的手势识别器。
- **UIGestureRecognizerRepresentableCoordinateSpaceConverter**：代理结构，用于将位置转换为与 [UIGestureRecognizerRepresentable](UIGestureRecognizerRepresentable.zh-Hans.md)相关联的 SwiftUI 视图层次结构中的坐标空间/坐标空间之间的位置。

## 共享配置信息

- **UITraitBridgedEnvironmentKey**

## 在 UIKit 中托管装饰品

- **UIHostingOrnament**：表示适合在 UIKit 中托管的装饰品的模型。
- **UIOrnament**：表示装饰品的抽象基类。

## 框架集成

- **AppKit 集成**：在 SwiftUI 应用程序中添加 AppKit 视图，或在 AppKit 应用程序中使用 SwiftUI 视图。
- **WatchKit 集成**：在您的 SwiftUI 应用程序中添加 WatchKit 视图，或在您的 WatchKit 应用程序中使用 SwiftUI 视图。
- 特定技术视图**：使用其他 Apple 框架提供的 SwiftUI 视图。


---
source: https://developer.apple.com/documentation/SwiftUI/UIKit-integration
crawled: 2025-12-02T17:44:49Z
---

# UIKit integration

**API Collection**

Add UIKit views to your SwiftUI app, or use SwiftUI views in your UIKit app.

## Overview

Integrate SwiftUI with your app’s existing content using hosting controllers to add SwiftUI views into UIKit interfaces. A hosting controller wraps a set of SwiftUI views in a form that you can then add to your storyboard-based app.



You can also add UIKit views and view controllers to your SwiftUI interfaces. A representable object wraps the designated view or view controller, and facilitates communication between the wrapped object and your SwiftUI views.

For design guidance, see the following sections in the Human Interface Guidelines:

- [doc://com.apple.documentation/design/Human-Interface-Guidelines/designing-for-ios]
- [doc://com.apple.documentation/design/Human-Interface-Guidelines/designing-for-ipados]
- [doc://com.apple.documentation/design/Human-Interface-Guidelines/designing-for-tvos]

## Displaying SwiftUI views in UIKit

- **Using SwiftUI with UIKit**: Learn how to incorporate SwiftUI views into a UIKit app.
- **Unifying your app’s animations**: Create a consistent UI animation experience across SwiftUI, UIKit, and AppKit.
- **UIHostingController**: A UIKit view controller that manages a SwiftUI view hierarchy.
- **UIHostingControllerSizingOptions**: Options for how a hosting controller tracks its content’s size.
- **UIHostingConfiguration**: A content configuration suitable for hosting a hierarchy of SwiftUI views.
- **UIHostingSceneDelegate**: Extends `UIKit/UISceneDelegate` to bridge SwiftUI scenes.

## Adding UIKit views to SwiftUI view hierarchies

- **UIViewRepresentable**: A wrapper for a UIKit view that you use to integrate that view into your SwiftUI view hierarchy.
- **UIViewRepresentableContext**: Contextual information about the state of the system that you use to create and update your UIKit view.
- **UIViewControllerRepresentable**: A view that represents a UIKit view controller.
- **UIViewControllerRepresentableContext**: Contextual information about the state of the system that you use to create and update your UIKit view controller.

## Adding UIKit gesture recognizers into SwiftUI view hierarchies

- **UIGestureRecognizerRepresentable**: A wrapper for a `UIGestureRecognizer` that you use to integrate that gesture recognizer into your SwiftUI hierarchy.
- **UIGestureRecognizerRepresentableContext**: Contextual information about the state of the system that you use to create and update a represented gesture recognizer.
- **UIGestureRecognizerRepresentableCoordinateSpaceConverter**: A proxy structure used to convert locations to/from coordinate spaces in the hierarchy of the SwiftUI view associated with a [UIGestureRecognizerRepresentable](UIGestureRecognizerRepresentable.zh-Hans.md).

## Sharing configuration information

- **UITraitBridgedEnvironmentKey**

## Hosting an ornament in UIKit

- **UIHostingOrnament**: A model that represents an ornament suitable for being hosted in UIKit.
- **UIOrnament**: The abstract base class that represents an ornament.

## Framework integration

- **AppKit integration**: Add AppKit views to your SwiftUI app, or use SwiftUI views in your AppKit app.
- **WatchKit integration**: Add WatchKit views to your SwiftUI app, or use SwiftUI views in your WatchKit app.
- **Technology-specific views**: Use SwiftUI views that other Apple frameworks provide.

