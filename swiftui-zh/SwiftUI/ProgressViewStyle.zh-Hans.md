---
来源： https://developer.apple.com/documentation/SwiftUI/ProgressViewStyle
抓取时间： 2025-12-02T17:33:14Z
---

# ProgressViewStyle

**Protocol**

对视图层次结构中的所有进度视图应用标准交互行为的类型。

### 声明

```swift
@MainActor @preconcurrency protocol ProgressViewStyle
```

## 概览

要为视图层次结构配置当前进度视图样式，请使用 [progressViewStyle(_:)](View/progressViewStyle.zh-Hans.md) 修改器。

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

## 获取内置的进度视图样式

- **automatic**：当前样式化视图上下文中的默认进度视图样式。
- **circular**：进度视图的样式，该样式使用圆形仪表来指示活动的部分完成情况。
- **linear**：使用水平条直观显示进度的进度视图。

## 创建自定义进度视图样式

- **makeBody(configuration:)**：创建表示进度视图主体的视图。
- **ProgressViewStyle.Configuration**：进度视图实例属性的类型别名。
- **Body**：表示进度视图主体的视图。

## 支持类型

- **DefaultProgressViewStyle**：当前样式化视图上下文中的默认进度视图样式。
- **CircularProgressViewStyle**：进度视图使用圆形仪表来指示活动的部分完成情况。
- **LinearProgressViewStyle**：使用水平条直观显示进度的进度视图。

### 风格指标

- **gaugeStyle(_:)**：设置此视图中仪表的样式。
- **GaugeStyle**：定义视图层次结构中所有仪表实例的实现。
- **GaugeStyleConfiguration**：量规实例的属性。
- **progressViewStyle(_:)**：设置此视图中进度视图的样式。
- **ProgressViewStyleConfiguration**：进度视图实例的属性：进度视图实例的属性。

## 符合类型

- 循环进度视图样式（CircularProgressViewStyle
- 默认进度视图样式
- 线性进度视图样式


---
source: https://developer.apple.com/documentation/SwiftUI/ProgressViewStyle
crawled: 2025-12-02T17:33:14Z
---

# ProgressViewStyle

**Protocol**

A type that applies standard interaction behavior to all progress views within a view hierarchy.

## Declaration

```swift
@MainActor @preconcurrency protocol ProgressViewStyle
```

## Overview

To configure the current progress view style for a view hierarchy, use the [progressViewStyle(_:)](View/progressViewStyle.zh-Hans.md) modifier.

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

## Getting built-in progress view styles

- **automatic**: The default progress view style in the current context of the view being styled.
- **circular**: The style of a progress view that uses a circular gauge to indicate the partial completion of an activity.
- **linear**: A progress view that visually indicates its progress using a horizontal bar.

## Creating custom progress view styles

- **makeBody(configuration:)**: Creates a view representing the body of a progress view.
- **ProgressViewStyle.Configuration**: A type alias for the properties of a progress view instance.
- **Body**: A view representing the body of a progress view.

## Supporting types

- **DefaultProgressViewStyle**: The default progress view style in the current context of the view being styled.
- **CircularProgressViewStyle**: A progress view that uses a circular gauge to indicate the partial completion of an activity.
- **LinearProgressViewStyle**: A progress view that visually indicates its progress using a horizontal bar.

## Styling indicators

- **gaugeStyle(_:)**: Sets the style for gauges within this view.
- **GaugeStyle**: Defines the implementation of all gauge instances within a view hierarchy.
- **GaugeStyleConfiguration**: The properties of a gauge instance.
- **progressViewStyle(_:)**: Sets the style for progress views in this view.
- **ProgressViewStyleConfiguration**: The properties of a progress view instance.

## Conforming Types

- CircularProgressViewStyle
- DefaultProgressViewStyle
- LinearProgressViewStyle

