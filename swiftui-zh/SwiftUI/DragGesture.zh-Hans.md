---
来源： https://developer.apple.com/documentation/SwiftUI/DragGesture
抓取时间： 2025-12-02T16:22:52Z
---

# DragGesture

**Structure**

随着拖动事件序列变化而调用动作的拖动动作。

## 声明

```swift
struct DragGesture
```

## 概览

要在视图中识别拖动手势，请创建并配置手势，然后使用 [gesture(_:including:)](View/gesture___including.zh-Hans.md) 修改器将其添加到视图中。

将拖曳手势添加到[Circle](Circle.zh-Hans.md) 中，并在用户执行拖曳手势时更改其颜色：

```swift
struct DragGestureView: View {
    @State private var isDragging = false

    var drag: some Gesture {
        DragGesture()
            .onChanged { _ in self.isDragging = true }
            .onEnded { _ in self.isDragging = false }
    }

    var body: some View {
        Circle()
            .fill(self.isDragging ? Color.red : Color.blue)
            .frame(width: 100, height: 100, alignment: .center)
            .gesture(drag)
    }
}
```

## 创建拖动手势

- **init(minimumDistance:coordinateSpace:)**：创建拖曳手势，并设置手势成功前的最小拖曳距离和手势位置的坐标空间。
- **minimumDistance**：手势成功前的最小拖动距离。
- **coordinateSpace**：接收位置值的坐标空间。

## 过时的初始化程序

- **init(minimumDistance:coordinateSpace:)**：创建一个拖动手势，手势成功前的最小拖动距离以及手势位置的坐标空间。

### 结构

- **DragGesture.Value**：拖动手势的属性。

## 初始化器

- **init(minimumDistance:coordinateSpace3D:)**：创建拖动手势，并设置手势成功前的最小拖动距离以及手势位置的坐标空间。
- **init(minimumDistance:coordinateSpace:)**：创建一个拖动手势，手势成功前的最小拖动距离和手势位置的坐标空间。

## 识别随时间变化的手势

- **gesture(_:)**：将[NSGestureRecognizerRepresentable](NSGestureRecognizerRepresentable.zh-Hans.md)附加到视图中。
- **gesture(_:isEnabled:)**：将手势附加到视图，其优先级低于视图定义的手势。
- **gesture(_:name:isEnabled:)**：将手势附加到视图，其优先级低于视图定义的手势。
- **gesture(_:including:)**：将手势附加到视图，其优先级低于视图定义的手势。
- **WindowDragGesture**：可识别拖动窗口的动作并进行处理的手势。
- **MagnifyGesture**：可识别放大动作并跟踪放大量的手势。
- **RotateGesture**：能识别旋转动作并跟踪旋转角度的手势。
- **RotateGesture3D**：能识别三维旋转运动并跟踪旋转角度和轴线的手势。
- **GestureMask**：控制在视图中添加手势如何影响视图及其子视图所识别的其他手势的选项。

## 符合

- 手势


---
source: https://developer.apple.com/documentation/SwiftUI/DragGesture
crawled: 2025-12-02T16:22:52Z
---

# DragGesture

**Structure**

A dragging motion that invokes an action as the drag-event sequence changes.

## Declaration

```swift
struct DragGesture
```

## Overview

To recognize a drag gesture on a view, create and configure the gesture, and then add it to the view using the [gesture(_:including:)](View/gesture___including.zh-Hans.md) modifier.

Add a drag gesture to a [Circle](Circle.zh-Hans.md) and change its color while the user performs the drag gesture:

```swift
struct DragGestureView: View {
    @State private var isDragging = false

    var drag: some Gesture {
        DragGesture()
            .onChanged { _ in self.isDragging = true }
            .onEnded { _ in self.isDragging = false }
    }

    var body: some View {
        Circle()
            .fill(self.isDragging ? Color.red : Color.blue)
            .frame(width: 100, height: 100, alignment: .center)
            .gesture(drag)
    }
}
```

## Creating a drag gesture

- **init(minimumDistance:coordinateSpace:)**: Creates a dragging gesture with the minimum dragging distance before the gesture succeeds and the coordinate space of the gesture’s location.
- **minimumDistance**: The minimum dragging distance before the gesture succeeds.
- **coordinateSpace**: The coordinate space in which to receive location values.

## Deprecated initializers

- **init(minimumDistance:coordinateSpace:)**: Creates a dragging gesture with the minimum dragging distance before the gesture succeeds and the coordinate space of the gesture’s location.

## Structures

- **DragGesture.Value**: The attributes of a drag gesture.

## Initializers

- **init(minimumDistance:coordinateSpace3D:)**: Creates a dragging gesture with the minimum dragging distance before the gesture succeeds and the coordinate space of the gesture’s location.
- **init(minimumDistance:coordinateSpace:)**: Creates a dragging gesture with the minimum dragging distance before the gesture succeeds and the coordinate space of the gesture’s location.

## Recognizing gestures that change over time

- **gesture(_:)**: Attaches an [NSGestureRecognizerRepresentable](NSGestureRecognizerRepresentable.zh-Hans.md) to the view.
- **gesture(_:isEnabled:)**: Attaches a gesture to the view with a lower precedence than gestures defined by the view.
- **gesture(_:name:isEnabled:)**: Attaches a gesture to the view with a lower precedence than gestures defined by the view.
- **gesture(_:including:)**: Attaches a gesture to the view with a lower precedence than gestures defined by the view.
- **WindowDragGesture**: A gesture that recognizes the motion of and handles dragging a window.
- **MagnifyGesture**: A gesture that recognizes a magnification motion and tracks the amount of magnification.
- **RotateGesture**: A gesture that recognizes a rotation motion and tracks the angle of the rotation.
- **RotateGesture3D**: A gesture that recognizes 3D rotation motion and tracks the angle and axis of the rotation.
- **GestureMask**: Options that control how adding a gesture to a view affects other gestures recognized by the view and its subviews.

## Conforms To

- Gesture

