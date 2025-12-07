--- 来源：https://developer.apple.com/documentation/SwiftUI/View/onLongTouchGesture(minimumDuration:perform:onTouchingChanged:)

抓取时间：2025-12-02T17:40:54Z

---

# onLongTouchGesture(minimumDuration:perform:onTouchingChanged:)

**实例方法**

当此视图识别到远程长按手势时，添加要执行的操作。长按手势是指手指停留在远程触控表面上但未实际按压。

## 声明

```swift
nonisolated func onLongTouchGesture(minimumDuration: Double = 0.5, perform action: @escaping () -> Void, onTouchingChanged: ((Bool) -> Void)? = nil) -> some View

```

## 参数

- **minimumDuration**：长按手势成功所需的最短持续时间。

- **action**：识别到长按时要执行的操作

- **onTouchingChanged**：手势触摸状态改变时要运行的闭包，并将当前状态作为参数传递。

## 识别长按手势

- **onLongPressGesture(minimumDuration:maximumDistance:perform:onPressingChanged:)**：添加一个当此视图识别到长按手势时要执行的操作。

- **onLongPressGesture(minimumDuration:perform:onPressingChanged:)**：添加一个当此视图识别到长按手势时要执行的操作。

- **LongPressGesture**：用户执行长按操作时成功的手势。


---
source: https://developer.apple.com/documentation/SwiftUI/View/onLongTouchGesture(minimumDuration:perform:onTouchingChanged:)
crawled: 2025-12-02T17:40:54Z
---

# onLongTouchGesture(minimumDuration:perform:onTouchingChanged:)

**Instance Method**

Adds an action to perform when this view recognizes a remote long touch gesture. A long touch gesture is when the finger is on the remote touch surface without actually pressing.

## Declaration

```swift
nonisolated func onLongTouchGesture(minimumDuration: Double = 0.5, perform action: @escaping () -> Void, onTouchingChanged: ((Bool) -> Void)? = nil) -> some View

```

## Parameters

- **minimumDuration**: The minimum duration of the long touch that must elapse before the gesture succeeds.
- **action**: The action to perform when a long touch is recognized
- **onTouchingChanged**: A closure to run when the touching state of the gesture changes, passing the current state as a parameter.

## Recognizing long press gestures

- **onLongPressGesture(minimumDuration:maximumDistance:perform:onPressingChanged:)**: Adds an action to perform when this view recognizes a long press gesture.
- **onLongPressGesture(minimumDuration:perform:onPressingChanged:)**: Adds an action to perform when this view recognizes a long press gesture.
- **LongPressGesture**: A gesture that succeeds when the user performs a long press.

