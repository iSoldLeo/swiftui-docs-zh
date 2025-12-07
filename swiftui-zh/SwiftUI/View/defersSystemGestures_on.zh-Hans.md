--- 来源：https://developer.apple.com/documentation/SwiftUI/View/defersSystemGestures(on:)

抓取时间：2025-11-30T21:26:23Z

---

# defersSystemGestures(on:)

**实例方法**

设置屏幕边缘，使你的手势优先于系统手势。

## 声明

```swift
nonisolated func defersSystemGestures(on edges: Edge.Set) -> some View

```

## 参数

- **edges**：一个值，指示你的手势优先于系统手势的屏幕边缘。

## 说明

以下代码会延迟给定画布的垂直屏幕边缘的系统手势。

```swift
struct DeferredView: View {
    var body: some View {
        Canvas()
            .defersSystemGestures(on: .vertical)
    }
}
```

## 定义自定义手势

- **highPriorityGesture(_:including:)**：将一个手势附加到视图，其优先级高于视图自身定义的手势。

- **highPriorityGesture(_:isEnabled:)**：将一个手势附加到视图，其优先级高于视图自身定义的手势。

- **highPriorityGesture(_:name:isEnabled:)**：将一个手势附加到视图，其优先级高于视图自身定义的手势。

- **handGestureShortcut(_:isEnabled:)**：为修改后的控件分配一个手势快捷键。

- **Gesture**：一个将事件序列与手势匹配的实例，并返回每个状态的值流。

- **AnyGesture**：一个擦除文本的手势。

- **HandActivationBehavior**：一种专门用于手部输入的激活行为。

- **HandGestureShortcut**：手势快捷键描述了用户可以通过手指和手腕的动作来激活按钮或切换开关。


---
source: https://developer.apple.com/documentation/SwiftUI/View/defersSystemGestures(on:)
crawled: 2025-11-30T21:26:23Z
---

# defersSystemGestures(on:)

**Instance Method**

Sets the screen edge from which you want your gesture to take precedence over the system gesture.

## Declaration

```swift
nonisolated func defersSystemGestures(on edges: Edge.Set) -> some View

```

## Parameters

- **edges**: A value that indicates the screen edge from which you want your gesture to take precedence over the system gesture.

## Discussion

The following code defers the vertical screen edges system gestures of a given canvas.

```swift
struct DeferredView: View {
    var body: some View {
        Canvas()
            .defersSystemGestures(on: .vertical)
    }
}
```

## Defining custom gestures

- **highPriorityGesture(_:including:)**: Attaches a gesture to the view with a higher precedence than gestures defined by the view.
- **highPriorityGesture(_:isEnabled:)**: Attaches a gesture to the view with a higher precedence than gestures defined by the view.
- **highPriorityGesture(_:name:isEnabled:)**: Attaches a gesture to the view with a higher precedence than gestures defined by the view.
- **handGestureShortcut(_:isEnabled:)**: Assigns a hand gesture shortcut to the modified control.
- **Gesture**: An instance that matches a sequence of events to a gesture, and returns a stream of values for each of its states.
- **AnyGesture**: A type-erased gesture.
- **HandActivationBehavior**: An activation behavior specific to hand-driven input.
- **HandGestureShortcut**: Hand gesture shortcuts describe finger and wrist movements that the user can perform in order to activate a button or toggle.

