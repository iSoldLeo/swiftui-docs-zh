---
来源： https://developer.apple.com/documentation/SwiftUI/CircularProgressViewStyle
抓取时间： 2025-12-03T06:10:20Z
---

# CircularProgressViewStyle

**Structure**

进度视图使用圆形仪表来显示活动的部分完成情况。

## 声明

```swift
struct CircularProgressViewStyle
```

## 概览

在 watchOS 以及 widget 和复杂功能中，圆形进度视图会显示为[accessoryCircularCapacity](GaugeStyle/accessoryCircularCapacity.zh-Hans.md)样式的仪表盘。如果进度视图不确定，则仪表盘为空。

如果没有确定的圆形进度视图样式，则圆形进度视图使用不确定样式。

使用 [circular](ProgressViewStyle/circular.zh-Hans.md) 构建循环进度视图样式。

## 创建进度视图样式

- **init()**：创建圆形进度视图样式。

## 过时的初始化程序

- **init(tint:)**：创建带有颜色的圆形进度视图样式。

## 支持类型

- **DefaultProgressViewStyle**：当前样式化视图上下文中的默认进度视图样式。
- **LinearProgressViewStyle**：使用水平条直观显示进度的进度视图。

## 符合

- ProgressViewStyle


---
source: https://developer.apple.com/documentation/SwiftUI/CircularProgressViewStyle
crawled: 2025-12-03T06:10:20Z
---

# CircularProgressViewStyle

**Structure**

A progress view that uses a circular gauge to indicate the partial completion of an activity.

## Declaration

```swift
struct CircularProgressViewStyle
```

## Overview

On watchOS, and in widgets and complications, a circular progress view appears as a gauge with the [accessoryCircularCapacity](GaugeStyle/accessoryCircularCapacity.zh-Hans.md) style. If the progress view is indeterminate, the gauge is empty.

In cases where no determinate circular progress view style is available, circular progress views use an indeterminate style.

Use [circular](ProgressViewStyle/circular.zh-Hans.md) to construct the circular progress view style.

## Creating the progress view style

- **init()**: Creates a circular progress view style.

## Deprecated initializers

- **init(tint:)**: Creates a circular progress view style with a tint color.

## Supporting types

- **DefaultProgressViewStyle**: The default progress view style in the current context of the view being styled.
- **LinearProgressViewStyle**: A progress view that visually indicates its progress using a horizontal bar.

## Conforms To

- ProgressViewStyle

