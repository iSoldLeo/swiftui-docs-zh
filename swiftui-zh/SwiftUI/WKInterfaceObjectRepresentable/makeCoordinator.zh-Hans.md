--- 来源：https://developer.apple.com/documentation/SwiftUI/WKInterfaceObjectRepresentable/makeCoordinator()

抓取时间：2025-12-03T05:39:11Z

---

# makeCoordinator()

**实例方法**

创建自定义实例，用于将界面对象的更改传递给 SwiftUI 界面的其他部分。

## 声明

```swift
@MainActor @preconcurrency func makeCoordinator() -> Self.Coordinator
```

## 说明

如果界面对象的更改可能会影响应用程序的其他部分，请实现此方法。在实现中，创建一个可以与界面其他部分通信的自定义 Swift 实例。例如，您可以提供一个将其变量绑定到 SwiftUI 属性的实例，从而使两者保持同步。如果界面对象不与应用程序的其他部分交互，则无需提供协调器。

SwiftUI 会在调用 [makeWKInterfaceObject(context:)](makeWKInterfaceObject_context.zh-Hans.md) 方法之前调用此方法。系统会在调用可表示实例的其他方法时，直接或作为上下文结构的一部分提供您的协调器。

## 提供自定义协调器对象

- **Coordinator**：用于与 WatchKit 接口对象协调的类型。

- **WKInterfaceObjectType**：要呈现的 WatchKit 接口对象的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/WKInterfaceObjectRepresentable/makeCoordinator()
crawled: 2025-12-03T05:39:11Z
---

# makeCoordinator()

**Instance Method**

Creates the custom instance that you use to communicate changes from your interface object to other parts of your SwiftUI interface.

## Declaration

```swift
@MainActor @preconcurrency func makeCoordinator() -> Self.Coordinator
```

## Discussion

Implement this method if changes to your interface object might affect other parts of your app. In your implementation, create a custom Swift instance that can communicate with other parts of your interface. For example, you might provide an instance that binds its variables to SwiftUI properties, causing the two to remain synchronized. If your interface object doesn’t interact with other parts of your app, providing a coordinator is unnecessary.

SwiftUI calls this method before calling the [makeWKInterfaceObject(context:)](makeWKInterfaceObject_context.zh-Hans.md) method. The system provides your coordinator either directly or as part of a context structure when calling the other methods of your representable instance.

## Providing a custom coordinator object

- **Coordinator**: A type to coordinate with the WatchKit interface object.
- **WKInterfaceObjectType**: The type of WatchKit interface object to be presented.

