---
来源： https://developer.apple.com/documentation/SwiftUI/WatchKit-integration
抓取时间： 2025-12-02T17:44:50Z
---

# WatchKit 集成

** 应用程序集**

在 SwiftUI 应用程序中添加 WatchKit 视图，或在 WatchKit 应用程序中使用 SwiftUI 视图。

## 概览

使用托管控制器将 SwiftUI 与应用程序的现有内容整合，从而将 SwiftUI 视图添加到 WatchKit 界面中。托管控制器将一组 SwiftUI 视图封装在一个表单中，然后您就可以将其添加到基于 storyboard 的应用程序中。



您还可以在 SwiftUI 界面中添加 WatchKit 视图和视图控制器。可表示对象会封装指定的视图或视图控制器，并促进被封装对象与 SwiftUI 视图之间的通信。

有关设计指导，请参阅《人机界面指南》中的 [doc://com.apple.documentation/design/Human-Interface-Guidelines/designing-for-watchos]。

## 在 WatchKit 中显示 SwiftUI 视图

- **WKHostingController**：承载 SwiftUI 视图层次结构的 WatchKit 界面控制器。
- **WKUserNotificationHostingController**：托管 SwiftUI 视图层次结构的 WatchKit 用户通知界面控制器。

## 将 WatchKit 视图添加到 SwiftUI 视图层次结构中

- **WKInterfaceObjectRepresentable**：表示 WatchKit 接口对象的视图。
- **WKInterfaceObjectRepresentableContext**：有关系统状态的上下文信息，用于创建和更新 WatchKit 接口对象。

## 框架集成

- **AppKit 集成**：在 SwiftUI 应用程序中添加 AppKit 视图，或在 AppKit 应用程序中使用 SwiftUI 视图。
- **UIKit 集成**：在您的 SwiftUI 应用程序中添加 UIKit 视图，或在您的 UIKit 应用程序中使用 SwiftUI 视图。
- 特定技术视图**：使用其他 Apple 框架提供的 SwiftUI 视图。


---
source: https://developer.apple.com/documentation/SwiftUI/WatchKit-integration
crawled: 2025-12-02T17:44:50Z
---

# WatchKit integration

**API Collection**

Add WatchKit views to your SwiftUI app, or use SwiftUI views in your WatchKit app.

## Overview

Integrate SwiftUI with your app’s existing content using hosting controllers to add SwiftUI views into WatchKit interfaces. A hosting controller wraps a set of SwiftUI views in a form that you can then add to your storyboard-based app.



You can also add WatchKit views and view controllers to your SwiftUI interfaces. A representable object wraps the designated view or view controller, and facilitates communication between the wrapped object and your SwiftUI views.

For design guidance, see [doc://com.apple.documentation/design/Human-Interface-Guidelines/designing-for-watchos] in the Human Interface Guidelines.

## Displaying SwiftUI views in WatchKit

- **WKHostingController**: A WatchKit interface controller that hosts a SwiftUI view hierarchy.
- **WKUserNotificationHostingController**: A WatchKit user notification interface controller that hosts a SwiftUI view hierarchy.

## Adding WatchKit views to SwiftUI view hierarchies

- **WKInterfaceObjectRepresentable**: A view that represents a WatchKit interface object.
- **WKInterfaceObjectRepresentableContext**: Contextual information about the state of the system that you use to create and update your WatchKit interface object.

## Framework integration

- **AppKit integration**: Add AppKit views to your SwiftUI app, or use SwiftUI views in your AppKit app.
- **UIKit integration**: Add UIKit views to your SwiftUI app, or use SwiftUI views in your UIKit app.
- **Technology-specific views**: Use SwiftUI views that other Apple frameworks provide.

