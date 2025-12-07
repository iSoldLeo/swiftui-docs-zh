---
来源： https://developer.apple.com/documentation/SwiftUI/NSViewControllerRepresentable/makeCoordinator()
抓取时间： 2025-12-01T10:26:55Z
---

# makeCoordinator()

**实例方法**

创建自定义对象，用于将视图控制器中的更改传达给 SwiftUI 界面的其他部分。

## 声明

```swift
@MainActor @preconcurrency func makeCoordinator() -> Self.Coordinator
```

## 讨论

如果视图控制器的更改可能会影响应用程序的其他部分，请执行此方法。在您的实现中，创建一个可以与界面其他部分通信的自定义 Swift 实例。例如，您可以提供一个实例，将其变量绑定到 SwiftUI 属性，使两者保持同步。如果视图控制器不与应用程序的其他部分交互，则无需提供协调器。

SwiftUI 在调用[makeNSViewController(context:)](makeNSViewController_context.zh-Hans.md) 方法之前会调用该方法。在调用可表示实例的其他方法时，系统会直接或作为上下文结构的一部分提供协调器实例。

## 提供自定义协调器对象

- **Coordinator**：用于与视图控制器协调的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/NSViewControllerRepresentable/makeCoordinator()
crawled: 2025-12-01T10:26:55Z
---

# makeCoordinator()

**Instance Method**

Creates the custom object that you use to communicate changes from your view controller to other parts of your SwiftUI interface.

## Declaration

```swift
@MainActor @preconcurrency func makeCoordinator() -> Self.Coordinator
```

## Discussion

Implement this method if changes to your view controller might affect other parts of your app. In your implementation, create a custom Swift instance that can communicate with other parts of your interface. For example, you might provide an instance that binds its variables to SwiftUI properties, causing the two to remain synchronized. If your view controller doesn’t interact with other parts of your app, providing a coordinator is unnecessary.

SwiftUI calls this method before calling the [makeNSViewController(context:)](makeNSViewController_context.zh-Hans.md) method. The system provides your coordinator instance either directly or as part of a context structure when calling the other methods of your representable instance.

## Providing a custom coordinator object

- **Coordinator**: A type to coordinate with the view controller.

