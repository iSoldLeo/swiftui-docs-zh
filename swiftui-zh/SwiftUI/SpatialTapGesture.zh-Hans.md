--- 来源：https://developer.apple.com/documentation/SwiftUI/SpatialTapGesture
抓取时间：2025-12-02T17:40:52Z

---

# SpatialTapGesture

**Structure**

一种识别一次或多次点击并报告其位置的手势。

## 声明

```swift
struct SpatialTapGesture
```

## 概述

要识别视图上的点击手势，请创建并配置该手势，然后使用 [gesture(_:including:)](View/gesture___including.zh-Hans.md) 修饰符将其添加到视图中。以下代码为 [Circle](Circle.zh-Hans.md) 添加一个点击手势，该手势会根据点击位置切换圆圈的颜色：

```swift
struct TapGestureView: View {
    @State private var location: CGPoint = .zero

    var tap: some Gesture {
        SpatialTapGesture()
            .onEnded { event in
                self.location = event.location
             }
    }

    var body: some View {
        Circle()
            .fill(self.location.y > 50 ? Color.blue : Color.red)
            .frame(width: 100, height: 100, alignment: .center)
            .gesture(tap)
    }
}
```

## 创建空间点击手势

- **init(count:coordinateSpace:)**：创建一个点击手势，并指定所需的点击次数和手势位置的坐标空间。

- **coordinateSpace**：接收位置值的坐标空间。

- **count**：所需的点击事件次数。

## 获取手势的值

- **SpatialTapGesture.Value**：点击手势的属性。

## 已弃用的初始化器

- **init(count:coordinateSpace:)**：创建一个点击手势，并指定所需的点击次数和手势位置的坐标空间。

## 初始化器

- **init(count:coordinateSpace3D:)**：创建一个点击手势，指定所需的点击次数和手势位置的坐标空间。

- **init(count:coordinateSpace:)**：创建一个点击手势，指定所需的点击次数和手势位置的坐标空间。

## 识别点击手势

- **onTapGesture(count:perform:)**：添加一个当此视图识别到点击手势时要执行的操作。

- **onTapGesture(count:coordinateSpace:perform:)**：添加一个当此视图识别到点击手势时要执行的操作，并为该操作提供交互位置。

- **TapGesture**：一个识别一次或多次点击的手势。

## 符合以下规范

- 手势


---
source: https://developer.apple.com/documentation/SwiftUI/SpatialTapGesture
crawled: 2025-12-02T17:40:52Z
---

# SpatialTapGesture

**Structure**

A gesture that recognizes one or more taps and reports their location.

## Declaration

```swift
struct SpatialTapGesture
```

## Overview

To recognize a tap gesture on a view, create and configure the gesture, and then add it to the view using the [gesture(_:including:)](View/gesture___including.zh-Hans.md) modifier. The following code adds a tap gesture to a [Circle](Circle.zh-Hans.md) that toggles the color of the circle based on the tap location:

```swift
struct TapGestureView: View {
    @State private var location: CGPoint = .zero

    var tap: some Gesture {
        SpatialTapGesture()
            .onEnded { event in
                self.location = event.location
             }
    }

    var body: some View {
        Circle()
            .fill(self.location.y > 50 ? Color.blue : Color.red)
            .frame(width: 100, height: 100, alignment: .center)
            .gesture(tap)
    }
}
```

## Creating a spatial tap gesture

- **init(count:coordinateSpace:)**: Creates a tap gesture with the number of required taps and the coordinate space of the gesture’s location.
- **coordinateSpace**: The coordinate space in which to receive location values.
- **count**: The required number of tap events.

## Getting the gesture’s value

- **SpatialTapGesture.Value**: The attributes of a tap gesture.

## Deprecated initializers

- **init(count:coordinateSpace:)**: Creates a tap gesture with the number of required taps and the coordinate space of the gesture’s location.

## Initializers

- **init(count:coordinateSpace3D:)**: Creates a tap gesture with the number of required taps and the coordinate space of the gesture’s location.
- **init(count:coordinateSpace:)**: Creates a tap gesture with the number of required taps and the coordinate space of the gesture’s location.

## Recognizing tap gestures

- **onTapGesture(count:perform:)**: Adds an action to perform when this view recognizes a tap gesture.
- **onTapGesture(count:coordinateSpace:perform:)**: Adds an action to perform when this view recognizes a tap gesture, and provides the action with the location of the interaction.
- **TapGesture**: A gesture that recognizes one or more taps.

## Conforms To

- Gesture

