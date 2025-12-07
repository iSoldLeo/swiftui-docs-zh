--- 来源：https://developer.apple.com/documentation/SwiftUI/NSApplicationDelegateAdaptor/init(_:)

抓取时间：2025-12-01T10:19:58Z

---

# init(_:)

**Initializer**

使用可观察委托创建 AppKit 应用委托适配器。

## 声明

```swift
@MainActor @preconcurrency init(_ delegateType: DelegateType.Type = DelegateType.self)
```

## 参数

- **delegateType**：您在应用中定义的应用委托类型，它符合 [doc://com.apple.documentation/documentation/AppKit/NSApplicationDelegate] 和 [doc://com.apple.documentation/documentation/Observation/Observable] 协议。

## 讨论

通过在声明内部使用属性包装器创建属性来间接调用此初始化器：



SwiftUI 初始化委托并管理其生命周期，根据需要调用它来处理应用程序委托回调。

当您的应用程序委托符合协议时，SwiftUI 会调用此方法。在这种情况下，SwiftUI 会自动将委托放置在 DL_0006 中。您可以使用属性包装器 [Environment](../Environment.zh-Hans.md) 从应用程序的任何场景或视图访问此类委托：

```swift
@Environment(MyAppDelegate.self) private var appDelegate
```

如果您的委托不可观察，SwiftUI 将调用 [doc://com.apple.SwiftUI/documentation/SwiftUI/NSApplicationDelegateAdaptor/init(_:)-67u91] 初始化器而不是此初始化器，并且不会将委托实例放入环境中。


---
source: https://developer.apple.com/documentation/SwiftUI/NSApplicationDelegateAdaptor/init(_:)
crawled: 2025-12-01T10:19:58Z
---

# init(_:)

**Initializer**

Creates an AppKit app delegate adaptor using an observable delegate.

## Declaration

```swift
@MainActor @preconcurrency init(_ delegateType: DelegateType.Type = DelegateType.self)
```

## Parameters

- **delegateType**: The type of application delegate that you define in your app, which conforms to the [doc://com.apple.documentation/documentation/AppKit/NSApplicationDelegate] and [doc://com.apple.documentation/documentation/Observation/Observable] protocols.

## Discussion

Call this initializer indirectly by creating a property with the [NSApplicationDelegateAdaptor](../NSApplicationDelegateAdaptor.zh-Hans.md) property wrapper from inside your [App](../App.zh-Hans.md) declaration:

```swift
@main
struct MyApp: App {
    @NSApplicationDelegateAdaptor private var appDelegate: MyAppDelegate

    var body: some Scene { ... }
}
```

SwiftUI initializes the delegate and manages its lifetime, calling it as needed to handle application delegate callbacks.

SwiftUI invokes this method when your app delegate conforms to the [doc://com.apple.documentation/documentation/Observation/Observable] protocol. In this case, SwiftUI automatically places the delegate in the [Environment](../Environment.zh-Hans.md). You can access such a delegate from any scene or view in your app using the [Environment](../Environment.zh-Hans.md) property wrapper:

```swift
@Environment(MyAppDelegate.self) private var appDelegate
```

If your delegate isn’t observable, SwiftUI invokes the [doc://com.apple.SwiftUI/documentation/SwiftUI/NSApplicationDelegateAdaptor/init(_:)-67u91] initializer rather than this one, and doesn’t put the delegate instance in the environment.

