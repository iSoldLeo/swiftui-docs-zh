---
来源： https://developer.apple.com/documentation/SwiftUI/UIApplicationDelegateAdaptor/projectedValue
抓取时间：2025-12-03T05:30:50Z
---

# 预计值

**实例属性**

被观察对象的投影，提供其属性的绑定。

## 声明

```swift
@MainActor @preconcurrency var projectedValue: ObservedObject<DelegateType>.Wrapper { get }
```

## 讨论

使用预测值可以绑定到代表发布的值。访问预测值的方法是在代表实例的名称前加上美元符号（`$`）。例如，您可以在应用程序委托中发布一个布尔值：

```swift
class MyAppDelegate: NSObject, UIApplicationDelegate, ObservableObject {
    @Published var isEnabled = false

    // ...
}
```

如果您使用[App](../App.zh-Hans.md) 属性包装器在[App](../App.zh-Hans.md) 中声明委托，您就可以从环境中获取 SwiftUI 实例化的委托，并从应用程序中的任何视图访问与委托发布值的绑定：

```swift
struct MyView: View {
    @EnvironmentObject private var appDelegate: MyAppDelegate

    var body: some View {
        Toggle("Enabled", isOn: $appDelegate.isEnabled)
    }
}
```

## 获取委托适配器

- **wrappedValue**：底层应用程序委托。


---
source: https://developer.apple.com/documentation/SwiftUI/UIApplicationDelegateAdaptor/projectedValue
crawled: 2025-12-03T05:30:50Z
---

# projectedValue

**Instance Property**

A projection of the observed object that provides bindings to its properties.

## Declaration

```swift
@MainActor @preconcurrency var projectedValue: ObservedObject<DelegateType>.Wrapper { get }
```

## Discussion

Use the projected value to get a binding to a value that the delegate publishes. Access the projected value by prefixing the name of the delegate instance with a dollar sign (`$`). For example, you might publish a Boolean value in your application delegate:

```swift
class MyAppDelegate: NSObject, UIApplicationDelegate, ObservableObject {
    @Published var isEnabled = false

    // ...
}
```

If you declare the delegate in your [App](../App.zh-Hans.md) using the [UIApplicationDelegateAdaptor](../UIApplicationDelegateAdaptor.zh-Hans.md) property wrapper, you can get the delegate that SwiftUI instantiates from the environment and access a binding to its published values from any view in your app:

```swift
struct MyView: View {
    @EnvironmentObject private var appDelegate: MyAppDelegate

    var body: some View {
        Toggle("Enabled", isOn: $appDelegate.isEnabled)
    }
}
```

## Getting the delegate adaptor

- **wrappedValue**: The underlying app delegate.

