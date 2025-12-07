--- 来源：https://developer.apple.com/documentation/SwiftUI/TapGesture
抓取时间：2025-12-02T17:40:52Z

---

# TapGesture

**Structure**

一种识别一次或多次点击的手势。

## 声明

```swift
struct TapGesture
```

## 概述

要在视图上识别点击手势，请创建并配置该手势，然后使用 [gesture(_:including:)](View/gesture___including.zh-Hans.md) 修饰符将其添加到视图中。以下代码向 [Circle](Circle.zh-Hans.md) 添加了一个点击手势，用于切换圆圈的颜色：

```swift
struct TapGestureView: View {
    @State private var tapped = false

    var tap: some Gesture {
        TapGesture(count: 1)
            .onEnded { _ in self.tapped = !self.tapped }
    }

    var body: some View {
        Circle()
            .fill(self.tapped ? Color.blue : Color.red)
            .frame(width: 100, height: 100, alignment: .center)
            .gesture(tap)
    }
}
```

## 创建点击手势

- **init(count:)**：创建一个包含所需点击次数的点击手势。

- **count**：所需的点击事件数量。

## 识别点击手势

- **onTapGesture(count:perform:)**：添加一个当此视图识别到点击手势时要执行的操作。

- **onTapGesture(count:coordinateSpace:perform:)**：添加一个当此视图识别到点击手势时要执行的操作，并为该操作提供交互位置信息。

- **SpatialTapGesture**：一种能够识别一次或多次点击并报告其位置的手势。

## 符合以下规范

- 手势


---
source: https://developer.apple.com/documentation/SwiftUI/TapGesture
crawled: 2025-12-02T17:40:52Z
---

# TapGesture

**Structure**

A gesture that recognizes one or more taps.

## Declaration

```swift
struct TapGesture
```

## Overview

To recognize a tap gesture on a view, create and configure the gesture, and then add it to the view using the [gesture(_:including:)](View/gesture___including.zh-Hans.md) modifier. The following code adds a tap gesture to a [Circle](Circle.zh-Hans.md) that toggles the color of the circle:

```swift
struct TapGestureView: View {
    @State private var tapped = false

    var tap: some Gesture {
        TapGesture(count: 1)
            .onEnded { _ in self.tapped = !self.tapped }
    }

    var body: some View {
        Circle()
            .fill(self.tapped ? Color.blue : Color.red)
            .frame(width: 100, height: 100, alignment: .center)
            .gesture(tap)
    }
}
```

## Creating a tap gesture

- **init(count:)**: Creates a tap gesture with the number of required taps.
- **count**: The required number of tap events.

## Recognizing tap gestures

- **onTapGesture(count:perform:)**: Adds an action to perform when this view recognizes a tap gesture.
- **onTapGesture(count:coordinateSpace:perform:)**: Adds an action to perform when this view recognizes a tap gesture, and provides the action with the location of the interaction.
- **SpatialTapGesture**: A gesture that recognizes one or more taps and reports their location.

## Conforms To

- Gesture

