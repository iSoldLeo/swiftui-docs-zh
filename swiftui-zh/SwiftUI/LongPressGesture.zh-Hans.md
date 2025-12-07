---
来源： https://developer.apple.com/documentation/SwiftUI/LongPressGesture
抓取时间： 2025-12-02T17:40:55Z
---

# 长按手势

**Structure**

当用户执行长按时成功做出的手势。

## 声明

```swift
struct LongPressGesture
```

## 概览

要在视图中识别长按手势，请创建并配置该手势，然后使用[gesture(_:including:)](View/gesture___including.zh-Hans.md)修饰符将其添加到视图中。

为[Circle](Circle.zh-Hans.md)添加长按手势，使其颜色从蓝色变为红色，然后在手势结束时将其变为绿色：

```swift
struct LongPressGestureView: View {
    @GestureState private var isDetectingLongPress = false
    @State private var completedLongPress = false

    var longPress: some Gesture {
        LongPressGesture(minimumDuration: 3)
            .updating($isDetectingLongPress) { currentState, gestureState,
                    transaction in
                gestureState = currentState
                transaction.animation = Animation.easeIn(duration: 2.0)
            }
            .onEnded { finished in
                self.completedLongPress = finished
            }
    }

    var body: some View {
        Circle()
            .fill(self.isDetectingLongPress ?
                Color.red :
                (self.completedLongPress ? Color.green : Color.blue))
            .frame(width: 100, height: 100, alignment: .center)
            .gesture(longPress)
    }
}
```

## 创建长按手势

- **init(minimumDuration:)**：创建持续时间最短的长按手势
- **init(minimumDuration:maximumDistance:)**：创建一个长按手势，该手势具有最短持续时间和交互失败前可移动的最大距离。
- **minimumDuration**：手势成功前长按的最短持续时间。
- **maximumDistance**：手势失败前长按所能移动的最大距离。

## 识别长按手势

- **onLongPressGesture(minimumDuration:maximumDistance:perform:onPressingChanged:)**：添加该视图识别长按手势时要执行的操作。
- **onLongPressGesture(minimumDuration:perform:onPressingChanged:)**：添加该视图识别长按手势时要执行的操作。
- **onLongTouchGesture(minimumDuration:perform:onTouchingChanged:)**：当该视图识别到远程长触手势时添加要执行的操作。长按手势是指手指放在远程触摸表面上，但没有实际按压。

## 符合

- 手势


---
source: https://developer.apple.com/documentation/SwiftUI/LongPressGesture
crawled: 2025-12-02T17:40:55Z
---

# LongPressGesture

**Structure**

A gesture that succeeds when the user performs a long press.

## Declaration

```swift
struct LongPressGesture
```

## Overview

To recognize a long-press gesture on a view, create and configure the gesture, then add it to the view using the [gesture(_:including:)](View/gesture___including.zh-Hans.md) modifier.

Add a long-press gesture to a [Circle](Circle.zh-Hans.md) to animate its color from blue to red, and then change it to green when the gesture ends:

```swift
struct LongPressGestureView: View {
    @GestureState private var isDetectingLongPress = false
    @State private var completedLongPress = false

    var longPress: some Gesture {
        LongPressGesture(minimumDuration: 3)
            .updating($isDetectingLongPress) { currentState, gestureState,
                    transaction in
                gestureState = currentState
                transaction.animation = Animation.easeIn(duration: 2.0)
            }
            .onEnded { finished in
                self.completedLongPress = finished
            }
    }

    var body: some View {
        Circle()
            .fill(self.isDetectingLongPress ?
                Color.red :
                (self.completedLongPress ? Color.green : Color.blue))
            .frame(width: 100, height: 100, alignment: .center)
            .gesture(longPress)
    }
}
```

## Creating a long press gesture

- **init(minimumDuration:)**: Creates a long-press gesture with a minimum duration
- **init(minimumDuration:maximumDistance:)**: Creates a long-press gesture with a minimum duration and a maximum distance that the interaction can move before the gesture fails.
- **minimumDuration**: The minimum duration of the long press that must elapse before the gesture succeeds.
- **maximumDistance**: The maximum distance that the long press can move before the gesture fails.

## Recognizing long press gestures

- **onLongPressGesture(minimumDuration:maximumDistance:perform:onPressingChanged:)**: Adds an action to perform when this view recognizes a long press gesture.
- **onLongPressGesture(minimumDuration:perform:onPressingChanged:)**: Adds an action to perform when this view recognizes a long press gesture.
- **onLongTouchGesture(minimumDuration:perform:onTouchingChanged:)**: Adds an action to perform when this view recognizes a remote long touch gesture. A long touch gesture is when the finger is on the remote touch surface without actually pressing.

## Conforms To

- Gesture

