---
来源： https://developer.apple.com/documentation/SwiftUI/HandActivationBehavior
抓取时间： 2025-12-02T17:41:19Z
---

# 手部激活行为

**Structure**

专用于手驱动输入的激活行为。

## 声明

```swift
struct HandActivationBehavior
```

## 概览

手部激活行为决定了哪些手部输入模式可以激活手势。

## 获取行为

- **automatic**：默认激活行为，包括直接触摸、直接捏合和间接捏合。
- **pinch**：需要用手捏住的激活行为。

## 定义自定义手势

- **highPriorityGesture(_:including:)**：将手势附加到视图，其优先级高于视图定义的手势。
- **highPriorityGesture(_:isEnabled:)**：将手势附加到视图，其优先级高于视图定义的手势。
- **highPriorityGesture(_:name:isEnabled:)**：将手势附加到视图，其优先级高于视图定义的手势。
- **handGestureShortcut(_:isEnabled:)**：为修改后的控件指定手势快捷方式。
- **defersSystemGestures(on:)**：设置您希望手势优先于系统手势的屏幕边缘。
- **Gesture**：一个将事件序列与手势相匹配的实例，并返回每个状态的数值流。
- **AnyGesture**：类型消除的手势。
- **HandGestureShortcut**：手势快捷方式描述了用户为激活按钮或切换键而执行的手指和手腕动作。

## 符合

- 等同


---
source: https://developer.apple.com/documentation/SwiftUI/HandActivationBehavior
crawled: 2025-12-02T17:41:19Z
---

# HandActivationBehavior

**Structure**

An activation behavior specific to hand-driven input.

## Declaration

```swift
struct HandActivationBehavior
```

## Overview

Hand activation behavior determines what hand input modes activate a gesture.

## Getting the behaviors

- **automatic**: The default activation behavior, including direct touch, direct pinch, and indirect pinch.
- **pinch**: Activation that requires a pinched hand.

## Defining custom gestures

- **highPriorityGesture(_:including:)**: Attaches a gesture to the view with a higher precedence than gestures defined by the view.
- **highPriorityGesture(_:isEnabled:)**: Attaches a gesture to the view with a higher precedence than gestures defined by the view.
- **highPriorityGesture(_:name:isEnabled:)**: Attaches a gesture to the view with a higher precedence than gestures defined by the view.
- **handGestureShortcut(_:isEnabled:)**: Assigns a hand gesture shortcut to the modified control.
- **defersSystemGestures(on:)**: Sets the screen edge from which you want your gesture to take precedence over the system gesture.
- **Gesture**: An instance that matches a sequence of events to a gesture, and returns a stream of values for each of its states.
- **AnyGesture**: A type-erased gesture.
- **HandGestureShortcut**: Hand gesture shortcuts describe finger and wrist movements that the user can perform in order to activate a button or toggle.

## Conforms To

- Equatable

