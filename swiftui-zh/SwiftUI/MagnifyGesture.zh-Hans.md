---
来源： https://developer.apple.com/documentation/SwiftUI/MagnifyGesture
抓取时间： 2025-12-02T17:41:01Z
---

# MagnifyGesture

**Structure**

识别放大动作并跟踪放大量的手势。

## 声明

```swift
struct MagnifyGesture
```

## 概览

放大手势可跟踪放大事件序列的变化。要在视图上识别放大手势，请创建并配置手势，然后使用[gesture(_:including:)](View/gesture___including.zh-Hans.md)修饰符将其添加到视图中。

将放大手势添加到[Circle](Circle.zh-Hans.md)中，在用户执行手势的同时改变其大小：

```swift
struct MagnifyGestureView: View {
    @GestureState private var magnifyBy = 1.0

    var magnification: some Gesture {
        MagnifyGesture()
            .updating($magnifyBy) { value, gestureState, transaction in
                gestureState = value.magnification
            }
    }

    var body: some View {
        Circle()
            .frame(width: 100, height: 100)
            .scaleEffect(magnifyBy)
            .gesture(magnification)
    }
}
```

## 创建手势

- **init(minimumScaleDelta:)**：创建一个放大手势，手势开始时的最小延迟为给定值。
- **minimumScaleDelta**：手势开始前所需的最小 delta 值。

## 识别随时间变化的手势

- **gesture(_:)**：将[NSGestureRecognizerRepresentable](NSGestureRecognizerRepresentable.zh-Hans.md) 附加到视图。
- **gesture(_:isEnabled:)**：将手势附加到视图，其优先级低于视图定义的手势。
- **gesture(_:name:isEnabled:)**：将手势附加到视图，其优先级低于视图定义的手势。
- **gesture(_:including:)**：将手势附加到视图，其优先级低于视图定义的手势。
- **DragGesture**：随着拖动事件序列变化而调用动作的拖动动作。
- **WindowDragGesture**：可识别拖动窗口的动作并进行处理的手势。
- **RotateGesture**：可识别旋转动作并跟踪旋转角度的手势。
- **RotateGesture3D**：能识别三维旋转运动并跟踪旋转角度和轴线的手势。
- **GestureMask**：控制在视图中添加手势如何影响视图及其子视图所识别的其他手势的选项。

## 符合

- 手势


---
source: https://developer.apple.com/documentation/SwiftUI/MagnifyGesture
crawled: 2025-12-02T17:41:01Z
---

# MagnifyGesture

**Structure**

A gesture that recognizes a magnification motion and tracks the amount of magnification.

## Declaration

```swift
struct MagnifyGesture
```

## Overview

A magnify gesture tracks how a magnification event sequence changes. To recognize a magnify gesture on a view, create and configure the gesture, and then add it to the view using the [gesture(_:including:)](View/gesture___including.zh-Hans.md) modifier.

Add a magnify gesture to a [Circle](Circle.zh-Hans.md) that changes its size while the user performs the gesture:

```swift
struct MagnifyGestureView: View {
    @GestureState private var magnifyBy = 1.0

    var magnification: some Gesture {
        MagnifyGesture()
            .updating($magnifyBy) { value, gestureState, transaction in
                gestureState = value.magnification
            }
    }

    var body: some View {
        Circle()
            .frame(width: 100, height: 100)
            .scaleEffect(magnifyBy)
            .gesture(magnification)
    }
}
```

## Creating the gesture

- **init(minimumScaleDelta:)**: Creates a magnify gesture with a given minimum delta for the gesture to start.
- **minimumScaleDelta**: The minimum required delta before the gesture starts.

## Recognizing gestures that change over time

- **gesture(_:)**: Attaches an [NSGestureRecognizerRepresentable](NSGestureRecognizerRepresentable.zh-Hans.md) to the view.
- **gesture(_:isEnabled:)**: Attaches a gesture to the view with a lower precedence than gestures defined by the view.
- **gesture(_:name:isEnabled:)**: Attaches a gesture to the view with a lower precedence than gestures defined by the view.
- **gesture(_:including:)**: Attaches a gesture to the view with a lower precedence than gestures defined by the view.
- **DragGesture**: A dragging motion that invokes an action as the drag-event sequence changes.
- **WindowDragGesture**: A gesture that recognizes the motion of and handles dragging a window.
- **RotateGesture**: A gesture that recognizes a rotation motion and tracks the angle of the rotation.
- **RotateGesture3D**: A gesture that recognizes 3D rotation motion and tracks the angle and axis of the rotation.
- **GestureMask**: Options that control how adding a gesture to a view affects other gestures recognized by the view and its subviews.

## Conforms To

- Gesture

