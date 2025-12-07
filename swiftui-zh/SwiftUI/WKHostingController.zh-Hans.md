---
来源： https://developer.apple.com/documentation/SwiftUI/WKHostingController
抓取时间： 2025-12-02T17:45:07Z
---

# WKHostingController

**Class**

用于托管 SwiftUI 视图层次结构的 WatchKit 界面控制器。

## 声明

```swift
@MainActor @preconcurrency class WKHostingController<Body> where Body : View
```

## 概览

[WKHostingController](WKHostingController.zh-Hans.md)使用 SwiftUI 视图展示和管理应用程序的主界面。您必须子类化[WKHostingController](WKHostingController.zh-Hans.md) 并覆盖[body](WKHostingController/body.zh-Hans.md) 属性，以提供您要显示的 SwiftUI 视图集。像显示其他[doc://com.apple.documentation/documentation/WatchKit/WKInterfaceController] 对象一样显示托管控制器的内容。例如，您可以将其作为应用程序的根界面控制器之一，或以模式方式显示。

## 创建托管控制器对象

- **init()**：创建托管控制器对象，用于使用 SwiftUI 视图实现应用程序的主界面

## 获取根视图

- **body**：要为界面控制器显示的视图层次结构的根视图。

## 更新根视图

- **updateBodyIfNeeded()**：立即更新界面控制器的视图集（如果正在等待更新）。
- **setNeedsBodyUpdate()**：使当前 SwiftUI 视图无效，并在下一周期触发更新。

## 在 WatchKit 中显示 SwiftUI 视图

- **WKUserNotificationHostingController**：承载 SwiftUI 视图层次结构的 WatchKit 用户通知界面控制器。

## 继承自

- WKInterfaceController

## 符合

- CVarArg
- 自定义调试字符串可转换
- 自定义字符串可转换
- 等价
- 可散列
- NSObjectProtocol


---
source: https://developer.apple.com/documentation/SwiftUI/WKHostingController
crawled: 2025-12-02T17:45:07Z
---

# WKHostingController

**Class**

A WatchKit interface controller that hosts a SwiftUI view hierarchy.

## Declaration

```swift
@MainActor @preconcurrency class WKHostingController<Body> where Body : View
```

## Overview

A [WKHostingController](WKHostingController.zh-Hans.md) presents and manages your app’s main interface using SwiftUI views. You must subclass [WKHostingController](WKHostingController.zh-Hans.md) and override the [body](WKHostingController/body.zh-Hans.md) property to provide the set of SwiftUI views you want to display. Display the content of your hosting controller as you would any other [doc://com.apple.documentation/documentation/WatchKit/WKInterfaceController] object. For example, you can include it as one of your app’s root interface controllers, or present it modally.

## Creating a hosting controller object

- **init()**: Creates a hosting controller object that you can use to implement your app’s main interface using SwiftUI views

## Getting the root view

- **body**: The root view of the view hierarchy to display for your interface controller.

## Updating the root view

- **updateBodyIfNeeded()**: Updates the interface controller’s set of views immediately, if updates are pending.
- **setNeedsBodyUpdate()**: Invalidates the current SwiftUI views and triggers an update during the next cycle.

## Displaying SwiftUI views in WatchKit

- **WKUserNotificationHostingController**: A WatchKit user notification interface controller that hosts a SwiftUI view hierarchy.

## Inherits From

- WKInterfaceController

## Conforms To

- CVarArg
- CustomDebugStringConvertible
- CustomStringConvertible
- Equatable
- Hashable
- NSObjectProtocol

