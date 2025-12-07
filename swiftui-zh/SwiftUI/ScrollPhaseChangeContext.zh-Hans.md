--- 来源：https://developer.apple.com/documentation/SwiftUI/ScrollPhaseChangeContext

抓取时间：2025-12-02T17:40:35Z

---

# ScrollPhaseChangeContext

**Structure**

当滚动视图的阶段发生变化时，此类型会提供更多内容。

## 声明

```swift
struct ScrollPhaseChangeContext
```

## 概述

您无需直接创建此类型。SwiftUI 会在 [onScrollPhaseChange(_:)](View/onScrollPhaseChange.zh-Hans.md) 修饰符中提供此类型的实例。

## 实例属性

- **geometry**：滚动视图在滚动阶段发生变化时的几何形状。

- **velocity**：滚动视图在滚动阶段发生变化时的速度。

## 响应滚动视图的变化

- **onScrollGeometryChange(for:of:action:)**：添加一个操作，当由滚动几何体创建的值发生变化时执行。

- **onScrollTargetVisibilityChange(idType:threshold:_:)**：添加一个操作，用于调用有关哪些视图被视为可见的信息。

- **onScrollVisibilityChange(threshold:_:)**：添加一个操作，当视图跨越阈值以被视为屏幕显示/隐藏时执行。

- **onScrollPhaseChange(_:)**：添加一个操作，当层次结构中第一个滚动视图的滚动阶段发生变化时执行。

- **ScrollGeometry**：定义滚动视图几何体的类型。

- **ScrollPhase**：描述可滚动视图（例如滚动视图）的滚动手势状态的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollPhaseChangeContext
crawled: 2025-12-02T17:40:35Z
---

# ScrollPhaseChangeContext

**Structure**

A type that provides you with more content when the phase of a scroll view changes.

## Declaration

```swift
struct ScrollPhaseChangeContext
```

## Overview

You don’t create this type directly. Instead, SwiftUI provides an instance of this type in the [onScrollPhaseChange(_:)](View/onScrollPhaseChange.zh-Hans.md) modifier.

## Instance Properties

- **geometry**: The geometry of the scroll view at the time of the scroll phase change.
- **velocity**: The velocity of the scroll view at the time of the scroll phase change.

## Responding to scroll view changes

- **onScrollGeometryChange(for:of:action:)**: Adds an action to be performed when a value, created from a scroll geometry, changes.
- **onScrollTargetVisibilityChange(idType:threshold:_:)**: Adds an action to be called with information about what views would be considered visible.
- **onScrollVisibilityChange(threshold:_:)**: Adds an action to be called when the view crosses the threshold to be considered on/off screen.
- **onScrollPhaseChange(_:)**: Adds an action to perform when the scroll phase of the first scroll view in the hierarchy changes.
- **ScrollGeometry**: A type that defines the geometry of a scroll view.
- **ScrollPhase**: A type that describes the state of a scroll gesture of a scrollable view like a scroll view.

