--- 来源：https://developer.apple.com/documentation/SwiftUI/NSViewControllerRepresentableContext/coordinator

抓取时间：2025-12-03T06:57:57Z

---

# 协调器

**实例属性**

用于将 AppKit 视图控制器的行为和状态传递给 SwiftUI 对象的一个对象。

## 声明

```swift
@MainActor @preconcurrency let coordinator: ViewController.Coordinator
```

## 讨论

协调器是您定义的自定义对象。更新视图控制器时，可以通过更新协调器的属性或调用相关方法来将更改传递给 SwiftUI。这些属性和方法的实现负责更新相应的 SwiftUI 值。例如，您可以在协调器中定义一个绑定到 SwiftUI 值的属性，如下面的代码示例所示。更改该属性会更新相应的 SwiftUI 变量的值。

```swift
class Coordinator: NSObject {
   @Binding var rating: Int
   init(rating: Binding<Int>) {
      $rating = rating
   }
}
```

要创建和配置自定义协调器，请实现 [NSViewControllerRepresentable](../NSViewControllerRepresentable.zh-Hans.md) 对象的 [makeCoordinator()](../NSViewControllerRepresentable/makeCoordinator.zh-Hans.md) 方法。

## 协调视图相关的交互

- **transaction**：当前事务。


---
source: https://developer.apple.com/documentation/SwiftUI/NSViewControllerRepresentableContext/coordinator
crawled: 2025-12-03T06:57:57Z
---

# coordinator

**Instance Property**

An object you use to communicate your AppKit view controller’s behavior and state out to SwiftUI objects.

## Declaration

```swift
@MainActor @preconcurrency let coordinator: ViewController.Coordinator
```

## Discussion

The coordinator is a custom object you define. When updating your view controller, communicate changes to SwiftUI by updating the properties of your coordinator, or by calling relevant methods to make those changes. The implementation of those properties and methods are responsible for updating the appropriate SwiftUI values. For example, you might define a property in your coordinator that binds to a SwiftUI value, as shown in the following code example. Changing the property updates the value of the corresponding SwiftUI variable.

```swift
class Coordinator: NSObject {
   @Binding var rating: Int
   init(rating: Binding<Int>) {
      $rating = rating
   }
}
```

To create and configure your custom coordinator, implement the [makeCoordinator()](../NSViewControllerRepresentable/makeCoordinator.zh-Hans.md) method of your [NSViewControllerRepresentable](../NSViewControllerRepresentable.zh-Hans.md) object.

## Coordinating view-related interactions

- **transaction**: The current transaction.

