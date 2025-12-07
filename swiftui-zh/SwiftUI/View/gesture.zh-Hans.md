--- 来源：https://developer.apple.com/documentation/SwiftUI/View/gesture(_:)

抓取时间：2025-12-02T17:40:58Z

---

# gesture(_:)

**实例方法**

将一个 [NSGestureRecognizerRepresentable](../NSGestureRecognizerRepresentable.zh-Hans.md) 附加到视图。

## 声明

```swift
nonisolated func gesture(_ representable: some NSGestureRecognizerRepresentable) -> some View

```

## 参数

- **representable**：创建和管理手势识别器的 [NSGestureRecognizerRepresentable](../NSGestureRecognizerRepresentable.zh-Hans.md)。

## 返回值

一个附加了 [NSGestureRecognizerRepresentable](../NSGestureRecognizerRepresentable.zh-Hans.md) 的视图。

## 识别随时间变化的手势

- **gesture(_:isEnabled:)**：将一个优先级低于视图定义的手势的手势附加到视图。

- **gesture(_:name:isEnabled:)**：将一个手势附加到视图，其优先级低于视图自身定义的手势。

- **gesture(_:including:)**：将一个手势附加到视图，其优先级低于视图自身定义的手势。

- **DragGesture**：拖动动作，当拖动事件序列发生变化时触发相应的操作。

- **WindowDragGesture**：识别并处理窗口拖动动作的手势。

- **MagnifyGesture**：识别放大动作并跟踪放大倍数的手势。

- **RotateGesture**：识别旋转动作并跟踪旋转角度的手势。

- **RotateGesture3D**：一种识别 3D 旋转运动并跟踪旋转角度和轴的手势。

- **GestureMask**：用于控制向视图添加手势如何影响该视图及其子视图识别的其他手势的选项。


---
source: https://developer.apple.com/documentation/SwiftUI/View/gesture(_:)
crawled: 2025-12-02T17:40:58Z
---

# gesture(_:)

**Instance Method**

Attaches an [NSGestureRecognizerRepresentable](../NSGestureRecognizerRepresentable.zh-Hans.md) to the view.

## Declaration

```swift
nonisolated func gesture(_ representable: some NSGestureRecognizerRepresentable) -> some View

```

## Parameters

- **representable**: The [NSGestureRecognizerRepresentable](../NSGestureRecognizerRepresentable.zh-Hans.md) that creates and manages a gesture recognizer.

## Return Value

A view with an [NSGestureRecognizerRepresentable](../NSGestureRecognizerRepresentable.zh-Hans.md) attached.

## Recognizing gestures that change over time

- **gesture(_:isEnabled:)**: Attaches a gesture to the view with a lower precedence than gestures defined by the view.
- **gesture(_:name:isEnabled:)**: Attaches a gesture to the view with a lower precedence than gestures defined by the view.
- **gesture(_:including:)**: Attaches a gesture to the view with a lower precedence than gestures defined by the view.
- **DragGesture**: A dragging motion that invokes an action as the drag-event sequence changes.
- **WindowDragGesture**: A gesture that recognizes the motion of and handles dragging a window.
- **MagnifyGesture**: A gesture that recognizes a magnification motion and tracks the amount of magnification.
- **RotateGesture**: A gesture that recognizes a rotation motion and tracks the angle of the rotation.
- **RotateGesture3D**: A gesture that recognizes 3D rotation motion and tracks the angle and axis of the rotation.
- **GestureMask**: Options that control how adding a gesture to a view affects other gestures recognized by the view and its subviews.

