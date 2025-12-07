---
来源： https://developer.apple.com/documentation/SwiftUI/WKUserNotificationHostingController
抓取时间： 2025-12-02T17:45:07Z
---

# WKUserNotificationHostingController

**Class**

用于托管 SwiftUI 视图层次结构的 WatchKit 用户通知界面控制器。

### 声明

```swift
@MainActor @preconcurrency class WKUserNotificationHostingController<Body> where Body : View
```

## 概览

[WKUserNotificationHostingController](WKUserNotificationHostingController.zh-Hans.md)使用 SwiftUI 视图展示和管理应用程序的通知界面。您必须子类化[WKUserNotificationHostingController](WKUserNotificationHostingController.zh-Hans.md) 并重载[body](WKUserNotificationHostingController/body.zh-Hans.md) 属性，以提供要显示的 SwiftUI 视图集。在手表应用程序的故事板中，为动态交互界面指定自定义类的名称。

## 创建托管控制器对象

- **init()**：创建一个通知托管控制器对象，用于使用 SwiftUI 视图实现通知接口。

## 获取根视图

- **body**：要为通知接口显示的视图层次结构的根视图。

## 配置通知

- **coalescedDescriptionFormat**：同一类型的多个通知同时到达时要显示的格式字符串。如果指定自定义字符串，则可以使用 %d 变量来反映通知的数量。`nil`格式将作为系统默认格式。
- **isInteractive**：如果通知应接受用户输入。
- **sashColor**：在长条形界面的斜线内使用的颜色。如果 `nil`，边框将使用系统默认颜色。
- **subtitleColor**：应用于简短外观界面中显示的字幕文本的颜色。如果`nil`，文本将使用默认系统颜色。
- **titleColor**：应用于窗格中显示的文本的颜色。如果 `nil`，文本将使用系统默认颜色。
- **wantsSashBlur**：如果纱带应包括背景模糊效果。

## 在 WatchKit 中显示 SwiftUI 视图

- **WKHostingController**：承载 SwiftUI 视图层次结构的 WatchKit 界面控制器。

## 继承自

- WKUserNotificationInterfaceController

## 符合

- CVarArg
- 自定义调试字符串可转换
- 自定义字符串可转换
- 等价
- 可散列
- NSObjectProtocol


---
source: https://developer.apple.com/documentation/SwiftUI/WKUserNotificationHostingController
crawled: 2025-12-02T17:45:07Z
---

# WKUserNotificationHostingController

**Class**

A WatchKit user notification interface controller that hosts a SwiftUI view hierarchy.

## Declaration

```swift
@MainActor @preconcurrency class WKUserNotificationHostingController<Body> where Body : View
```

## Overview

A [WKUserNotificationHostingController](WKUserNotificationHostingController.zh-Hans.md) presents and manages your app’s notification interface using SwiftUI views. You must subclass [WKUserNotificationHostingController](WKUserNotificationHostingController.zh-Hans.md) and override the [body](WKUserNotificationHostingController/body.zh-Hans.md) property to provide the set of SwiftUI views you want to display. In the storyboard of your watch app, specify the name of your custom class for your dynamic interactive interface.

## Creating a hosting controller object

- **init()**: Creates a notification hosting controller object that you can use to implement your notification interfaces using SwiftUI views.

## Getting the root view

- **body**: The root view of the view hierarchy to display for your notification interface.

## Configuring the notification

- **coalescedDescriptionFormat**: The format string to display when multiple notifications of the same type arrive simultaneously. If you specify a custom string, you can use the %d variable to reflect the number of notifications. If `nil` format will be the system default.
- **isInteractive**: If the notification should accept user input.
- **sashColor**: Color to use within the sash of the long look interface. If `nil` the sash will be the default system color.
- **subtitleColor**: The color to apply to the subtitle text displayed in the short look interface. If `nil` the text will be the default system color.
- **titleColor**: The color to apply to the text displayed in the sash. If `nil` the text will be the default system color.
- **wantsSashBlur**: If the sash should include a blur over the background.

## Displaying SwiftUI views in WatchKit

- **WKHostingController**: A WatchKit interface controller that hosts a SwiftUI view hierarchy.

## Inherits From

- WKUserNotificationInterfaceController

## Conforms To

- CVarArg
- CustomDebugStringConvertible
- CustomStringConvertible
- Equatable
- Hashable
- NSObjectProtocol

