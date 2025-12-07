---
来源： https://developer.apple.com/documentation/SwiftUI/WKExtensionDelegateAdaptor
抓取时间： 2025-12-02T17:20:40Z
---

# WKExtensionDelegateAdaptor

**Structure**

用于创建 WatchKit 扩展委托的属性包装器类型。

## 声明

```swift
@MainActor @preconcurrency @propertyWrapper struct WKExtensionDelegateAdaptor<DelegateType> where DelegateType : NSObject, DelegateType : WKExtensionDelegate
```

## 概览

要在使用 SwiftUI 生命周期的扩展中处理扩展委托回调，请定义符合 [doc://com.apple.documentation/documentation/WatchKit/WKExtensionDelegate] 协议的类型，并实现所需的委托方法。例如，您可以实现[doc://com.apple.documentation/documentation/WatchKit/WKExtensionDelegate/didRegisterForRemoteNotifications(withDeviceToken:)] 方法来处理远程通知注册：

```swift
class MyExtensionDelegate: NSObject, WKExtensionDelegate, ObservableObject {
    func didRegisterForRemoteNotifications(withDeviceToken: Data) {
        // Record the device token.
    }
}
```

然后在您的[App](App.zh-Hans.md) 声明中使用`WKExtensionDelegateAdaptor` 属性包装器来告诉 SwiftUI 委托类型：

```swift
@main
struct MyApp: App {
    @WKExtensionDelegateAdaptor private var extensionDelegate: MyExtensionDelegate

    var body: some Scene { ... }
}
```

SwiftUI 会实例化委托并调用委托的方法来响应生命周期事件。请仅在[App](App.zh-Hans.md) 声明中定义委托适配器，且仅在给定扩展中定义一次。如果声明多次，SwiftUI 将生成运行时错误。

如果您的扩展委托符合[doc://com.apple.documentation/documentation/Combine/ObservableObject] 协议（如上面的示例），那么 SwiftUI 就会将其创建的委托放入[Environment](Environment.zh-Hans.md) 中。您可以使用 [EnvironmentObject](EnvironmentObject.zh-Hans.md) 属性包装器从扩展中的任何场景或视图访问该委托：

```swift
@EnvironmentObject private var extensionDelegate: MyExtensionDelegate
```

这样，您就可以使用美元符号 (`$`)前缀来绑定您在委托中声明的已发布属性。更多信息，请参阅 [projectedValue](WKExtensionDelegateAdaptor/projectedValue.zh-Hans.md)。



## 创建委托适配器

- **init(_:)**：使用可观察委托创建 WatchKit 扩展委托适配器。

## 获取委托适配器

- **projectedValue**：被观察对象的投影，可提供其属性的绑定。
- **wrappedValue**：底层委托。

## targeting watchOS

- **WKApplicationDelegateAdaptor**：在 `App` 中使用的属性包装器，用于提供 WatchKit 的委托。

## 符合

- 动态属性
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/WKExtensionDelegateAdaptor
crawled: 2025-12-02T17:20:40Z
---

# WKExtensionDelegateAdaptor

**Structure**

A property wrapper type that you use to create a WatchKit extension delegate.

## Declaration

```swift
@MainActor @preconcurrency @propertyWrapper struct WKExtensionDelegateAdaptor<DelegateType> where DelegateType : NSObject, DelegateType : WKExtensionDelegate
```

## Overview

To handle extension delegate callbacks in an extension that uses the SwiftUI life cycle, define a type that conforms to the [doc://com.apple.documentation/documentation/WatchKit/WKExtensionDelegate] protocol, and implement the delegate methods that you need. For example, you can implement the [doc://com.apple.documentation/documentation/WatchKit/WKExtensionDelegate/didRegisterForRemoteNotifications(withDeviceToken:)] method to handle remote notification registration:

```swift
class MyExtensionDelegate: NSObject, WKExtensionDelegate, ObservableObject {
    func didRegisterForRemoteNotifications(withDeviceToken: Data) {
        // Record the device token.
    }
}
```

Then use the `WKExtensionDelegateAdaptor` property wrapper inside your [App](App.zh-Hans.md) declaration to tell SwiftUI about the delegate type:

```swift
@main
struct MyApp: App {
    @WKExtensionDelegateAdaptor private var extensionDelegate: MyExtensionDelegate

    var body: some Scene { ... }
}
```

SwiftUI instantiates the delegate and calls the delegate’s methods in response to life cycle events. Define the delegate adaptor only in your [App](App.zh-Hans.md) declaration, and only once for a given extension. If you declare it more than once, SwiftUI generates a runtime error.

If your extension delegate conforms to the [doc://com.apple.documentation/documentation/Combine/ObservableObject] protocol, as in the example above, then SwiftUI puts the delegate it creates into the [Environment](Environment.zh-Hans.md). You can access the delegate from any scene or view in your extension using the [EnvironmentObject](EnvironmentObject.zh-Hans.md) property wrapper:

```swift
@EnvironmentObject private var extensionDelegate: MyExtensionDelegate
```

This enables you to use the dollar sign (`$`) prefix to get a binding to published properties that you declare in the delegate. For more information, see [projectedValue](WKExtensionDelegateAdaptor/projectedValue.zh-Hans.md).



## Creating a delegate adaptor

- **init(_:)**: Creates a WatchKit extension delegate adaptor using an observable delegate.

## Getting the delegate adaptor

- **projectedValue**: A projection of the observed object that provides bindings to its properties.
- **wrappedValue**: The underlying delegate.

## Targeting watchOS

- **WKApplicationDelegateAdaptor**: A property wrapper that is used in `App` to provide a delegate from WatchKit.

## Conforms To

- DynamicProperty
- Sendable
- SendableMetatype

