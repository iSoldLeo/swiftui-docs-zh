---
来源： https://developer.apple.com/documentation/SwiftUI/RotateGesture
抓取时间： 2025-12-02T17:41:02Z
---

# 旋转姿态

**Structure**

识别旋转动作并跟踪旋转角度的手势。

## 声明

```swift
struct RotateGesture
```

## 概览

旋转手势可跟踪旋转事件序列的变化。要在视图中识别旋转手势，需要创建并配置手势，然后使用[gesture(_:including:)](View/gesture___including.zh-Hans.md)修饰符将其添加到视图中。

将旋转手势添加到 [Rectangle](Rectangle.zh-Hans.md) 并应用旋转效果：

```swift
struct RotateGestureView: View {
    @State private var angle = Angle(degrees: 0.0)

    var rotation: some Gesture {
        RotateGesture()
            .onChanged { value in
                angle = value.rotation
            }
    }

    var body: some View {
        Rectangle()
            .frame(width: 200, height: 200, alignment: .center)
            .rotationEffect(angle)
            .gesture(rotation)
    }
}
```

## 创建手势

- **init(minimumAngleDelta:)**：创建一个旋转手势，手势开始时的最小 delta 值为 **init(minimumAngleDelta:)**: 创建一个旋转手势。
- **minimumAngleDelta**：手势成功前所需的最小 delta 值。

## 识别随时间变化的手势

- **gesture(_:)**：将[NSGestureRecognizerRepresentable](NSGestureRecognizerRepresentable.zh-Hans.md) 附加到视图。
- **gesture(_:isEnabled:)**：将手势附加到视图，其优先级低于视图定义的手势。
- **gesture(_:name:isEnabled:)**：将手势附加到视图，其优先级低于视图定义的手势。
- **gesture(_:including:)**：将手势附加到视图，其优先级低于视图定义的手势。
- **DragGesture**：随着拖动事件序列变化而调用动作的拖动动作。
- **WindowDragGesture**：可识别拖动窗口的动作并进行处理的手势。
- **MagnifyGesture**：识别放大动作并跟踪放大量的手势。
- **RotateGesture3D**：能识别三维旋转运动并跟踪旋转角度和轴线的手势。
- **GestureMask**：控制在视图中添加手势如何影响视图及其子视图所识别的其他手势的选项。

## 符合

- 手势


---
source: https://developer.apple.com/documentation/SwiftUI/RotateGesture
crawled: 2025-12-02T17:41:02Z
---

# RotateGesture

**Structure**

A gesture that recognizes a rotation motion and tracks the angle of the rotation.

## Declaration

```swift
struct RotateGesture
```

## Overview

A rotate gesture tracks how a rotation event sequence changes. To recognize a rotate gesture on a view, create and configure the gesture, and then add it to the view using the [gesture(_:including:)](View/gesture___including.zh-Hans.md) modifier.

Add a rotate gesture to a [Rectangle](Rectangle.zh-Hans.md) and apply a rotation effect:

```swift
struct RotateGestureView: View {
    @State private var angle = Angle(degrees: 0.0)

    var rotation: some Gesture {
        RotateGesture()
            .onChanged { value in
                angle = value.rotation
            }
    }

    var body: some View {
        Rectangle()
            .frame(width: 200, height: 200, alignment: .center)
            .rotationEffect(angle)
            .gesture(rotation)
    }
}
```

## Creating the gesture

- **init(minimumAngleDelta:)**: Creates a rotation gesture with a minimum delta for the gesture to start.
- **minimumAngleDelta**: The minimum delta required before the gesture succeeds.

## Recognizing gestures that change over time

- **gesture(_:)**: Attaches an [NSGestureRecognizerRepresentable](NSGestureRecognizerRepresentable.zh-Hans.md) to the view.
- **gesture(_:isEnabled:)**: Attaches a gesture to the view with a lower precedence than gestures defined by the view.
- **gesture(_:name:isEnabled:)**: Attaches a gesture to the view with a lower precedence than gestures defined by the view.
- **gesture(_:including:)**: Attaches a gesture to the view with a lower precedence than gestures defined by the view.
- **DragGesture**: A dragging motion that invokes an action as the drag-event sequence changes.
- **WindowDragGesture**: A gesture that recognizes the motion of and handles dragging a window.
- **MagnifyGesture**: A gesture that recognizes a magnification motion and tracks the amount of magnification.
- **RotateGesture3D**: A gesture that recognizes 3D rotation motion and tracks the angle and axis of the rotation.
- **GestureMask**: Options that control how adding a gesture to a view affects other gestures recognized by the view and its subviews.

## Conforms To

- Gesture

