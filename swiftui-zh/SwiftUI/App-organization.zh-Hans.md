---
来源： https://developer.apple.com/documentation/SwiftUI/App-organization
抓取时间： 2025-12-02T17:20:58Z
---

# 应用程序组织

** 应用程序集**

定义应用程序的入口点和顶层结构。

## 概览

声明式地描述应用程序的结构，就像声明视图的外观一样。创建一个符合[App](App.zh-Hans.md)协议的类型，并用它来枚举代表应用程序用户界面各个方面的[Scenes](Scenes.zh-Hans.md)。



通过 SwiftUI，您编写的代码可以在苹果的所有平台上运行。不过，它也能让您根据每个平台的特定功能定制应用程序。例如，如果您需要响应系统传统上对 UIKit、AppKit 或 WatchKit 应用程序的委托进行的回调，请定义一个委托对象，并使用适当的委托适配器属性包装器（如 [UIApplicationDelegateAdaptor](UIApplicationDelegateAdaptor.zh-Hans.md)）在您的应用程序结构中将其实例化。

有关特定平台的设计指导，请参阅《人机界面指南》中的 [doc://com.apple.documentation/design/Human-Interface-Guidelines/getting-started]。

## 创建应用程序

- **目的地视频**：利用 SwiftUI 在多平台应用程序中构建身临其境的媒体体验。
- 你好，世界**：利用窗口、体积和沉浸式空间向人们介绍地球。
- 后院小鸟使用 SwiftData 和 widgets 构建应用程序**：使用持久数据、交互式小工具和全新的应用内购买体验创建一款应用。
- ** Food Truck：构建 SwiftUI 多平台应用程序**：为 Mac、iPad 和 iPhone 创建单一代码库和应用程序目标。
- **Fruta：使用 SwiftUI 构建功能丰富的应用程序**：创建共享代码库，以构建一个提供小工具和应用剪辑的多平台应用。
- 迁移到 SwiftUI 生命周期**：在 SwiftUI 中使用基于场景的生命周期，同时保留现有代码库。
- **App**：表示应用程序结构和行为的类型。

## 针对 iOS 和 iPadOS

- **UILaunchScreen**：应用程序启动时显示的用户界面。
- **UILaunchScreens**：根据不同的 URL 方案启动应用程序时要显示的用户界面。
- **UIApplicationDelegateAdaptor**：用于创建 UIKit 应用程序委托的属性封装类型。

## 针对 macOS

- **NSApplicationDelegateAdaptor**：用于创建 AppKit 应用程序委托的属性封装类型。

## targeting watchOS

- **WKApplicationDelegateAdaptor**：在 `App` 中使用的属性包装器，用于提供来自 WatchKit 的委托。
- **WKExtensionDelegateAdaptor**：用于创建 WatchKit 扩展委托的属性包装器类型。

## targeting tvOS

- 在 SwiftUI 中创建 tvOS 媒体目录应用程序**：为你的 tvOS 应用程序构建标准的内容锁和内容搁架行。

## 处理系统重定向事件

- **WorldRecenterPhase**：表示与系统重启事件某一阶段相关信息的类型。此类型的值将传递给 View.onWorldRecenter(action:) 中指定的闭包。

### 应用程序结构

- **Scenes**：声明构成应用程序各部分的用户界面分组。
- **Windows**：在窗口或窗口集合中显示用户界面内容。
- ** 无限空间**：在人的周围显示无限制的内容。
- **Documents**：让人们能够打开和管理文件。
- **Navigation**：使人们能够在场景中的应用程序视图层次结构的不同部分之间移动。
- **模拟演示**：在单独的视图中展示内容，提供集中的交互。
- **Toolbars**：提供对常用命令和控件的即时访问。
- **Search**：使人们能够在您的应用程序中搜索文本或其他内容。
- **应用扩展**：将应用程序的基本功能扩展到系统的其他部分，如添加 Widget。


---
source: https://developer.apple.com/documentation/SwiftUI/App-organization
crawled: 2025-12-02T17:20:58Z
---

# App organization

**API Collection**

Define the entry point and top-level structure of your app.

## Overview

Describe your app’s structure declaratively, much like you declare a view’s appearance. Create a type that conforms to the [App](App.zh-Hans.md) protocol and use it to enumerate the [Scenes](Scenes.zh-Hans.md) that represent aspects of your app’s user interface.



SwiftUI enables you to write code that works across all of Apple’s platforms. However, it also enables you to tailor your app to the specific capabilities of each platform. For example, if you need to respond to the callbacks that the system traditionally makes on a UIKit, AppKit, or WatchKit app’s delegate, define a delegate object and instantiate it in your app structure using an appropriate delegate adaptor property wrapper, like [UIApplicationDelegateAdaptor](UIApplicationDelegateAdaptor.zh-Hans.md).

For platform-specific design guidance, see [doc://com.apple.documentation/design/Human-Interface-Guidelines/getting-started] in the Human Interface Guidelines.

## Creating an app

- **Destination Video**: Leverage SwiftUI to build an immersive media experience in a multiplatform app.
- **Hello World**: Use windows, volumes, and immersive spaces to teach people about the Earth.
- **Backyard Birds: Building an app with SwiftData and widgets**: Create an app with persistent data, interactive widgets, and an all new in-app purchase experience.
- **Food Truck: Building a SwiftUI multiplatform app**: Create a single codebase and app target for Mac, iPad, and iPhone.
- **Fruta: Building a feature-rich app with SwiftUI**: Create a shared codebase to build a multiplatform app that offers widgets and an App Clip.
- **Migrating to the SwiftUI life cycle**: Use a scene-based life cycle in SwiftUI while keeping your existing codebase.
- **App**: A type that represents the structure and behavior of an app.

## Targeting iOS and iPadOS

- **UILaunchScreen**: The user interface to show while an app launches.
- **UILaunchScreens**: The user interfaces to show while an app launches in response to different URL schemes.
- **UIApplicationDelegateAdaptor**: A property wrapper type that you use to create a UIKit app delegate.

## Targeting macOS

- **NSApplicationDelegateAdaptor**: A property wrapper type that you use to create an AppKit app delegate.

## Targeting watchOS

- **WKApplicationDelegateAdaptor**: A property wrapper that is used in `App` to provide a delegate from WatchKit.
- **WKExtensionDelegateAdaptor**: A property wrapper type that you use to create a WatchKit extension delegate.

## Targeting tvOS

- **Creating a tvOS media catalog app in SwiftUI**: Build standard content lockups and rows of content shelves for your tvOS app.

## Handling system recenter events

- **WorldRecenterPhase**: A type that represents information associated with a phase of a system recenter event. Values of this type are passed to the closure specified in View.onWorldRecenter(action:).

## App structure

- **Scenes**: Declare the user interface groupings that make up the parts of your app.
- **Windows**: Display user interface content in a window or a collection of windows.
- **Immersive spaces**: Display unbounded content in a person’s surroundings.
- **Documents**: Enable people to open and manage documents.
- **Navigation**: Enable people to move between different parts of your app’s view hierarchy within a scene.
- **Modal presentations**: Present content in a separate view that offers focused interaction.
- **Toolbars**: Provide immediate access to frequently used commands and controls.
- **Search**: Enable people to search for text or other content within your app.
- **App extensions**: Extend your app’s basic functionality to other parts of the system, like by adding a Widget.

