--- 来源：https://developer.apple.com/documentation/SwiftUI/WKInterfaceObjectRepresentable/Coordinator

抓取时间：2025-12-03T05:39:12Z

---

# 协调器

**关联类型**

用于与 WatchKit 界面对象进行协调的类型。

## 声明

```swift
associatedtype Coordinator = Void
```

## 提供自定义协调器对象

- **makeCoordinator()**：创建自定义实例，用于将界面对象的更改传递给 SwiftUI 界面的其他部分。

- **WKInterfaceObjectType**：要呈现的 WatchKit 界面对象的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/WKInterfaceObjectRepresentable/Coordinator
crawled: 2025-12-03T05:39:12Z
---

# Coordinator

**Associated Type**

A type to coordinate with the WatchKit interface object.

## Declaration

```swift
associatedtype Coordinator = Void
```

## Providing a custom coordinator object

- **makeCoordinator()**: Creates the custom instance that you use to communicate changes from your interface object to other parts of your SwiftUI interface.
- **WKInterfaceObjectType**: The type of WatchKit interface object to be presented.

