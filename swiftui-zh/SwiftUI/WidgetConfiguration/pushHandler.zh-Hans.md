---
来源： https://developer.apple.com/documentation/SwiftUI/WidgetConfiguration/pushHandler(_:)
抓取时间： 2025-12-01T10:54:50Z
---

# pushHandler(_:)

**实例方法**

注册一个可以处理部件推送令牌更改的类型。

## 声明

```swift
@MainActor @preconcurrency func pushHandler(_ pushHandlerType: any WidgetPushHandler.Type) -> some WidgetConfiguration

```

## 参数

- **pushHandlerType**：可以处理推送令牌的对象类型，用于通过推送通知更新 widget。

## 概览

使用此选项可使此 widget 支持通过推送通知进行更新。

如果您有多个 widget 配置，可以选择在这些 widget 配置中使用相同的推送处理程序类型。

当 Widget 的推送配置发生变化时，每个独特的处理程序类型将被实例化，[doc://com.apple.documentation/documentation/WidgetKit/WidgetPushHandler/pushTokenDidChange(_:widgets:)] 将被调用。


---
source: https://developer.apple.com/documentation/SwiftUI/WidgetConfiguration/pushHandler(_:)
crawled: 2025-12-01T10:54:50Z
---

# pushHandler(_:)

**Instance Method**

Register a type that can handle push tokens changing for widgets.

## Declaration

```swift
@MainActor @preconcurrency func pushHandler(_ pushHandlerType: any WidgetPushHandler.Type) -> some WidgetConfiguration

```

## Parameters

- **pushHandlerType**: The type of the object that can handle push tokens you use to update the widget with push notifications.

## Overview

Use this to opt this widget into supporting updates via push notifications.

If you have multiple widget configurations, you can choose to use the same push handler type for those widget configurations.

When the push configuration of your widgets changes, each unique handler type will be instantiated and [doc://com.apple.documentation/documentation/WidgetKit/WidgetPushHandler/pushTokenDidChange(_:widgets:)] will be called.

