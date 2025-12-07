--- 来源：https://developer.apple.com/documentation/SwiftUI/View/handGestureShortcut(_:isEnabled:)

抓取时间：2025-12-02T17:23:54Z

---

# handGestureShortcut(_:isEnabled:)

**实例方法**

为修改后的控件分配手势快捷键。

## 声明

```swift
nonisolated func handGestureShortcut(_ shortcut: HandGestureShortcut, isEnabled: Bool = true) -> some View

```

## 参数

- **shortcut**：要与此控件关联的快捷键。

- **isEnabled**：一个布尔值，指示是否为此控件启用了快捷键。

## 说明

当控件位于最前端场景的任何位置时，执行控件的快捷键等效于直接与控件交互以执行其主要操作。

以下示例允许 watchOS 音乐应用的用户通过拇指和食指同时双击来切换播放：

```swift
struct PlaybackControls: View {
    let model: TrackModel

    var body: some View {
        HStack {
            Button("Skip Back") {
                model.skipBack()
            }

            Button("Play/Pause") {
                model.playPause()
            }
            .handGestureShortcut(.primaryAction)

            Button("Skip Forward") {
                model.skipForward()
            }
        }
    }
}
```

手势快捷方式的目标位置是通过遍历当前场景的首尾顺序来确定的。

## 定义自定义手势

- **highPriorityGesture(_:including:)**：将手势附加到视图，使其优先级高于视图定义的手势。

- **highPriorityGesture(_:isEnabled:)**：将手势附加到视图，使其优先级高于视图定义的手势。

- **highPriorityGesture(_:name:isEnabled:)**：将手势附加到视图，使其优先级高于视图定义的手势。

- **defersSystemGestures(on:)**：设置手势优先于系统手势的屏幕边缘。

- **Gesture**：将事件序列与手势匹配，并返回其每个状态的值流的实例。

- **AnyGesture**：擦除输入的手势。

- **HandActivationBehavior**：特定于手部输入的激活行为。

- **HandGestureShortcut**：手势快捷方式描述用户可以通过手指和手腕的动作来激活按钮或切换开关。


---
source: https://developer.apple.com/documentation/SwiftUI/View/handGestureShortcut(_:isEnabled:)
crawled: 2025-12-02T17:23:54Z
---

# handGestureShortcut(_:isEnabled:)

**Instance Method**

Assigns a hand gesture shortcut to the modified control.

## Declaration

```swift
nonisolated func handGestureShortcut(_ shortcut: HandGestureShortcut, isEnabled: Bool = true) -> some View

```

## Parameters

- **shortcut**: The shortcut to associate with this control.
- **isEnabled**: A Boolean value that indicates whether the shortcut is is enabled for this control.

## Discussion

Performing the control’s shortcut while the control is anywhere in the frontmost scene is equivalent to direct interaction with the control to perform its primary action.

The following example lets users of a watchOS music app toggle playback by double-tapping their thumb and index finger together:

```swift
struct PlaybackControls: View {
    let model: TrackModel

    var body: some View {
        HStack {
            Button("Skip Back") {
                model.skipBack()
            }

            Button("Play/Pause") {
                model.playPause()
            }
            .handGestureShortcut(.primaryAction)

            Button("Skip Forward") {
                model.skipForward()
            }
        }
    }
}
```

The target of a hand gesture shortcut is resolved in a leading-to-trailing traversal of the active scene.

## Defining custom gestures

- **highPriorityGesture(_:including:)**: Attaches a gesture to the view with a higher precedence than gestures defined by the view.
- **highPriorityGesture(_:isEnabled:)**: Attaches a gesture to the view with a higher precedence than gestures defined by the view.
- **highPriorityGesture(_:name:isEnabled:)**: Attaches a gesture to the view with a higher precedence than gestures defined by the view.
- **defersSystemGestures(on:)**: Sets the screen edge from which you want your gesture to take precedence over the system gesture.
- **Gesture**: An instance that matches a sequence of events to a gesture, and returns a stream of values for each of its states.
- **AnyGesture**: A type-erased gesture.
- **HandActivationBehavior**: An activation behavior specific to hand-driven input.
- **HandGestureShortcut**: Hand gesture shortcuts describe finger and wrist movements that the user can perform in order to activate a button or toggle.

