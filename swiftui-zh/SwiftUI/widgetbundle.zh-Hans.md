---
来源： https://developer.apple.com/documentation/swiftui/widgetbundle
抓取时间： 2025-12-04T01:51:14Z
---

# WidgetBundle

**Protocol**

用于从单个 Widget 扩展中公开多个 Widget 的容器。

### 声明

```swift
@MainActor @preconcurrency protocol WidgetBundle
```

## 概览

要支持多种类型的 widget，可在符`@main` 的结构中添加`WidgetBundle` 属性。例如，一个游戏可能会有一个小部件来显示游戏的概要信息，而第二个小部件则用来显示各个角色的详细信息。

```swift
@main
struct GameWidgets: WidgetBundle {
   var body: some Widget {
       GameStatusWidget()
       CharacterDetailWidget()
   }
}
```

## 实现部件捆绑

- **body**：声明应用程序支持的部件组。
- **Body**：表示捆绑内容的 widget 类型。
- **WidgetBundleBuilder**：用于构建 widget bundle 主体的自定义属性。

## 运行部件包

- **init()**：使用 bundle 的正文作为内容创建 widget bundle。
- **main()**：初始化并运行 widget bundle。

## 创建部件

- 使用 WidgetKit 和 SwiftUI 创建小工具**：创建小工具，在主屏幕上显示应用程序的内容，并为用户自定义设置提供自定义意图。
- 创建 widget 扩展**：在各种设备上以方便、信息丰富的 widget 显示应用程序的内容。
- 保持小工具更新**：规划 widget 的时间轴，使用动态视图及时显示相关信息，并在情况发生变化时更新时间轴。
- 制作可配置的小工具**：通过在项目中添加自定义应用程序意图，让人们可以选择定制自己的小工具。
- **Widget**：在主屏幕或通知中心显示的 widget 的配置和内容。
- **LimitedAvailabilityConfiguration**：按类型排列的 widget 配置。
- **WidgetConfiguration**：描述 widget 内容的类型。
- **EmptyWidgetConfiguration**：一个空的 widget 配置。


---
source: https://developer.apple.com/documentation/swiftui/widgetbundle
crawled: 2025-12-04T01:51:14Z
---

# WidgetBundle

**Protocol**

A container used to expose multiple widgets from a single widget extension.

## Declaration

```swift
@MainActor @preconcurrency protocol WidgetBundle
```

## Overview

To support multiple types of widgets, add the `@main` attribute to a structure that conforms to `WidgetBundle`. For example, a game might have one widget to display summary information about the game and a second widget to display detailed information about individual characters.

```swift
@main
struct GameWidgets: WidgetBundle {
   var body: some Widget {
       GameStatusWidget()
       CharacterDetailWidget()
   }
}
```

## Implementing a widget bundle

- **body**: Declares the group of widgets that an app supports.
- **Body**: The type of widget that represents the content of the bundle.
- **WidgetBundleBuilder**: A custom attribute that constructs a widget bundle’s body.

## Running a widget bundle

- **init()**: Creates a widget bundle using the bundle’s body as its content.
- **main()**: Initializes and runs the widget bundle.

## Creating widgets

- **Building Widgets Using WidgetKit and SwiftUI**: Create widgets to show your app’s content on the Home screen, with custom intents for user-customizable settings.
- **Creating a widget extension**: Display your app’s content in a convenient, informative widget on various devices.
- **Keeping a widget up to date**: Plan your widget’s timeline to show timely, relevant information using dynamic views, and update the timeline when things change.
- **Making a configurable widget**: Give people the option to customize their widgets by adding a custom app intent to your project.
- **Widget**: The configuration and content of a widget to display on the Home screen or in Notification Center.
- **LimitedAvailabilityConfiguration**: A type-erased widget configuration.
- **WidgetConfiguration**: A type that describes a widget’s content.
- **EmptyWidgetConfiguration**: An empty widget configuration.

