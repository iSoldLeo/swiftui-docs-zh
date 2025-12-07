---
来源： https://developer.apple.com/documentation/SwiftUI/AppKit-integration
抓取时间： 2025-12-02T17:45:06Z
---

# AppKit 集成

**API 集合**

在 SwiftUI 应用程序中添加 AppKit 视图，或在 AppKit 应用程序中使用 SwiftUI 视图。

### 概览

使用托管控制器将 SwiftUI 与应用程序的现有内容整合，从而将 SwiftUI 视图添加到 AppKit 界面中。托管控制器将一组 SwiftUI 视图封装在一个表单中，然后您就可以将其添加到基于 storyboard 的应用程序中。



您还可以在 SwiftUI 界面中添加 AppKit 视图和视图控制器。可表示对象会封装指定的视图或视图控制器，并促进被封装对象与 SwiftUI 视图之间的通信。

有关设计指导，请参阅《人机界面指南》中的 [doc://com.apple.documentation/design/Human-Interface-Guidelines/designing-for-macos]。

## 在 AppKit 中显示 SwiftUI 视图

- 统一应用程序的动画**：在 SwiftUI、UIKit 和 AppKit 中创建一致的 UI 动画体验。
- **NSHostingController**：托管 SwiftUI 视图层次结构的 AppKit 视图控制器。
- **NSHostingView**：托管 SwiftUI 视图层次结构的 AppKit 视图。
- **NSHostingMenu**：包含由 SwiftUI 视图定义的菜单项的 AppKit 菜单。
- **NSHostingSizingOptions**：关于托管视图和控制器如何将其内容的大小反映到自动布局约束中的选项。
- **NSHostingSceneRepresentation**：一种承载并可呈现 SwiftUI 场景的 AppKit 类型
- **NSHostingSceneBridgingOptions**：托管视图和控制器如何管理相关窗口的选项。

## 将 AppKit 视图添加到 SwiftUI 视图层次结构中

- **NSViewRepresentable**：封装器，用于将 AppKit 视图集成到 SwiftUI 视图层次结构中。
- **NSViewRepresentableContext**：有关系统状态的上下文信息，用于创建和更新 AppKit 视图。
- **NSViewControllerRepresentable**：封装器，用于将 AppKit 视图控制器集成到 SwiftUI 界面中。
- **NSViewControllerRepresentableContext**：有关系统状态的上下文信息，用于创建和更新 AppKit 视图控制器。

## 在 SwiftUI 视图层次中添加 AppKit 手势识别器

- **NSGestureRecognizerRepresentable**：`NSGestureRecognizer`的封装器，用于将手势识别器集成到 SwiftUI 层次结构中。
- **NSGestureRecognizerRepresentableContext**：有关系统状态的上下文信息，用于创建和更新所代表的手势识别器。
- **NSGestureRecognizerRepresentableCoordinateSpaceConverter**：一种结构，用于在 SwiftUI 视图的层次结构中将位置转换为与 [NSGestureRecognizerRepresentable](NSGestureRecognizerRepresentable.zh-Hans.md)相关联的坐标空间，或将位置转换为与 [NSGestureRecognizerRepresentable](NSGestureRecognizerRepresentable.zh-Hans.md)相关联的坐标空间。

## 框架集成

- **UIKit 集成**：在 SwiftUI 应用程序中添加 UIKit 视图，或在 UIKit 应用程序中使用 SwiftUI 视图。
- **WatchKit 集成**：在您的 SwiftUI 应用程序中添加 WatchKit 视图，或在您的 WatchKit 应用程序中使用 SwiftUI 视图。
- 特定技术视图**：使用其他 Apple 框架提供的 SwiftUI 视图。


---
source: https://developer.apple.com/documentation/SwiftUI/AppKit-integration
crawled: 2025-12-02T17:45:06Z
---

# AppKit integration

**API Collection**

Add AppKit views to your SwiftUI app, or use SwiftUI views in your AppKit app.

## Overview

Integrate SwiftUI with your app’s existing content using hosting controllers to add SwiftUI views into AppKit interfaces. A hosting controller wraps a set of SwiftUI views in a form that you can then add to your storyboard-based app.



You can also add AppKit views and view controllers to your SwiftUI interfaces. A representable object wraps the designated view or view controller, and facilitates communication between the wrapped object and your SwiftUI views.

For design guidance, see [doc://com.apple.documentation/design/Human-Interface-Guidelines/designing-for-macos] in the Human Interface Guidelines.

## Displaying SwiftUI views in AppKit

- **Unifying your app’s animations**: Create a consistent UI animation experience across SwiftUI, UIKit, and AppKit.
- **NSHostingController**: An AppKit view controller that hosts SwiftUI view hierarchy.
- **NSHostingView**: An AppKit view that hosts a SwiftUI view hierarchy.
- **NSHostingMenu**: An AppKit menu with menu items that are defined by a SwiftUI View.
- **NSHostingSizingOptions**: Options for how hosting views and controllers reflect their content’s size into Auto Layout constraints.
- **NSHostingSceneRepresentation**: An AppKit type that hosts and can present SwiftUI scenes
- **NSHostingSceneBridgingOptions**: Options for how hosting views and controllers manage aspects of the associated window.

## Adding AppKit views to SwiftUI view hierarchies

- **NSViewRepresentable**: A wrapper that you use to integrate an AppKit view into your SwiftUI view hierarchy.
- **NSViewRepresentableContext**: Contextual information about the state of the system that you use to create and update your AppKit view.
- **NSViewControllerRepresentable**: A wrapper that you use to integrate an AppKit view controller into your SwiftUI interface.
- **NSViewControllerRepresentableContext**: Contextual information about the state of the system that you use to create and update your AppKit view controller.

## Adding AppKit gesture recognizers into SwiftUI view hierarchies

- **NSGestureRecognizerRepresentable**: A wrapper for an `NSGestureRecognizer` that you use to integrate that gesture recognizer into your SwiftUI hierarchy.
- **NSGestureRecognizerRepresentableContext**: Contextual information about the state of the system that you use to create and update a represented gesture recognizer.
- **NSGestureRecognizerRepresentableCoordinateSpaceConverter**: A structure used to convert locations to and from coordinate spaces in the hierarchy of the SwiftUI view associated with an [NSGestureRecognizerRepresentable](NSGestureRecognizerRepresentable.zh-Hans.md).

## Framework integration

- **UIKit integration**: Add UIKit views to your SwiftUI app, or use SwiftUI views in your UIKit app.
- **WatchKit integration**: Add WatchKit views to your SwiftUI app, or use SwiftUI views in your WatchKit app.
- **Technology-specific views**: Use SwiftUI views that other Apple frameworks provide.

