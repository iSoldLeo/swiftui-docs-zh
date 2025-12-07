--- 来源：https://developer.apple.com/documentation/SwiftUI/UIApplicationDelegateAdaptor
抓取时间：2025-12-02T17:20:38Z

---

# UIApplicationDelegateAdaptor

**Structure**

用于创建 UIKit 应用委托的属性包装类型。

## 声明

```swift
@MainActor @preconcurrency @propertyWrapper struct UIApplicationDelegateAdaptor<DelegateType> where DelegateType : NSObject, DelegateType : UIApplicationDelegate
```

## 概述

要在使用 SwiftUI 生命周期的应用中处理应用委托回调，请定义一个符合 [doc://com.apple.documentation/documentation/UIKit/UIApplicationDelegate] 协议的类型，并实现所需的委托方法。例如，您可以实现 [doc://com.apple.documentation/documentation/UIKit/UIApplicationDelegate/application(_:didRegisterForRemoteNotificationsWithDeviceToken:)] 方法来处理远程通知注册：

```swift
class MyAppDelegate: NSObject, UIApplicationDelegate, ObservableObject {
    func application(
        _ application: UIApplication,
        didRegisterForRemoteNotificationsWithDeviceToken deviceToken: Data
    ) {
        // Record the device token.
    }
}
```

然后在 [App](App.zh-Hans.md) 声明中使用 `UIApplicationDelegateAdaptor` 属性包装器来告知 SwiftUI 委托类型：

```swift
@main
struct MyApp: App {
    @UIApplicationDelegateAdaptor private var appDelegate: MyAppDelegate

    var body: some Scene { ... }
}
```

SwiftUI 会实例化委托并根据生命周期事件调用委托的方法。委托适配器只能在 [App](App.zh-Hans.md) 声明中定义，并且对于给定的应用只能定义一次。如果多次声明，SwiftUI 会生成运行时错误。

如果您的应用委托遵循 [doc://com.apple.documentation/documentation/Combine/ObservableObject] 协议（如上例所示），则 SwiftUI 会将其创建的委托放入 [Environment](Environment.zh-Hans.md) 中。您可以使用属性包装器 [EnvironmentObject](EnvironmentObject.zh-Hans.md) 从应用程序中的任何场景或视图访问委托：

```swift
@EnvironmentObject private var appDelegate: MyAppDelegate
```

这使您可以使用美元符号 (`$`) 前缀来绑定到您在委托中声明的已发布属性。有关更多信息，请参阅 [projectedValue](UIApplicationDelegateAdaptor/projectedValue.zh-Hans.md)。

### 场景委托

一些 iOS 应用会定义一个 [doc://com.apple.documentation/documentation/UIKit/UIWindowSceneDelegate] 来处理基于场景的事件，例如应用快捷方式：

```swift
class MySceneDelegate: NSObject, UIWindowSceneDelegate, ObservableObject {
    func windowScene(
        _ windowScene: UIWindowScene,
        performActionFor shortcutItem: UIApplicationShortcutItem
    ) async -> Bool {
        // Do something with the shortcut...

        return true
    }
}
```

您可以通过在应用委托中通过 [doc://com.apple.documentation/documentation/UIKit/UIApplicationDelegate/application(_:configurationForConnecting:options:)] 方法返回场景委托的类型，将这种委托提供给 SwiftUI 应用：

```swift
extension MyAppDelegate {
    func application(
        _ application: UIApplication,
        configurationForConnecting connectingSceneSession: UISceneSession,
        options: UIScene.ConnectionOptions
    ) -> UISceneConfiguration {

        let configuration = UISceneConfiguration(
                                name: nil,
                                sessionRole: connectingSceneSession.role)
        if connectingSceneSession.role == .windowApplication {
            configuration.delegateClass = MySceneDelegate.self
        }
        return configuration
    }
}
```

配置 [doc://com.apple.documentation/documentation/UIKit/UISceneConfiguration] 实例时，您只需指定委托类，无需指定场景类或故事板。SwiftUI 会创建并管理委托实例，并向其发送任何相关的委托回调。

与应用委托一样，如果您将场景委托设为可观察对象，SwiftUI 会自动将其放入 [Environment](Environment.zh-Hans.md) 中，您可以通过 [EnvironmentObject](EnvironmentObject.zh-Hans.md) 属性包装器访问它，并创建对其已发布属性的绑定。

## 创建委托适配器

- **init(_:)**：使用可观察委托创建 UIKit 应用委托适配器。

## 获取委托适配器

- **projectedValue**：被观察对象的投影，提供对其属性的绑定。

- **wrappedValue**：底层应用委托。

## 目标平台：iOS 和 iPadOS

- **UILaunchScreen**：应用启动时显示的用户界面。

- **UILaunchScreens**：应用响应不同 URL 方案启动时显示的用户界面。

## 符合以下规范：

- DynamicProperty

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/UIApplicationDelegateAdaptor
crawled: 2025-12-02T17:20:38Z
---

# UIApplicationDelegateAdaptor

**Structure**

A property wrapper type that you use to create a UIKit app delegate.

## Declaration

```swift
@MainActor @preconcurrency @propertyWrapper struct UIApplicationDelegateAdaptor<DelegateType> where DelegateType : NSObject, DelegateType : UIApplicationDelegate
```

## Overview

To handle app delegate callbacks in an app that uses the SwiftUI life cycle, define a type that conforms to the [doc://com.apple.documentation/documentation/UIKit/UIApplicationDelegate] protocol, and implement the delegate methods that you need. For example, you can implement the [doc://com.apple.documentation/documentation/UIKit/UIApplicationDelegate/application(_:didRegisterForRemoteNotificationsWithDeviceToken:)] method to handle remote notification registration:

```swift
class MyAppDelegate: NSObject, UIApplicationDelegate, ObservableObject {
    func application(
        _ application: UIApplication,
        didRegisterForRemoteNotificationsWithDeviceToken deviceToken: Data
    ) {
        // Record the device token.
    }
}
```

Then use the `UIApplicationDelegateAdaptor` property wrapper inside your [App](App.zh-Hans.md) declaration to tell SwiftUI about the delegate type:

```swift
@main
struct MyApp: App {
    @UIApplicationDelegateAdaptor private var appDelegate: MyAppDelegate

    var body: some Scene { ... }
}
```

SwiftUI instantiates the delegate and calls the delegate’s methods in response to life cycle events. Define the delegate adaptor only in your [App](App.zh-Hans.md) declaration, and only once for a given app. If you declare it more than once, SwiftUI generates a runtime error.

If your app delegate conforms to the [doc://com.apple.documentation/documentation/Combine/ObservableObject] protocol, as in the example above, then SwiftUI puts the delegate it creates into the [Environment](Environment.zh-Hans.md). You can access the delegate from any scene or view in your app using the [EnvironmentObject](EnvironmentObject.zh-Hans.md) property wrapper:

```swift
@EnvironmentObject private var appDelegate: MyAppDelegate
```

This enables you to use the dollar sign (`$`) prefix to get a binding to published properties that you declare in the delegate. For more information, see [projectedValue](UIApplicationDelegateAdaptor/projectedValue.zh-Hans.md).



### Scene delegates

Some iOS apps define a [doc://com.apple.documentation/documentation/UIKit/UIWindowSceneDelegate] to handle scene-based events, like app shortcuts:

```swift
class MySceneDelegate: NSObject, UIWindowSceneDelegate, ObservableObject {
    func windowScene(
        _ windowScene: UIWindowScene,
        performActionFor shortcutItem: UIApplicationShortcutItem
    ) async -> Bool {
        // Do something with the shortcut...

        return true
    }
}
```

You can provide this kind of delegate to a SwiftUI app by returning the scene delegate’s type from the [doc://com.apple.documentation/documentation/UIKit/UIApplicationDelegate/application(_:configurationForConnecting:options:)] method inside your app delegate:

```swift
extension MyAppDelegate {
    func application(
        _ application: UIApplication,
        configurationForConnecting connectingSceneSession: UISceneSession,
        options: UIScene.ConnectionOptions
    ) -> UISceneConfiguration {

        let configuration = UISceneConfiguration(
                                name: nil,
                                sessionRole: connectingSceneSession.role)
        if connectingSceneSession.role == .windowApplication {
            configuration.delegateClass = MySceneDelegate.self
        }
        return configuration
    }
}
```

When you configure the [doc://com.apple.documentation/documentation/UIKit/UISceneConfiguration] instance, you only need to indicate the delegate class, and not a scene class or storyboard. SwiftUI creates and manages the delegate instance, and sends it any relevant delegate callbacks.

As with the app delegate, if you make your scene delegate an observable object, SwiftUI automatically puts it in the [Environment](Environment.zh-Hans.md), from where you can access it with the [EnvironmentObject](EnvironmentObject.zh-Hans.md) property wrapper, and create bindings to its published properties.

## Creating a delegate adaptor

- **init(_:)**: Creates a UIKit app delegate adaptor using an observable delegate.

## Getting the delegate adaptor

- **projectedValue**: A projection of the observed object that provides bindings to its properties.
- **wrappedValue**: The underlying app delegate.

## Targeting iOS and iPadOS

- **UILaunchScreen**: The user interface to show while an app launches.
- **UILaunchScreens**: The user interfaces to show while an app launches in response to different URL schemes.

## Conforms To

- DynamicProperty
- Sendable
- SendableMetatype

