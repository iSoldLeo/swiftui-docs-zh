--- 来源：https://developer.apple.com/documentation/SwiftUI/WKInterfaceObjectRepresentable/WKInterfaceObjectType
抓取时间：2025-12-03T05:39:12Z

---

# WKInterfaceObjectType

**关联类型**

要呈现的 WatchKit 界面对象的类型。

## 声明

```swift
associatedtype WKInterfaceObjectType : WKInterfaceObject
```

## 提供自定义协调器对象

- **makeCoordinator()**：创建自定义实例，用于将界面对象的更改传递给 SwiftUI 界面的其他部分。

- **Coordinator**：用于与 WatchKit 界面对象协调的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/WKInterfaceObjectRepresentable/WKInterfaceObjectType
crawled: 2025-12-03T05:39:12Z
---

# WKInterfaceObjectType

**Associated Type**

The type of WatchKit interface object to be presented.

## Declaration

```swift
associatedtype WKInterfaceObjectType : WKInterfaceObject
```

## Providing a custom coordinator object

- **makeCoordinator()**: Creates the custom instance that you use to communicate changes from your interface object to other parts of your SwiftUI interface.
- **Coordinator**: A type to coordinate with the WatchKit interface object.

