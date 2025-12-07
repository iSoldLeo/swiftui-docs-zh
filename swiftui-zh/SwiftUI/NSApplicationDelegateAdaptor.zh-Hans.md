---
来源： https://developer.apple.com/documentation/SwiftUI/NSApplicationDelegateAdaptor
抓取时间： 2025-12-02T17:20:39Z
---

# NSApplicationDelegateAdaptor

**Structure**

用于创建 AppKit 应用程序委托的属性包装器类型。

## 声明

```swift
@MainActor @preconcurrency @propertyWrapper struct NSApplicationDelegateAdaptor<DelegateType> where DelegateType : NSObject, DelegateType : NSApplicationDelegate
```

## 概览

要在使用 SwiftUI 生命周期的应用程序中处理应用程序委托回调，请定义符合 [doc://com.apple.documentation/documentation/AppKit/NSApplicationDelegate] 协议的类型，并实现所需的委托方法。例如，您可以实现[doc://com.apple.documentation/documentation/AppKit/NSApplicationDelegate/application(_:didRegisterForRemoteNotificationsWithDeviceToken:)] 方法来处理远程通知注册：

```swift
class MyAppDelegate: NSObject, NSApplicationDelegate, ObservableObject {
    func application(
        _ application: NSApplication,
        didRegisterForRemoteNotificationsWithDeviceToken deviceToken: Data
    ) {
        // Record the device token.
    }
}
```

然后在您的[App](App.zh-Hans.md) 声明中使用`NSApplicationDelegateAdaptor` 属性包装器来告诉 SwiftUI 委托类型：

```swift
@main
struct MyApp: App {
    @NSApplicationDelegateAdaptor private var appDelegate: MyAppDelegate

    var body: some Scene { ... }
}
```

SwiftUI 会实例化委托并调用委托的方法来响应生命周期事件。请仅在[App](App.zh-Hans.md) 声明中定义委托适配器，且仅在给定应用程序中定义一次。如果声明多次，SwiftUI 将生成运行时错误。

如果您的应用程序委托符合[doc://com.apple.documentation/documentation/Combine/ObservableObject] 协议（如上面的示例），那么 SwiftUI 就会将其创建的委托放入[Environment](Environment.zh-Hans.md) 中。您可以使用 [EnvironmentObject](EnvironmentObject.zh-Hans.md) 属性包装器从应用程序中的任何场景或视图访问该委托：

```swift
@EnvironmentObject private var appDelegate: MyAppDelegate
```

这样，您就可以使用美元符号 (`$`)前缀来绑定您在委托中声明的已发布属性。更多信息，请参阅 [projectedValue](NSApplicationDelegateAdaptor/projectedValue.zh-Hans.md)。



## 创建委托适配器

- **init(_:)**：使用可观察委托创建 AppKit 应用程序委托适配器。

## 获取委托适配器

- **projectedValue**：被观察对象的投影，为其属性提供绑定。
- **wrappedValue**：底层委托。

## 符合

- 动态属性
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/NSApplicationDelegateAdaptor
crawled: 2025-12-02T17:20:39Z
---

# NSApplicationDelegateAdaptor

**Structure**

A property wrapper type that you use to create an AppKit app delegate.

## Declaration

```swift
@MainActor @preconcurrency @propertyWrapper struct NSApplicationDelegateAdaptor<DelegateType> where DelegateType : NSObject, DelegateType : NSApplicationDelegate
```

## Overview

To handle app delegate callbacks in an app that uses the SwiftUI life cycle, define a type that conforms to the [doc://com.apple.documentation/documentation/AppKit/NSApplicationDelegate] protocol, and implement the delegate methods that you need. For example, you can implement the [doc://com.apple.documentation/documentation/AppKit/NSApplicationDelegate/application(_:didRegisterForRemoteNotificationsWithDeviceToken:)] method to handle remote notification registration:

```swift
class MyAppDelegate: NSObject, NSApplicationDelegate, ObservableObject {
    func application(
        _ application: NSApplication,
        didRegisterForRemoteNotificationsWithDeviceToken deviceToken: Data
    ) {
        // Record the device token.
    }
}
```

Then use the `NSApplicationDelegateAdaptor` property wrapper inside your [App](App.zh-Hans.md) declaration to tell SwiftUI about the delegate type:

```swift
@main
struct MyApp: App {
    @NSApplicationDelegateAdaptor private var appDelegate: MyAppDelegate

    var body: some Scene { ... }
}
```

SwiftUI instantiates the delegate and calls the delegate’s methods in response to life cycle events. Define the delegate adaptor only in your [App](App.zh-Hans.md) declaration, and only once for a given app. If you declare it more than once, SwiftUI generates a runtime error.

If your app delegate conforms to the [doc://com.apple.documentation/documentation/Combine/ObservableObject] protocol, as in the example above, then SwiftUI puts the delegate it creates into the [Environment](Environment.zh-Hans.md). You can access the delegate from any scene or view in your app using the [EnvironmentObject](EnvironmentObject.zh-Hans.md) property wrapper:

```swift
@EnvironmentObject private var appDelegate: MyAppDelegate
```

This enables you to use the dollar sign (`$`) prefix to get a binding to published properties that you declare in the delegate. For more information, see [projectedValue](NSApplicationDelegateAdaptor/projectedValue.zh-Hans.md).



## Creating a delegate adaptor

- **init(_:)**: Creates an AppKit app delegate adaptor using an observable delegate.

## Getting the delegate adaptor

- **projectedValue**: A projection of the observed object that provides bindings to its properties.
- **wrappedValue**: The underlying delegate.

## Conforms To

- DynamicProperty
- Sendable
- SendableMetatype

