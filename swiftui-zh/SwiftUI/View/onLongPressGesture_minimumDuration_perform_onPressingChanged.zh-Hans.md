--- 来源：https://developer.apple.com/documentation/SwiftUI/View/onLongPressGesture(minimumDuration:perform:onPressingChanged:)

抓取时间：2025-11-30T21:25:59Z

---

# onLongPressGesture(minimumDuration:perform:onPressingChanged:)

**实例方法**

添加一个操作，当此视图识别到长按手势时执行。

## 声明

```swift
nonisolated func onLongPressGesture(minimumDuration: Double = 0.5, perform action: @escaping () -> Void, onPressingChanged: ((Bool) -> Void)? = nil) -> some View

```

## 参数

- **minimumDuration**：长按操作必须持续的最短时间，超过此时间长短才会成功。

- **action**：识别到长按操作时要执行的操作。

- **onPressingChanged**：当手势的按压状态改变时运行的闭包，并将当前状态作为参数传递。

## 识别长按手势

- **onLongPressGesture(minimumDuration:maximumDistance:perform:onPressingChanged:)**：添加一个操作，当此视图识别到长按手势时执行。

- **onLongTouchGesture(minimumDuration:perform:onTouchingChanged:)**：添加一个操作，当此视图识别到远程长触手势时执行。长触手势是指手指放在远程触控表面上但未实际按压。

- **LongPressGesture**：用户执行长按操作时成功的手势。


---
source: https://developer.apple.com/documentation/SwiftUI/View/onLongPressGesture(minimumDuration:perform:onPressingChanged:)
crawled: 2025-11-30T21:25:59Z
---

# onLongPressGesture(minimumDuration:perform:onPressingChanged:)

**Instance Method**

Adds an action to perform when this view recognizes a long press gesture.

## Declaration

```swift
nonisolated func onLongPressGesture(minimumDuration: Double = 0.5, perform action: @escaping () -> Void, onPressingChanged: ((Bool) -> Void)? = nil) -> some View

```

## Parameters

- **minimumDuration**: The minimum duration of the long press that must elapse before the gesture succeeds.
- **action**: The action to perform when a long press is recognized.
- **onPressingChanged**: A closure to run when the pressing state of the gesture changes, passing the current state as a parameter.

## Recognizing long press gestures

- **onLongPressGesture(minimumDuration:maximumDistance:perform:onPressingChanged:)**: Adds an action to perform when this view recognizes a long press gesture.
- **onLongTouchGesture(minimumDuration:perform:onTouchingChanged:)**: Adds an action to perform when this view recognizes a remote long touch gesture. A long touch gesture is when the finger is on the remote touch surface without actually pressing.
- **LongPressGesture**: A gesture that succeeds when the user performs a long press.

