--- 来源：https://developer.apple.com/documentation/SwiftUI/View/onLongPressGesture(minimumDuration:maximumDistance:perform:onPressingChanged:)

抓取时间：2025-11-30T21:25:58Z

---

# onLongPressGesture(minimumDuration:maximumDistance:perform:onPressingChanged:)

**实例方法**

添加一个操作，当此视图识别到长按手势时执行。

## 声明

```swift
nonisolated func onLongPressGesture(minimumDuration: Double = 0.5, maximumDistance: CGFloat = 10, perform action: @escaping () -> Void, onPressingChanged: ((Bool) -> Void)? = nil) -> some View

```

## 参数

- **minimumDuration**：长按操作必须持续的最短时间，超过此时间手势才会成功。

- **maximumDistance**：执行长按操作的手指或光标可以移动的最大距离，超过此距离手势将失败。

- **action**：识别到长按时要执行的操作。

- **onPressingChanged**：手势按下状态改变时要运行的闭包，并将当前状态作为参数传递。

## 识别长按手势

- **onLongPressGesture(minimumDuration:perform:onPressingChanged:)**：添加一个操作，当此视图识别到长按手势时要执行。

- **onLongTouchGesture(minimumDuration:perform:onTouchingChanged:)**：添加一个操作，当此视图识别到远程长触手势时要执行。长触手势是指手指放在远程触控表面上但未实际按下。

- **LongPressGesture**：用户执行长按操作时成功的手势。


---
source: https://developer.apple.com/documentation/SwiftUI/View/onLongPressGesture(minimumDuration:maximumDistance:perform:onPressingChanged:)
crawled: 2025-11-30T21:25:58Z
---

# onLongPressGesture(minimumDuration:maximumDistance:perform:onPressingChanged:)

**Instance Method**

Adds an action to perform when this view recognizes a long press gesture.

## Declaration

```swift
nonisolated func onLongPressGesture(minimumDuration: Double = 0.5, maximumDistance: CGFloat = 10, perform action: @escaping () -> Void, onPressingChanged: ((Bool) -> Void)? = nil) -> some View

```

## Parameters

- **minimumDuration**: The minimum duration of the long press that must elapse before the gesture succeeds.
- **maximumDistance**: The maximum distance that the fingers or cursor performing the long press can move before the gesture fails.
- **action**: The action to perform when a long press is recognized.
- **onPressingChanged**: A closure to run when the pressing state of the gesture changes, passing the current state as a parameter.

## Recognizing long press gestures

- **onLongPressGesture(minimumDuration:perform:onPressingChanged:)**: Adds an action to perform when this view recognizes a long press gesture.
- **onLongTouchGesture(minimumDuration:perform:onTouchingChanged:)**: Adds an action to perform when this view recognizes a remote long touch gesture. A long touch gesture is when the finger is on the remote touch surface without actually pressing.
- **LongPressGesture**: A gesture that succeeds when the user performs a long press.

