--- 来源：https://developer.apple.com/documentation/SwiftUI/WindowDragGesture
抓取时间：2025-12-02T17:41:01Z

---

# WindowDragGesture

**Structure**

一种识别并处理窗口拖动的手势。

## 声明

```swift
struct WindowDragGesture
```

## 概述

要识别视图上的窗口拖动手势，请创建并配置该手势，然后使用 [gesture(_:isEnabled:)](View/gesture___isEnabled.zh-Hans.md) 修饰符将其添加到视图。建议同时启用 [doc://com.apple.documentation/documentation/SwiftUI/View/allowsWindowActivationEvents(_:)] 修饰符，以便即使窗口处于非活动状态，拖动包含窗口的操作也能正常工作。

要为 [Circle](Circle.zh-Hans.md) 添加窗口拖动手势，并在用户执行该手势时更改其颜色：

```swift
struct MyView: View {
    @GestureState var isDraggingWindow = false

    var dragWindow: some Gesture {
        WindowDragGesture()
            .updating($isDraggingWindow) { _, state, _ in
                state = true
            }
    }

    var body: some View {
        Circle()
            .fill(isDraggingWindow ? Color.green : .blue)
            .frame(width: 50, height: 50)
            .gesture(dragWindow)
            .allowsWindowActivationEvents()
    }
}
```

## 结构体

- **WindowDragGesture.Value**：窗口拖动手势的属性。

## 初始化器

- **init()**：创建窗口拖动手势。

## 识别随时间变化的手势

- **gesture(_:)**：将 [NSGestureRecognizerRepresentable](NSGestureRecognizerRepresentable.zh-Hans.md) 附加到视图。

- **gesture(_:isEnabled:)**：将一个优先级低于视图自身定义的手势的手势附加到视图。

- **gesture(_:name:isEnabled:)**：将一个优先级低于视图自身定义的手势的手势附加到视图。

- **gesture(_:including:)**：将手势附加到视图，其优先级低于视图自身定义的手势。

- **DragGesture**：拖动动作，当拖动事件序列发生变化时触发相应的操作。

- **MagnifyGesture**：识别放大动作并跟踪放大倍数的手势。

- **RotateGesture**：识别旋转动作并跟踪旋转角度的手势。

- **RotateGesture3D**：识别 3D 旋转动作并跟踪旋转角度和轴的手势。

- **GestureMask**：控制向视图添加手势如何影响视图及其子视图识别的其他手势的选项。

## 符合以下规范

- 手势


---
source: https://developer.apple.com/documentation/SwiftUI/WindowDragGesture
crawled: 2025-12-02T17:41:01Z
---

# WindowDragGesture

**Structure**

A gesture that recognizes the motion of and handles dragging a window.

## Declaration

```swift
struct WindowDragGesture
```

## Overview

To recognize a window drag gesture on a view, create and configure the gesture, and then add it to the view using the [gesture(_:isEnabled:)](View/gesture___isEnabled.zh-Hans.md) modifier. Consider also letting the gesture [doc://com.apple.documentation/documentation/SwiftUI/View/allowsWindowActivationEvents(_:)] so that dragging the containing window works even when it’s inactive.

To add a window drag gesture to a [Circle](Circle.zh-Hans.md) and change its color while a user performs the window drag gesture:

```swift
struct MyView: View {
    @GestureState var isDraggingWindow = false

    var dragWindow: some Gesture {
        WindowDragGesture()
            .updating($isDraggingWindow) { _, state, _ in
                state = true
            }
    }

    var body: some View {
        Circle()
            .fill(isDraggingWindow ? Color.green : .blue)
            .frame(width: 50, height: 50)
            .gesture(dragWindow)
            .allowsWindowActivationEvents()
    }
}
```

## Structures

- **WindowDragGesture.Value**: The properties of a window drag gesture.

## Initializers

- **init()**: Creates a window drag gesture.

## Recognizing gestures that change over time

- **gesture(_:)**: Attaches an [NSGestureRecognizerRepresentable](NSGestureRecognizerRepresentable.zh-Hans.md) to the view.
- **gesture(_:isEnabled:)**: Attaches a gesture to the view with a lower precedence than gestures defined by the view.
- **gesture(_:name:isEnabled:)**: Attaches a gesture to the view with a lower precedence than gestures defined by the view.
- **gesture(_:including:)**: Attaches a gesture to the view with a lower precedence than gestures defined by the view.
- **DragGesture**: A dragging motion that invokes an action as the drag-event sequence changes.
- **MagnifyGesture**: A gesture that recognizes a magnification motion and tracks the amount of magnification.
- **RotateGesture**: A gesture that recognizes a rotation motion and tracks the angle of the rotation.
- **RotateGesture3D**: A gesture that recognizes 3D rotation motion and tracks the angle and axis of the rotation.
- **GestureMask**: Options that control how adding a gesture to a view affects other gestures recognized by the view and its subviews.

## Conforms To

- Gesture

