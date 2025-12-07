--- 来源：https://developer.apple.com/documentation/SwiftUI/WKInterfaceObjectRepresentable/dismantleWKInterfaceObject(_:coordinator:)

抓取时间：2025-12-01T10:28:18Z

---

# dismantleWKInterfaceObject(_:coordinator:)

**类型方法**

清理已呈现的 WatchKit 界面对象（及其协调器），以便将其移除。

## 声明

```swift
@MainActor @preconcurrency static func dismantleWKInterfaceObject(_ wkInterfaceObject: Self.WKInterfaceObjectType, coordinator: Self.Coordinator)
```

## 参数

- **wkInterfaceObject**：您的自定义界面对象。

- **coordinator**：您用于将更改反馈给 SwiftUI 的自定义协调器实例。如果您未使用自定义协调器，系统将提供一个默认实例。

## 讨论

使用此方法可以对自定义界面对象执行额外的清理工作。例如，您可以使用此方法移除观察者或更新 SwiftUI 界面的其他部分。


---
source: https://developer.apple.com/documentation/SwiftUI/WKInterfaceObjectRepresentable/dismantleWKInterfaceObject(_:coordinator:)
crawled: 2025-12-01T10:28:18Z
---

# dismantleWKInterfaceObject(_:coordinator:)

**Type Method**

Cleans up the presented WatchKit interface object (and its coordinator) in anticipation of their removal.

## Declaration

```swift
@MainActor @preconcurrency static func dismantleWKInterfaceObject(_ wkInterfaceObject: Self.WKInterfaceObjectType, coordinator: Self.Coordinator)
```

## Parameters

- **wkInterfaceObject**: Your custom interface object.
- **coordinator**: The custom coordinator instance you use to communicate changes back to SwiftUI. If you do not use a custom coordinator, the system provides a default instance.

## Discussion

Use this method to perform additional clean-up work related to your custom interface object. For example, you might use this method to remove observers or update other parts of your SwiftUI interface.

