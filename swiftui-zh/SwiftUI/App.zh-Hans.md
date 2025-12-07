---
来源： https://developer.apple.com/documentation/SwiftUI/App
抓取时间： 2025-12-02T16:15:46Z
---

# 应用程序

**Protocol**

表示应用程序结构和行为的类型。

## 声明

```swift
@MainActor @preconcurrency protocol App
```

## 概览

通过声明符合`App` 协议的结构来创建应用程序。实现所需的[body-swift.property](App/body-swift_property.zh-Hans.md)计算属性，以定义应用程序的内容：

```swift
@main
struct MyApp: App {
    var body: some Scene {
        WindowGroup {
            Text("Hello, world!")
        }
    }
}
```

在结构体声明之前加上 [https://docs.swift.org/swift-book/ReferenceManual/Attributes.html#ID626] 属性，以表明您自定义的`App` 协议符合者为您的应用程序提供了入口点。该协议提供了[main()](App/main.zh-Hans.md) 方法的默认实现，系统调用该方法来启动您的应用程序。您可以在应用程序的所有文件中使用一个入口点。

由符合[Scene](Scene.zh-Hans.md) 协议的实例组成应用程序的主体。每个场景都包含视图层次结构的根视图，并有一个由系统管理的生命周期。SwiftUI 提供了一些具体的场景类型来处理常见场景，如显示文档或设置。您还可以创建自定义场景。

```swift
@main
struct Mail: App {
    var body: some Scene {
        WindowGroup {
            MailViewer()
        }
        Settings {
            SettingsView()
        }
    }
}
```

您可以在应用程序中声明状态，以便在所有场景中共享。例如，您可以使用[StateObject](StateObject.zh-Hans.md) 属性初始化数据模型，然后在视图输入中将该模型作为[ObservedObject](ObservedObject.zh-Hans.md) 或通过环境作为[EnvironmentObject](EnvironmentObject.zh-Hans.md) 提供给应用程序中的场景：

```swift
@main
struct Mail: App {
    @StateObject private var model = MailModel()

    var body: some Scene {
        WindowGroup {
            MailViewer()
                .environmentObject(model) // Passed through the environment.
        }
        Settings {
            SettingsView(model: model) // Passed as an observed object.
        }
    }
}
```

如果符合该协议的类型的基本声明中包含该符合性，则该符合该协议的类型将继承`@preconcurrency @MainActor` 隔离性：

```swift
struct MyCustomType: Transition {
    // `@preconcurrency @MainActor` isolation by default
}
```

默认情况下与主要角色隔离，但这不是必须的。在扩展声明中声明一致性，就可以不使用主要角色隔离：

```swift
extension MyCustomType: Transition {
    // `nonisolated` by default
}
```

## 实现应用程序

- **body**：应用程序的内容和行为。
- **Body**：代表应用程序内容的场景类型。

## 运行应用程序

- **init()**：使用您为其内容定义的主体创建应用程序实例。
- **main()**：初始化并运行应用程序。

## 创建应用程序

- **目的地视频**：利用 SwiftUI 在多平台应用程序中构建身临其境的媒体体验。
- 你好，世界**：利用窗口、体积和沉浸式空间向人们介绍地球。
- 后院小鸟使用 SwiftData 和 widgets 构建应用程序**：使用持久数据、交互式小工具和全新的应用内购买体验创建一款应用。
- ** Food Truck：构建 SwiftUI 多平台应用程序**：为 Mac、iPad 和 iPhone 创建单一代码库和应用程序目标。
- **Fruta：使用 SwiftUI 构建功能丰富的应用程序**：创建共享代码库，以构建一个提供小工具和应用剪辑的多平台应用。
- 迁移到 SwiftUI 生命周期**：在 SwiftUI 中使用基于场景的生命周期，同时保留现有代码库。


---
source: https://developer.apple.com/documentation/SwiftUI/App
crawled: 2025-12-02T16:15:46Z
---

# App

**Protocol**

A type that represents the structure and behavior of an app.

## Declaration

```swift
@MainActor @preconcurrency protocol App
```

## Overview

Create an app by declaring a structure that conforms to the `App` protocol. Implement the required [body-swift.property](App/body-swift_property.zh-Hans.md) computed property to define the app’s content:

```swift
@main
struct MyApp: App {
    var body: some Scene {
        WindowGroup {
            Text("Hello, world!")
        }
    }
}
```

Precede the structure’s declaration with the [https://docs.swift.org/swift-book/ReferenceManual/Attributes.html#ID626] attribute to indicate that your custom `App` protocol conformer provides the entry point into your app. The protocol provides a default implementation of the [main()](App/main.zh-Hans.md) method that the system calls to launch your app. You can have exactly one entry point among all of your app’s files.

Compose the app’s body from instances that conform to the [Scene](Scene.zh-Hans.md) protocol. Each scene contains the root view of a view hierarchy and has a life cycle managed by the system. SwiftUI provides some concrete scene types to handle common scenarios, like for displaying documents or settings. You can also create custom scenes.

```swift
@main
struct Mail: App {
    var body: some Scene {
        WindowGroup {
            MailViewer()
        }
        Settings {
            SettingsView()
        }
    }
}
```

You can declare state in your app to share across all of its scenes. For example, you can use the [StateObject](StateObject.zh-Hans.md) attribute to initialize a data model, and then provide that model on a view input as an [ObservedObject](ObservedObject.zh-Hans.md) or through the environment as an [EnvironmentObject](EnvironmentObject.zh-Hans.md) to scenes in the app:

```swift
@main
struct Mail: App {
    @StateObject private var model = MailModel()

    var body: some Scene {
        WindowGroup {
            MailViewer()
                .environmentObject(model) // Passed through the environment.
        }
        Settings {
            SettingsView(model: model) // Passed as an observed object.
        }
    }
}
```

A type conforming to this protocol inherits `@preconcurrency @MainActor` isolation from the protocol if the conformance is included in the type’s base declaration:

```swift
struct MyCustomType: Transition {
    // `@preconcurrency @MainActor` isolation by default
}
```

Isolation to the main actor is the default, but it’s not required. Declare the conformance in an extension to opt out of main actor isolation:

```swift
extension MyCustomType: Transition {
    // `nonisolated` by default
}
```

## Implementing an app

- **body**: The content and behavior of the app.
- **Body**: The type of scene representing the content of the app.

## Running an app

- **init()**: Creates an instance of the app using the body that you define for its content.
- **main()**: Initializes and runs the app.

## Creating an app

- **Destination Video**: Leverage SwiftUI to build an immersive media experience in a multiplatform app.
- **Hello World**: Use windows, volumes, and immersive spaces to teach people about the Earth.
- **Backyard Birds: Building an app with SwiftData and widgets**: Create an app with persistent data, interactive widgets, and an all new in-app purchase experience.
- **Food Truck: Building a SwiftUI multiplatform app**: Create a single codebase and app target for Mac, iPad, and iPhone.
- **Fruta: Building a feature-rich app with SwiftUI**: Create a shared codebase to build a multiplatform app that offers widgets and an App Clip.
- **Migrating to the SwiftUI life cycle**: Use a scene-based life cycle in SwiftUI while keeping your existing codebase.

