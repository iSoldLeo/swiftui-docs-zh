--- 来源：https://developer.apple.com/documentation/SwiftUI/WKInterfaceObjectRepresentable/updateWKInterfaceObject(_:context:)

抓取时间：2025-12-03T05:39:03Z

---

# updateWKInterfaceObject(_:context:)

**实例方法**

将呈现的 WatchKit 界面对象（及其协调器）更新到最新配置。

## 声明

```swift
@MainActor @preconcurrency func updateWKInterfaceObject(_ wkInterfaceObject: Self.WKInterfaceObjectType, context: Self.Context)
```

## 参数

- **wkInterfaceObject**：您的自定义界面对象。

- **context**：包含系统当前状态信息的上下文结构。

## 说明

当您的应用状态发生变化时，SwiftUI 会更新受这些变化影响的界面部分。SwiftUI 会针对影响相应界面对象的任何更改调用此方法。使用此方法更新对象的配置，使其与 `context` 参数中提供的新状态信息相匹配。

## 创建和更新接口对象

- **makeWKInterfaceObject(context:)**：创建 WatchKit 接口对象并配置其初始状态。

- **WKInterfaceObjectRepresentable.Context**


---
source: https://developer.apple.com/documentation/SwiftUI/WKInterfaceObjectRepresentable/updateWKInterfaceObject(_:context:)
crawled: 2025-12-03T05:39:03Z
---

# updateWKInterfaceObject(_:context:)

**Instance Method**

Updates the presented WatchKit interface object (and its coordinator) to the latest configuration.

## Declaration

```swift
@MainActor @preconcurrency func updateWKInterfaceObject(_ wkInterfaceObject: Self.WKInterfaceObjectType, context: Self.Context)
```

## Parameters

- **wkInterfaceObject**: Your custom interface object.
- **context**: A context structure containing information about the current state of the system.

## Discussion

When the state of your app changes, SwiftUI updates the portions of your interface affected by those changes. SwiftUI calls this method for any changes affecting the corresponding interface object. Use this method to update the configuration of your object to match the new state information provided in the `context` parameter.

## Creating and updating the interface object

- **makeWKInterfaceObject(context:)**: Creates a WatchKit interface object and configures its initial state.
- **WKInterfaceObjectRepresentable.Context**

