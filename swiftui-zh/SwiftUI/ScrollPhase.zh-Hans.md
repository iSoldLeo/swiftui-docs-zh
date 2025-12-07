---
来源： https://developer.apple.com/documentation/SwiftUI/ScrollPhase
抓取时间： 2025-12-02T17:40:34Z
---

# 滚动相位

**Enumeration**

描述可滚动视图（如滚动视图）的滚动手势状态的类型。

### 声明

```swift
@frozen enum ScrollPhase
```

## 概览

滚动手势可以处于以下四个阶段之一： - 空闲：无活动滚动。- 平移：由用户驱动的活动滚动正在进行。- 减速：用户已停止驱动滚动，滚动视图正减速至最终目标。- 动画：由于使用[ScrollViewReader](ScrollViewReader.zh-Hans.md) 或[scrollPosition(id:anchor:)](View/scrollPosition_id_anchor.zh-Hans.md) 修饰符编程动画滚动，系统正以动画方式到达最终目标。

在使用[onScrollPhaseChange(_:)](View/onScrollPhaseChange.zh-Hans.md)修饰符时，SwiftUI 会为您提供这种类型的值。

## 获取滚动手势状态

- **ScrollPhase.animating**：滚动视图向最终目标滚动的动画阶段。
- **ScrollPhase.decelerating**：减速阶段：用户停止与滚动视图交互，滚动视图向最终目标减速。
- **ScrollPhase.idle**：空闲阶段，不进行任何滚动操作。
- **ScrollPhase.interacting**：交互阶段，用户正在与滚动视图交互。
- **ScrollPhase.tracking**：跟踪阶段：滚动视图正在跟踪用户的潜在滚动，但用户尚未开始滚动。

## 检查是否正在滚动

- **isScrolling**：滚动视图是否正在滚动。

## 响应滚动视图的变化

- **onScrollGeometryChange(for:of:action:)**：添加当滚动几何体创建的值发生变化时要执行的操作。
- **onScrollTargetVisibilityChange(idType:threshold:_:)**：添加一个可调用的操作，其中包含有关哪些视图被视为可见的信息。
- **onScrollVisibilityChange(threshold:_:)**：添加当视图越过阈值被视为开屏/关屏时调用的操作。
- **onScrollPhaseChange(_:)**：添加当层次结构中第一个滚动视图的滚动阶段发生变化时要执行的操作。
- **ScrollGeometry**：定义滚动视图几何形状的类型。
- **ScrollPhaseChangeContext**：当滚动视图的相位发生变化时，为您提供更多内容的类型。

## 符合

- 比特可复制
- 可复制
- 自定义调试字符串可转换
- 等价
- 可散列
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollPhase
crawled: 2025-12-02T17:40:34Z
---

# ScrollPhase

**Enumeration**

A type that describes the state of a scroll gesture of a scrollable view like a scroll view.

## Declaration

```swift
@frozen enum ScrollPhase
```

## Overview

A scroll gesture can be in one of four phases: - idle: No active scroll is occurring. - panning: An active scroll being driven by the user is occurring. - decelerating: The user has stopped driving a scroll and the scroll view is decelerating to its final target. - animating: The system is animating to a final target as a result of a programmatic animated scroll from using a [ScrollViewReader](ScrollViewReader.zh-Hans.md) or [scrollPosition(id:anchor:)](View/scrollPosition_id_anchor.zh-Hans.md) modifier.

SwiftUI provides you a value of this type when using the [onScrollPhaseChange(_:)](View/onScrollPhaseChange.zh-Hans.md) modifier.

## Getting scroll gesture states

- **ScrollPhase.animating**: The animating phase where the scroll view is animating towards a final target.
- **ScrollPhase.decelerating**: The decelerating phase where the user use has stopped interacting with the scroll view and the scroll view is decelerating towards its final target.
- **ScrollPhase.idle**: The idle phase where no kind of scrolling is occurring.
- **ScrollPhase.interacting**: The interacting phase where the user is interacting with the scroll view.
- **ScrollPhase.tracking**: The tracking phase where the scroll view is tracking a potential scroll by the user but the user hasn’t started a scroll.

## Checking for active scrolling

- **isScrolling**: Whether the scroll view is actively scrolling.

## Responding to scroll view changes

- **onScrollGeometryChange(for:of:action:)**: Adds an action to be performed when a value, created from a scroll geometry, changes.
- **onScrollTargetVisibilityChange(idType:threshold:_:)**: Adds an action to be called with information about what views would be considered visible.
- **onScrollVisibilityChange(threshold:_:)**: Adds an action to be called when the view crosses the threshold to be considered on/off screen.
- **onScrollPhaseChange(_:)**: Adds an action to perform when the scroll phase of the first scroll view in the hierarchy changes.
- **ScrollGeometry**: A type that defines the geometry of a scroll view.
- **ScrollPhaseChangeContext**: A type that provides you with more content when the phase of a scroll view changes.

## Conforms To

- BitwiseCopyable
- Copyable
- CustomDebugStringConvertible
- Equatable
- Hashable
- Sendable
- SendableMetatype

