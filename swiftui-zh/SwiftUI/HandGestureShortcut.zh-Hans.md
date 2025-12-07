---
来源： https://developer.apple.com/documentation/SwiftUI/HandGestureShortcut
抓取时间： 2025-12-02T17:41:19Z
---

# 手势快捷键

**Structure**

手势快捷方式描述了用户为激活按钮或切换键而执行的手指和手腕动作。

## 声明

```swift
struct HandGestureShortcut
```

## 类型属性

- **primaryAction**：主要操作的手势快捷方式。

## 定义自定义手势

- **highPriorityGesture(_:including:)**：将手势附加到视图，其优先级高于视图定义的手势。
- **highPriorityGesture(_:isEnabled:)**：将手势附加到视图，其优先级高于视图定义的手势。
- **highPriorityGesture(_:name:isEnabled:)**：将手势附加到视图，其优先级高于视图定义的手势。
- **handGestureShortcut(_:isEnabled:)**：为修改后的控件指定手势快捷方式。
- **defersSystemGestures(on:)**：设置您希望手势优先于系统手势的屏幕边缘。
- **Gesture**：一个将事件序列与手势相匹配的实例，并返回每个状态的数值流。
- **AnyGesture**：类型消除的手势。
- **HandActivationBehavior**：手驱动输入特有的激活行为。

## 符合

- 等价
- 可发送
- 可发送元数据类型


---
source: https://developer.apple.com/documentation/SwiftUI/HandGestureShortcut
crawled: 2025-12-02T17:41:19Z
---

# HandGestureShortcut

**Structure**

Hand gesture shortcuts describe finger and wrist movements that the user can perform in order to activate a button or toggle.

## Declaration

```swift
struct HandGestureShortcut
```

## Type Properties

- **primaryAction**: The hand gesture shortcut for the primary action.

## Defining custom gestures

- **highPriorityGesture(_:including:)**: Attaches a gesture to the view with a higher precedence than gestures defined by the view.
- **highPriorityGesture(_:isEnabled:)**: Attaches a gesture to the view with a higher precedence than gestures defined by the view.
- **highPriorityGesture(_:name:isEnabled:)**: Attaches a gesture to the view with a higher precedence than gestures defined by the view.
- **handGestureShortcut(_:isEnabled:)**: Assigns a hand gesture shortcut to the modified control.
- **defersSystemGestures(on:)**: Sets the screen edge from which you want your gesture to take precedence over the system gesture.
- **Gesture**: An instance that matches a sequence of events to a gesture, and returns a stream of values for each of its states.
- **AnyGesture**: A type-erased gesture.
- **HandActivationBehavior**: An activation behavior specific to hand-driven input.

## Conforms To

- Equatable
- Sendable
- SendableMetatype

