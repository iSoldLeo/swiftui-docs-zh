--- 来源：https://developer.apple.com/documentation/SwiftUI/ControlWidgetConfiguration/pushHandler(_:)

抓取时间：2025-12-01T10:55:09Z

---

# pushHandler(_:)

**实例方法**

注册一个可以处理此类型控件推送令牌更改的类型。

## 声明

```swift
@MainActor @preconcurrency func pushHandler(_ pushHandlerType: any ControlPushHandler.Type) -> some ControlWidgetConfiguration

```

## 参数

- **pushHandlerType**：用于处理推送令牌的对象类型，用于通过推送通知更新控件。

## 概述

使用此方法可让您的控件启用推送通知。

如果您有多种控件类型，可以选择为这些控件类型使用相同的推送处理程序类型。

当控件的推送配置发生更改时，将实例化每个处理程序类型，并调用 [doc://com.apple.documentation/documentation/WidgetKit/ControlPushHandler/pushTokensDidChange(controls:)]。


---
source: https://developer.apple.com/documentation/SwiftUI/ControlWidgetConfiguration/pushHandler(_:)
crawled: 2025-12-01T10:55:09Z
---

# pushHandler(_:)

**Instance Method**

Register a type that can handle push tokens changing for controls of this type.

## Declaration

```swift
@MainActor @preconcurrency func pushHandler(_ pushHandlerType: any ControlPushHandler.Type) -> some ControlWidgetConfiguration

```

## Parameters

- **pushHandlerType**: The type of the object that can handle push tokens you use to update the control with push notifications.

## Overview

Use this to opt your control into using push notifications.

If you have multiple control types, you can choose to use the same push handler type for those control types.

When the push configuration of your controls changes, each handler type will be instantiated and [doc://com.apple.documentation/documentation/WidgetKit/ControlPushHandler/pushTokensDidChange(controls:)] will be called.

