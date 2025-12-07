---
来源： https://developer.apple.com/documentation/SwiftUI/ScrollGeometry
抓取时间： 2025-12-02T17:40:33Z
---

# 滚动几何

**Structure**

定义滚动视图几何图形的类型。

### 声明

```swift
struct ScrollGeometry
```

## 概览

在使用`View/onScrollGeometryChange(_:action:)` 或 [onScrollPhaseChange(_:)](View/onScrollPhaseChange.zh-Hans.md)等修饰符时，SwiftUI 会为您提供这种类型的值。

## 初始化器

- **init(contentOffset:contentSize:contentInsets:containerSize:)**：创建一个滚动几何体。

### 实例属性

- **bounds**：滚动视图的边界矩形。
- **containerSize**：滚动视图容器的大小。
- **contentInsets**：滚动视图的内容嵌入。
- **contentOffset**：滚动视图的内容偏移量：滚动视图的内容偏移量。
- **contentSize**：滚动视图的内容偏移量：滚动视图内容的大小。
- **visibleRect**：滚动视图内容的大小：滚动视图的可见矩形。

## 响应滚动视图的变化

- **onScrollGeometryChange(for:of:action:)**：添加当滚动几何体创建的值发生变化时要执行的操作。
- **onScrollTargetVisibilityChange(idType:threshold:_:)**：添加一个可调用的操作，其中包含有关哪些视图被视为可见的信息。
- **onScrollVisibilityChange(threshold:_:)**：添加当视图越过阈值被视为开屏/关屏时调用的操作。
- **onScrollPhaseChange(_:)**：添加当层次结构中第一个滚动视图的滚动阶段发生变化时要执行的操作。
- **ScrollPhase**：描述可滚动视图（如滚动视图）的滚动手势状态的类型。
- **ScrollPhaseChangeContext**：当滚动视图的阶段发生变化时，为您提供更多内容的类型。

## 符合

- 可复制
- 自定义调试字符串可转换
- 可等价
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollGeometry
crawled: 2025-12-02T17:40:33Z
---

# ScrollGeometry

**Structure**

A type that defines the geometry of a scroll view.

## Declaration

```swift
struct ScrollGeometry
```

## Overview

SwiftUI provides you values of this type when using modifiers like `View/onScrollGeometryChange(_:action:)` or [onScrollPhaseChange(_:)](View/onScrollPhaseChange.zh-Hans.md).

## Initializers

- **init(contentOffset:contentSize:contentInsets:containerSize:)**: Creates a scroll geometry.

## Instance Properties

- **bounds**: The bounds rect of the scroll view.
- **containerSize**: The size of the container of the scroll view.
- **contentInsets**: The content insets of the scroll view.
- **contentOffset**: The content offset of the scroll view.
- **contentSize**: The size of the content of the scroll view.
- **visibleRect**: The visible rect of the scroll view.

## Responding to scroll view changes

- **onScrollGeometryChange(for:of:action:)**: Adds an action to be performed when a value, created from a scroll geometry, changes.
- **onScrollTargetVisibilityChange(idType:threshold:_:)**: Adds an action to be called with information about what views would be considered visible.
- **onScrollVisibilityChange(threshold:_:)**: Adds an action to be called when the view crosses the threshold to be considered on/off screen.
- **onScrollPhaseChange(_:)**: Adds an action to perform when the scroll phase of the first scroll view in the hierarchy changes.
- **ScrollPhase**: A type that describes the state of a scroll gesture of a scrollable view like a scroll view.
- **ScrollPhaseChangeContext**: A type that provides you with more content when the phase of a scroll view changes.

## Conforms To

- Copyable
- CustomDebugStringConvertible
- Equatable
- Sendable
- SendableMetatype

