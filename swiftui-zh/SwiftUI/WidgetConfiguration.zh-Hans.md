---
来源： https://developer.apple.com/documentation/SwiftUI/WidgetConfiguration
抓取时间： 2025-12-02T17:31:58Z
---

# WidgetConfiguration

**Protocol**

描述 widget 内容的类型。

### 声明

```swift
@MainActor @preconcurrency protocol WidgetConfiguration
```

## 概览

如果符合本协议的类型的基本声明中包含了本协议，那么该类型就继承了本协议的 `@preconcurrency @MainActor` 隔离性：

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

- **body**：该 widget 的内容和行为。
- **Body**：代表此配置主体的 widget 配置类型。

## 设置名称

- **configurationDisplayName(_:)**：设置用户添加或编辑 widget 时显示的本地化名称。

## 设置描述

- **description(_:)**：设置用户使用文本视图内容添加或编辑 widget 时显示的描述。

## 设置外观

- **supportedFamilies(_:)**：设置 widget 支持的尺寸。
- **contentMarginsDisabled()**：禁用默认内容边距。
- **disfavoredLocations(_:for:)**：为 widget 设置不喜欢的位置。
- **containerBackgroundRemovable(_:)**：将 widget 的背景标记为可移动的修改器。

## 管理后台任务

- **backgroundTask(_:action:)**：当系统提供后台任务时，运行给定的操作。
- **onBackgroundURLSessionEvents(matching:_:)**：当与闭包标识的 URL 会话相关的事件等待处理时，添加要执行的操作。

### 实例方法

- **associatedKind(_:)**：告诉系统基于相关性的 widget 可以取代基于时间线的 widget。
- **promptsForUserConfiguration()**：指定 widget 的配置 UI 应在添加 widget 后自动显示。
- **pushHandler(_:)**：注册一种类型，用于处理部件的推送令牌更改。
- **supplementalActivityFamilies(_:)**：设置实时活动支持的尺寸。
- **supportedMountingStyles(_:)**：指定此 widget 的安装样式。
- **widgetTexture(_:)**：指定此 widget 的纹理。

## 创建 widget

- 使用 WidgetKit 和 SwiftUI 创建 Widget**：创建 Widget，在主屏幕上显示应用程序的内容，并为用户自定义设置提供自定义意图。
- 创建 widget 扩展**：在各种设备上以方便、信息丰富的 widget 显示应用程序的内容。
- 保持小工具更新**：规划 widget 的时间轴，使用动态视图及时显示相关信息，并在情况发生变化时更新时间轴。
- 制作可配置的小工具**：通过在项目中添加自定义应用程序意图，让人们可以选择定制自己的小工具。
- **Widget**：在主屏幕或通知中心显示的 widget 的配置和内容。
- **WidgetBundle**：用于从单个 widget 扩展中公开多个 widget 的容器。
- **LimitedAvailabilityConfiguration**：类型已消除的 widget 配置。
- **EmptyWidgetConfiguration**：一个空的 widget 配置。

## 符合类型

- 空 widgetConfiguration
- 有限可用性配置（LimitedAvailabilityConfiguration


---
source: https://developer.apple.com/documentation/SwiftUI/WidgetConfiguration
crawled: 2025-12-02T17:31:58Z
---

# WidgetConfiguration

**Protocol**

A type that describes a widget’s content.

## Declaration

```swift
@MainActor @preconcurrency protocol WidgetConfiguration
```

## Overview

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

- **body**: The content and behavior of this widget.
- **Body**: The type of widget configuration representing the body of this configuration.

## Setting a name

- **configurationDisplayName(_:)**: Sets the localized name shown for a widget when a user adds or edits the widget.

## Setting a description

- **description(_:)**: Sets the description shown for a widget when a user adds or edits it using the contents of a text view.

## Setting the appearance

- **supportedFamilies(_:)**: Sets the sizes that a widget supports.
- **contentMarginsDisabled()**: Disable default content margins.
- **disfavoredLocations(_:for:)**: Sets the disfavored locations for a widget.
- **containerBackgroundRemovable(_:)**: A modifier that marks the background of a widget as removable.

## Managing background tasks

- **backgroundTask(_:action:)**: Runs the given action when the system provides a background task.
- **onBackgroundURLSessionEvents(matching:_:)**: Adds an action to perform when events related to a URL session identified by a closure are waiting to be processed.

## Instance Methods

- **associatedKind(_:)**: Tells the system that a relevance-based widget can replace a timeline-based widget.
- **promptsForUserConfiguration()**: Specifies that a widget’s configuration UI should be automatically presented after the widget is added.
- **pushHandler(_:)**: Register a type that can handle push tokens changing for widgets.
- **supplementalActivityFamilies(_:)**: Sets the sizes that a Live Activity supports.
- **supportedMountingStyles(_:)**: Specifies the mounting style for this widget.
- **widgetTexture(_:)**: Specifies the widget texture for this widget.

## Creating widgets

- **Building Widgets Using WidgetKit and SwiftUI**: Create widgets to show your app’s content on the Home screen, with custom intents for user-customizable settings.
- **Creating a widget extension**: Display your app’s content in a convenient, informative widget on various devices.
- **Keeping a widget up to date**: Plan your widget’s timeline to show timely, relevant information using dynamic views, and update the timeline when things change.
- **Making a configurable widget**: Give people the option to customize their widgets by adding a custom app intent to your project.
- **Widget**: The configuration and content of a widget to display on the Home screen or in Notification Center.
- **WidgetBundle**: A container used to expose multiple widgets from a single widget extension.
- **LimitedAvailabilityConfiguration**: A type-erased widget configuration.
- **EmptyWidgetConfiguration**: An empty widget configuration.

## Conforming Types

- EmptyWidgetConfiguration
- LimitedAvailabilityConfiguration

