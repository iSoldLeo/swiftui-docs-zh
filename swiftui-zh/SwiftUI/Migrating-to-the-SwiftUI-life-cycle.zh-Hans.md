---
来源： https://developer.apple.com/documentation/SwiftUI/Migrating-to-the-SwiftUI-life-cycle
抓取时间： 2025-12-02T16:15:46Z
---

# 迁移到 SwiftUI 生命周期

**Article**

在 SwiftUI 中使用基于场景的生命周期，同时保留现有代码库。

## 概览

将您的应用程序移至 SwiftUI 生命周期，从而利用 SwiftUI 中的声明式语法及其与空间框架的兼容性。

迁移到 SwiftUI 生命周期需要几个步骤，包括更改应用程序的入口点、配置应用程序的启动以及使用 SwiftUI 提供的方法监控生命周期的变化。

#### 更改应用程序的入口点

[doc://com.apple.documentation/documentation/UIKit]框架通过注解`@main`将`AppDelegate`文件定义为应用程序的入口点。有关 `@main` 的更多信息，请参阅《Swift 编程语言》中的 [https://docs.swift.org/swift-book/documentation/the-swift-programming-language/attributes/#main] 部分。要表示 SwiftUI 应用程序的入口，您需要创建一个新文件来定义应用程序的结构。

1.在 Xcode 中打开您的项目。
2.选择文件 > 新建 > 文件 > Swift 文件。
3.将文件命名为 `<YourAppName>App.swift`。
4.在文件顶部添加 `import SwiftUI`。
5.5. 用 `@main` 属性注释应用程序结构，以指示 SwiftUI 应用程序的入口点，如下面的代码片段所示。



使用以下代码创建 SwiftUI 应用程序结构。要了解有关此结构的更多信息，请参阅 [https://developer.apple.com/tutorials/swiftui-concepts/exploring-the-structure-of-a-swiftui-app] 中的教程。

```swift
import SwiftUI

@main
struct MyExampleApp: App {
    var body: some Scene {
        WindowGroup {
            ContentView()
        }
    }
}
```

### 支持应用程序委托方法

要继续在应用程序委托中使用方法，请使用 [UIApplicationDelegateAdaptor](UIApplicationDelegateAdaptor.zh-Hans.md) 属性包装器。要告诉 SwiftUI 有关符合[doc://com.apple.documentation/documentation/UIKit/UIApplicationDelegate] 协议的委托的信息，请将此属性包装器置于您的[App](App.zh-Hans.md) 声明中：

```swift
@main
struct MyExampleApp: App {
    @UIApplicationDelegateAdaptor private var appDelegate: MyAppDelegate
    var body: some Scene { ... }
}
```

此示例将名为 `MyAppDelegate` 的自定义应用程序委托标记为委托适配器。请务必在该类型中实现任何必要的委托方法。



### 配置应用程序的启动

如果要将包含故事板的应用程序迁移到 SwiftUI，请确保在不再需要时将其删除。

1.在 Xcode 中打开项目。
2.从项目导航器中移除 `Main.storyboard`。
3.3. 选择应用程序的目标。
4.打开 `Info.plist` 文件。
5.删除[doc://com.apple.documentation/documentation/BundleResources/Information-Property-List/UIMainStoryboardFile]键。
6.删除 [doc://com.apple.documentation/documentation/BundleResources/Information-Property-List/UIApplicationSceneManifest] > [doc://com.apple.documentation/documentation/BundleResources/Information-Property-List/UIApplicationSceneManifest/UISceneConfigurations] > [doc://com.apple.documentation/documentation/BundleResources/Information-Property-List/UIApplicationSceneManifest/UISceneConfigurations/UIWindowSceneSessionRoleApplication] > `Item 0 (Default Configuration)` 字典中的[doc://com.apple.documentation/documentation/BundleResources/Information-Property-List/UIApplicationSceneManifest/UISceneConfigurations/UIWindowSceneSessionRoleApplication/UISceneStoryboardFile]键。

该图显示了删除这些键之前`Info.plist` 文件的结构。



从`Info.plist`文件中移除键值后，场景委托将继续被调用，因此您仍可在此文件中处理其他基于场景的生命周期更改。如果之前是在场景委托中启动应用程序，请从场景委托中移除 [doc://com.apple.documentation/documentation/UIKit/UISceneDelegate/scene(_:willConnectTo:options:)] 方法。

如果您以前在应用程序中不支持场景，而是依靠应用程序委托来响应应用程序的启动，请确保不再在 [doc://com.apple.documentation/documentation/UIKit/UIApplicationDelegate/application(_:didFinishLaunchingWithOptions:)] 中设置根视图控制器。相反，请返回 `true`。

### 监控生命周期变化

由于 SwiftUI 基于场景的特性（参见 [Scene](Scene.zh-Hans.md)），您将无法在应用程序委托中监控生命周期的变化。您最好在 [ScenePhase](ScenePhase.zh-Hans.md)（SwiftUI 提供的用于监控场景阶段的生命周期枚举）中处理这些变化。观察[Environment](Environment.zh-Hans.md) 值，以便在阶段发生变化时启动操作。

```swift
@Environment(\.scenePhase) private var scenePhase
```

根据读取位置的不同，对该值的解释也不同。如果从[View](View.zh-Hans.md) 实例内部读取相位，该值反映的是包含视图的场景的相位。如果从`App` 实例中读取相位，该值反映的是应用程序中所有场景的相位的集合。

要使用场景委托处理基于场景的事件，请在应用程序委托中为 SwiftUI 应用程序提供场景委托。有关详细信息，请参阅[UIApplicationDelegateAdaptor](UIApplicationDelegateAdaptor.zh-Hans.md)中的 "场景委托 "部分。

有关处理基于场景的生命周期事件的详细信息，请参见 [doc://com.apple.documentation/documentation/UIKit/managing-your-app-s-life-cycle]。

## 创建应用程序

- **目的地视频**：利用 SwiftUI 在多平台应用程序中构建身临其境的媒体体验。
- 你好，世界**：利用窗口、体积和沉浸式空间向人们介绍地球。
- 后院小鸟使用 SwiftData 和 widgets 构建应用程序**：使用持久数据、交互式小工具和全新的应用内购买体验创建一款应用。
- ** Food Truck：构建 SwiftUI 多平台应用程序**：为 Mac、iPad 和 iPhone 创建单一代码库和应用程序目标。
- **Fruta：使用 SwiftUI 构建功能丰富的应用程序**：创建共享代码库，以构建一个提供小工具和应用剪辑的多平台应用。
- **App**：表示应用程序结构和行为的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/Migrating-to-the-SwiftUI-life-cycle
crawled: 2025-12-02T16:15:46Z
---

# Migrating to the SwiftUI life cycle

**Article**

Use a scene-based life cycle in SwiftUI while keeping your existing codebase.

## Overview

Take advantage of the declarative syntax in SwiftUI and its compatibility with spatial frameworks by moving your app to the SwiftUI life cycle.

Moving to the SwiftUI life cycle requires several steps, including changing your app’s entry point, configuring the launch of your app, and monitoring life-cycle changes with the methods that SwiftUI provides.

### Change your app’s entry point

The [doc://com.apple.documentation/documentation/UIKit] framework defines the `AppDelegate` file as the entry point of your app with the annotation `@main`. For more information on `@main`, see the [https://docs.swift.org/swift-book/documentation/the-swift-programming-language/attributes/#main] section in The Swift Programming Language. To indicate the entry of a SwiftUI app, you’ll need to create a new file that defines your app’s structure.

1. Open your project in Xcode.
2. Choose File > New > File > Swift file.
3. Name the file `<YourAppName>App.swift`.
4. Add `import SwiftUI` at the top of the file.
5. Annotate the app structure with the `@main` attribute to indicate the entry point of the SwiftUI app, as shown in the code snippet below.



Use following code to create the SwiftUI app structure. To learn more about this structure, follow the tutorial in [https://developer.apple.com/tutorials/swiftui-concepts/exploring-the-structure-of-a-swiftui-app].

```swift
import SwiftUI

@main
struct MyExampleApp: App {
    var body: some Scene {
        WindowGroup {
            ContentView()
        }
    }
}
```

### Support app delegate methods

To continue using methods in your app delegate, use the [UIApplicationDelegateAdaptor](UIApplicationDelegateAdaptor.zh-Hans.md) property wrapper. To tell SwiftUI about a delegate that conforms to the [doc://com.apple.documentation/documentation/UIKit/UIApplicationDelegate] protocol, place this property wrapper inside your [App](App.zh-Hans.md) declaration:

```swift
@main
struct MyExampleApp: App {
    @UIApplicationDelegateAdaptor private var appDelegate: MyAppDelegate
    var body: some Scene { ... }
}
```

This example marks a custom app delegate named `MyAppDelegate` as the delegate adaptor. Be sure to implement any necessary delegate methods in that type.



### Configure the launch of your app

If you’re migrating an app that contains storyboards to SwiftUI, make sure to remove them when they’re no longer needed.

1. Open your project in Xcode.
2. Remove `Main.storyboard` from the project navigator.
3. Choose your app’s target.
4. Open the `Info.plist` file.
5. Remove the [doc://com.apple.documentation/documentation/BundleResources/Information-Property-List/UIMainStoryboardFile] key.
6. Remove the [doc://com.apple.documentation/documentation/BundleResources/Information-Property-List/UIApplicationSceneManifest/UISceneConfigurations/UIWindowSceneSessionRoleApplication/UISceneStoryboardFile] key in the [doc://com.apple.documentation/documentation/BundleResources/Information-Property-List/UIApplicationSceneManifest] > [doc://com.apple.documentation/documentation/BundleResources/Information-Property-List/UIApplicationSceneManifest/UISceneConfigurations] > [doc://com.apple.documentation/documentation/BundleResources/Information-Property-List/UIApplicationSceneManifest/UISceneConfigurations/UIWindowSceneSessionRoleApplication] > `Item 0 (Default Configuration)` dictionary.

This figure shows the structure of the `Info.plist` file before removing these keys.



The scene delegate continues to be called after removing the keys from the `Info.plist` file, so you can still handle other scene-based life cycle changes in this file. If you were previously launching your app in your scene delegate, remove the [doc://com.apple.documentation/documentation/UIKit/UISceneDelegate/scene(_:willConnectTo:options:)] method from your scene delegate.

If you didn’t previously support scenes in your app and rely on your app delegate to respond to the launch of your app, ensure you’re no longer setting a root view controller in [doc://com.apple.documentation/documentation/UIKit/UIApplicationDelegate/application(_:didFinishLaunchingWithOptions:)]. Instead, return `true`.

### Monitor life cycle changes

You will no longer be able to monitor life-cycle changes in your app delegate due to the scene-based nature of SwiftUI (see [Scene](Scene.zh-Hans.md)). Prefer to handle these changes in [ScenePhase](ScenePhase.zh-Hans.md), the life cycle enumeration that SwiftUI provides to monitor the phases of a scene. Observe the [Environment](Environment.zh-Hans.md) value to initiate actions when the phase changes.

```swift
@Environment(\.scenePhase) private var scenePhase
```

Interpret the value differently based on where you read it from. If you read the phase from inside a [View](View.zh-Hans.md) instance, the value reflects the phase of the scene that contains the view. If you read the phase from within an `App` instance, the value reflects an aggregation of the phases of all of the scenes in your app.

To handle scene-based events with a scene delegate, provide your scene delegate to your SwiftUI app inside your app delegate. For more information, see the “Scene delegates” section of [UIApplicationDelegateAdaptor](UIApplicationDelegateAdaptor.zh-Hans.md).

For more information on handling scene-based life cycle events, see [doc://com.apple.documentation/documentation/UIKit/managing-your-app-s-life-cycle].

## Creating an app

- **Destination Video**: Leverage SwiftUI to build an immersive media experience in a multiplatform app.
- **Hello World**: Use windows, volumes, and immersive spaces to teach people about the Earth.
- **Backyard Birds: Building an app with SwiftData and widgets**: Create an app with persistent data, interactive widgets, and an all new in-app purchase experience.
- **Food Truck: Building a SwiftUI multiplatform app**: Create a single codebase and app target for Mac, iPad, and iPhone.
- **Fruta: Building a feature-rich app with SwiftUI**: Create a shared codebase to build a multiplatform app that offers widgets and an App Clip.
- **App**: A type that represents the structure and behavior of an app.

