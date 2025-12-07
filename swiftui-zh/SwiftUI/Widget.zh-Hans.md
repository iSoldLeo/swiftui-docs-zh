---
来源： https://developer.apple.com/documentation/SwiftUI/Widget
抓取时间： 2025-12-02T17:31:57Z
---

# 小工具

**Protocol**

在主屏幕或通知中心显示的 widget 的配置和内容。

## 声明

```swift
@MainActor @preconcurrency protocol Widget
```

## 概览

小工具可在 iOS 的主屏幕或 macOS 的通知中心显示应用程序的相关内容，一目了然。用户可以添加、配置和排列 Widget，以满足个人需求。你可以提供多种类型的 widget，每种类型都能呈现特定的信息。当用户需要更多信息时，比如阅读标题的完整文章或查看包裹投递的详细信息，widget 可以让他们快速获取应用中的信息。

小工具有三个关键组成部分：

- 配置，用于确定 widget 是否可配置、标识 widget 以及定义显示 widget 内容的 SwiftUI 视图。
- 时间线提供程序，用于驱动随时间更新 widget 视图的过程。
- WidgetKit 用于显示 widget 的 SwiftUI 视图。

有关在应用程序中添加 widget 扩展和更新 widget 的信息，请分别参见 [doc://com.apple.documentation/documentation/WidgetKit/Creating-a-Widget-Extension] 和 [doc://com.apple.documentation/documentation/WidgetKit/Keeping-a-Widget-Up-To-Date] 。

通过添加自定义 SiriKit 意图定义，你可以让用户自定义他们的 widget，以显示与他们最相关的信息。如果你已经添加了对 Siri 或快捷方式的支持，那么你就可以很好地支持自定义 widget 了。有关更多信息，请参阅[doc://com.apple.documentation/documentation/WidgetKit/Making-a-Configurable-Widget]。

如果符合该协议的类型的基本声明中包含了该协议，则该类型将继承`@preconcurrency @MainActor` 隔离协议：

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

## 实现一个小部件

- **body**：widget 的内容和行为。
- **Body**：代表 widget 内容的配置类型。

## 运行部件

- **init()**：创建一个以 `body` 为内容的 widget。
- **main()**：初始化并运行 widget。

## 创建部件

- 使用 WidgetKit 和 SwiftUI 创建小工具**：创建小工具，在主屏幕上显示应用程序的内容，并为用户自定义设置提供自定义意图。
- 创建 widget 扩展**：在各种设备上以方便、信息丰富的 widget 显示应用程序的内容。
- 保持小工具更新**：规划 widget 的时间轴，使用动态视图及时显示相关信息，并在情况发生变化时更新时间轴。
- 制作可配置的小工具**：通过在项目中添加自定义应用程序意图，让人们可以选择定制自己的小工具。
- **WidgetBundle**：用于从单个 widget 扩展中公开多个 widget 的容器。
- **LimitedAvailabilityConfiguration**：类型已消除的 widget 配置。
- **WidgetConfiguration**：描述 widget 内容的类型。
- **EmptyWidgetConfiguration**：一个空的 widget 配置。


---
source: https://developer.apple.com/documentation/SwiftUI/Widget
crawled: 2025-12-02T17:31:57Z
---

# Widget

**Protocol**

The configuration and content of a widget to display on the Home screen or in Notification Center.

## Declaration

```swift
@MainActor @preconcurrency protocol Widget
```

## Overview

Widgets show glanceable and relevant content from your app right on the iOS Home screen or in Notification Center on macOS. Users can add, configure, and arrange widgets to suit their individual needs. You can provide multiple types of widgets, each presenting a specific kind of information. When users want more information, like to read the full article for a headline or to see the details of a package delivery, the widget lets them get to the information in your app quickly.

There are three key components to a widget:

- A configuration that determines whether the widget is configurable, identifies the widget, and defines the SwiftUI views that show the widget’s content.
- A timeline provider that drives the process of updating the widget’s view over time.
- SwiftUI views used by WidgetKit to display the widget.

For information about adding a widget extension to your app, and keeping your widget up to date, see [doc://com.apple.documentation/documentation/WidgetKit/Creating-a-Widget-Extension] and [doc://com.apple.documentation/documentation/WidgetKit/Keeping-a-Widget-Up-To-Date], respectively.

By adding a custom SiriKit intent definition, you can let users customize their widgets to show the information that’s most relevant to them. If you’ve already added support for Siri or Shortcuts, you’re well on your way to supporting customizable widgets. For more information, see [doc://com.apple.documentation/documentation/WidgetKit/Making-a-Configurable-Widget].

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

## Implementing a widget

- **body**: The content and behavior of the widget.
- **Body**: The type of configuration representing the content of the widget.

## Running a widget

- **init()**: Creates a widget using `body` as its content.
- **main()**: Initializes and runs the widget.

## Creating widgets

- **Building Widgets Using WidgetKit and SwiftUI**: Create widgets to show your app’s content on the Home screen, with custom intents for user-customizable settings.
- **Creating a widget extension**: Display your app’s content in a convenient, informative widget on various devices.
- **Keeping a widget up to date**: Plan your widget’s timeline to show timely, relevant information using dynamic views, and update the timeline when things change.
- **Making a configurable widget**: Give people the option to customize their widgets by adding a custom app intent to your project.
- **WidgetBundle**: A container used to expose multiple widgets from a single widget extension.
- **LimitedAvailabilityConfiguration**: A type-erased widget configuration.
- **WidgetConfiguration**: A type that describes a widget’s content.
- **EmptyWidgetConfiguration**: An empty widget configuration.

