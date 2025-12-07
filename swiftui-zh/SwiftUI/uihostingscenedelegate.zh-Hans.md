---
来源： https://developer.apple.com/documentation/swiftui/uihostingscenedelegate
抓取时间： 2025-12-04T13:47:22Z
---

# UIHostingSceneDelegate

**Protocol**

扩展 `UIKit/UISceneDelegate` 以桥接 SwiftUI 场景。

## 声明

```swift
protocol UIHostingSceneDelegate : UISceneDelegate
```

## 概览

在符合要求的类的静态 `rootScene` 属性中声明您希望从 UIKit 激活的任何 SwiftUI 场景：

```swift
class HostingSceneDelegate: UIHostingSceneDelegate {
    static var rootScene: some Scene {
        WindowGroup(id: "swiftui-window") {
            ContentView()
        }
    }

    // Add UISceneDelegate lifecycle callbacks here
}
```

使用符合[UIHostingSceneDelegate](UIHostingSceneDelegate.zh-Hans.md) 的类通过其 ID 或`UISceneSessionActivationRequest` 的显示值激活场景：

```swift
if let requestWithID = UISceneSessionActivationRequest(
    hostingDelegateClass: HostingSceneDelegate.self,
    id: "swiftui-window"
) {
    UIApplication.shared.activateSceneSession(for: requestWithID)
}

if let requestWithData = UISceneSessionActivationRequest(
    hostingDelegateClass: HostingSceneDelegate.self,
    value: FavoriteNumber(13)
) {
    UIApplication.shared.activateSceneSession(for: requestWithData)
}
```

当您的 `rootScene` 属性中声明的 SwiftUI 场景被激活时，您的符合类的实例将被 SwiftUI 创建并接收窗口场景生命周期回调。

您的`UIHostingSceneDelegate`类可与应用程序委托的`UISceneConfiguration`方法中的`application(_:configurationForConnecting:options:)`一起使用，以激活 SwiftUI 场景来响应外部事件：

```swift
class AppDelegate: UIApplicationDelegate {

    func application(
        _ app: UIApplication,
        configurationForConnecting sceneSession: UISceneSession,
        options: UIScene.ConnectionOptions
    ) -> UISceneConfiguration {
        let config = UISceneConfiguration(
            name: nil, sessionRole: sceneSession.role)
        config.delegateClass = HostingSceneDelegate.self
        return config
    }

}
```

## 关联类型

- **RootScene**

## 类型属性

- **rootScene**

## 在 UIKit 中显示 SwiftUI 视图

- 在 UIKit 中使用 SwiftUI**：了解如何将 SwiftUI 视图纳入 UIKit 应用程序。
- 统一应用程序的动画**：在 SwiftUI、UIKit 和 AppKit 中创建一致的 UI 动画体验。
- **UIHostingController**：管理 SwiftUI 视图层次结构的 UIKit 视图控制器。
- **UIHostingControllerSizingOptions**：托管控制器如何跟踪其内容大小的选项。
- **UIHostingConfiguration**：适合托管 SwiftUI 视图层次结构的内容配置。

## 继承自

- NSObjectProtocol
- UISceneDelegate


---
source: https://developer.apple.com/documentation/swiftui/uihostingscenedelegate
crawled: 2025-12-04T13:47:22Z
---

# UIHostingSceneDelegate

**Protocol**

Extends `UIKit/UISceneDelegate` to bridge SwiftUI scenes.

## Declaration

```swift
protocol UIHostingSceneDelegate : UISceneDelegate
```

## Overview

Declare any SwiftUI scenes you wish to activate from UIKit in the static `rootScene` property of your conforming class:

```swift
class HostingSceneDelegate: UIHostingSceneDelegate {
    static var rootScene: some Scene {
        WindowGroup(id: "swiftui-window") {
            ContentView()
        }
    }

    // Add UISceneDelegate lifecycle callbacks here
}
```

Use a class conforming to [UIHostingSceneDelegate](UIHostingSceneDelegate.zh-Hans.md) to  activate a scene by its ID or presented value with `UISceneSessionActivationRequest`:

```swift
if let requestWithID = UISceneSessionActivationRequest(
    hostingDelegateClass: HostingSceneDelegate.self,
    id: "swiftui-window"
) {
    UIApplication.shared.activateSceneSession(for: requestWithID)
}

if let requestWithData = UISceneSessionActivationRequest(
    hostingDelegateClass: HostingSceneDelegate.self,
    value: FavoriteNumber(13)
) {
    UIApplication.shared.activateSceneSession(for: requestWithData)
}
```

When a SwiftUI scene declared in your `rootScene` property is activated, an instance of your conforming class will be created by SwiftUI and receive window scene lifecycle callbacks.

Your `UIHostingSceneDelegate` class can be used with a `UISceneConfiguration` in your app delegate’s `application(_:configurationForConnecting:options:)`method to activate a SwiftUI scene in response to an external event:

```swift
class AppDelegate: UIApplicationDelegate {

    func application(
        _ app: UIApplication,
        configurationForConnecting sceneSession: UISceneSession,
        options: UIScene.ConnectionOptions
    ) -> UISceneConfiguration {
        let config = UISceneConfiguration(
            name: nil, sessionRole: sceneSession.role)
        config.delegateClass = HostingSceneDelegate.self
        return config
    }

}
```

## Associated Types

- **RootScene**

## Type Properties

- **rootScene**

## Displaying SwiftUI views in UIKit

- **Using SwiftUI with UIKit**: Learn how to incorporate SwiftUI views into a UIKit app.
- **Unifying your app’s animations**: Create a consistent UI animation experience across SwiftUI, UIKit, and AppKit.
- **UIHostingController**: A UIKit view controller that manages a SwiftUI view hierarchy.
- **UIHostingControllerSizingOptions**: Options for how a hosting controller tracks its content’s size.
- **UIHostingConfiguration**: A content configuration suitable for hosting a hierarchy of SwiftUI views.

## Inherits From

- NSObjectProtocol
- UISceneDelegate

