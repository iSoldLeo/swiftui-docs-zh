---
来源： https://developer.apple.com/documentation/SwiftUI/RotateGesture3D
抓取时间： 2025-12-02T17:41:03Z
---

# RotateGesture3D

**Structure**

可识别 3D 旋转运动并跟踪旋转角度和轴线的手势。

## 声明

```swift
struct RotateGesture3D
```

## 概览

您可以限制该手势以识别围绕特定 3D 轴的旋转。例如，`RotateGesture3D(constrainedToAxis: .x)` 创建的手势只能识别围绕全局 X 轴的旋转。您提供的轴将被归一化。

旋转手势可跟踪旋转事件序列的变化。要在视图中识别旋转手势，请创建并配置手势，然后使用[gesture(_:including:)](View/gesture___including.zh-Hans.md) 修改器将其添加到视图中。

## 创建手势

- **init(constrainedToAxis:minimumAngleDelta:)**：创建一个旋转手势，手势的起始点和轴线的最小三角洲值用于限制旋转测量。
- **minimumAngleDelta**：手势激活前的最小角度三角。
- **constrainedAxis**：限制旋转的轴线。

## 识别随时间变化的手势

- **gesture(_:)**：将[NSGestureRecognizerRepresentable](NSGestureRecognizerRepresentable.zh-Hans.md) 附加到视图。
- **gesture(_:isEnabled:)**：将手势附加到视图，其优先级低于视图定义的手势。
- **gesture(_:name:isEnabled:)**：将手势附加到视图，其优先级低于视图定义的手势。
- **gesture(_:including:)**：将手势附加到视图，其优先级低于视图定义的手势。
- **DragGesture**：随着拖动事件序列变化而调用动作的拖动动作。
- **WindowDragGesture**：可识别拖动窗口的动作并进行处理的手势。
- **MagnifyGesture**：能识别放大动作并跟踪放大量的手势。
- **RotateGesture**：能识别旋转动作并跟踪旋转角度的手势。
- **GestureMask**：控制向视图添加手势如何影响视图及其子视图所识别的其他手势的选项。

## 符合

- 手势


---
source: https://developer.apple.com/documentation/SwiftUI/RotateGesture3D
crawled: 2025-12-02T17:41:03Z
---

# RotateGesture3D

**Structure**

A gesture that recognizes 3D rotation motion and tracks the angle and axis of the rotation.

## Declaration

```swift
struct RotateGesture3D
```

## Overview

You can constrain this gesture to recognize rotation about a specific 3D axis. For example, `RotateGesture3D(constrainedToAxis: .x)` creates a gesture that recognizes rotation only around the global X axis. The axis you provide will be normalized.

A rotation gesture tracks how a rotation event sequence changes. To recognize a rotation gesture on a view, create and configure the gesture, and then add it to the view using the [gesture(_:including:)](View/gesture___including.zh-Hans.md) modifier.

## Creating the gesture

- **init(constrainedToAxis:minimumAngleDelta:)**: Creates a rotation gesture with a minimum delta for the gesture to start and axis to constrain measurement of rotation.
- **minimumAngleDelta**: The minimum angle delta before the gesture becomes active.
- **constrainedAxis**: An axis around which the rotation is constrained.

## Recognizing gestures that change over time

- **gesture(_:)**: Attaches an [NSGestureRecognizerRepresentable](NSGestureRecognizerRepresentable.zh-Hans.md) to the view.
- **gesture(_:isEnabled:)**: Attaches a gesture to the view with a lower precedence than gestures defined by the view.
- **gesture(_:name:isEnabled:)**: Attaches a gesture to the view with a lower precedence than gestures defined by the view.
- **gesture(_:including:)**: Attaches a gesture to the view with a lower precedence than gestures defined by the view.
- **DragGesture**: A dragging motion that invokes an action as the drag-event sequence changes.
- **WindowDragGesture**: A gesture that recognizes the motion of and handles dragging a window.
- **MagnifyGesture**: A gesture that recognizes a magnification motion and tracks the amount of magnification.
- **RotateGesture**: A gesture that recognizes a rotation motion and tracks the angle of the rotation.
- **GestureMask**: Options that control how adding a gesture to a view affects other gestures recognized by the view and its subviews.

## Conforms To

- Gesture

