--- 来源：https://developer.apple.com/documentation/SwiftUI/AnyGesture
抓取时间：2025-12-02T17:41:18Z

---

# AnyGesture

**Structure**

一个擦除文字的手势。

## 声明

```swift
@frozen struct AnyGesture<Value>
```

## 实现自定义手势

- **init(_:)**：从另一个手势创建实例。

## 定义自定义手势

- **highPriorityGesture(_:including:)**：将一个手势附加到视图，其优先级高于视图定义的手势。

- **highPriorityGesture(_:isEnabled:)**：将一个手势附加到视图，其优先级高于视图定义的手势。

- **highPriorityGesture(_:name:isEnabled:)**：将手势附加到视图，使其优先级高于视图定义的手势。

- **handGestureShortcut(_:isEnabled:)**：为修改后的控件分配手势快捷键。

- **defersSystemGestures(on:)**：设置手势优先于系统手势的屏幕边缘。

- **Gesture**：将事件序列与手势匹配，并返回其每个状态的值流的实例。

- **HandActivationBehavior**：特定于手部输入的激活行为。

- **HandGestureShortcut**：手势快捷键描述用户可用于激活按钮或切换开关的手指和手腕动作。

## 符合

- 手势


---
source: https://developer.apple.com/documentation/SwiftUI/AnyGesture
crawled: 2025-12-02T17:41:18Z
---

# AnyGesture

**Structure**

A type-erased gesture.

## Declaration

```swift
@frozen struct AnyGesture<Value>
```

## Implementing a custom gesture

- **init(_:)**: Creates an instance from another gesture.

## Defining custom gestures

- **highPriorityGesture(_:including:)**: Attaches a gesture to the view with a higher precedence than gestures defined by the view.
- **highPriorityGesture(_:isEnabled:)**: Attaches a gesture to the view with a higher precedence than gestures defined by the view.
- **highPriorityGesture(_:name:isEnabled:)**: Attaches a gesture to the view with a higher precedence than gestures defined by the view.
- **handGestureShortcut(_:isEnabled:)**: Assigns a hand gesture shortcut to the modified control.
- **defersSystemGestures(on:)**: Sets the screen edge from which you want your gesture to take precedence over the system gesture.
- **Gesture**: An instance that matches a sequence of events to a gesture, and returns a stream of values for each of its states.
- **HandActivationBehavior**: An activation behavior specific to hand-driven input.
- **HandGestureShortcut**: Hand gesture shortcuts describe finger and wrist movements that the user can perform in order to activate a button or toggle.

## Conforms To

- Gesture

