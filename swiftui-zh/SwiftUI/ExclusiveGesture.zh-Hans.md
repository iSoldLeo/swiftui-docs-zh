--- 来源：https://developer.apple.com/documentation/SwiftUI/ExclusiveGesture
抓取时间：2025-12-02T17:41:14Z

---

# ExclusiveGesture

**Structure**

一种由两个手势组成的手势，其中只有一个手势会成功执行。

## 声明

```swift
@frozen struct ExclusiveGesture<First, Second> where First : Gesture, Second : Gesture
```

## 概述

`ExclusiveGesture` 赋予其第一个手势优先权。

## 创建手势

- **init(_:_:)**：由两个手势组成，其中只有一个手势会成功执行。

- **first**：两个手势中的第一个。

- **second**：两个手势中的第二个。

## 支持的类型

- **ExclusiveGesture.Value**：互斥手势的值，指示两个手势中哪个成功执行。

## 组合手势

- **组合 SwiftUI 手势**：组合手势以创建复杂的交互。

- **simultaneousGesture(_:including:)**：将手势附加到视图，以便与视图定义的其他手势同时处理。

- **simultaneousGesture(_:isEnabled:)**：将手势附加到视图，以便与视图定义的其他手势同时处理。

- **simultaneousGesture(_:name:isEnabled:)**：将手势附加到视图，以便与视图定义的其他手势同时处理。

- **SequenceGesture**：由两个手势组成的序列手势。

- **SimultaneousGesture**：包含两个可以同时执行且互不先后的手势。

## 符合

- 手势


---
source: https://developer.apple.com/documentation/SwiftUI/ExclusiveGesture
crawled: 2025-12-02T17:41:14Z
---

# ExclusiveGesture

**Structure**

A gesture that consists of two gestures where only one of them can succeed.

## Declaration

```swift
@frozen struct ExclusiveGesture<First, Second> where First : Gesture, Second : Gesture
```

## Overview

The `ExclusiveGesture` gives precedence to its first gesture.

## Creating the gesture

- **init(_:_:)**: Creates a gesture from two gestures where only one of them succeeds.
- **first**: The first of two gestures.
- **second**: The second of two gestures.

## Supporting types

- **ExclusiveGesture.Value**: The value of an exclusive gesture that indicates which of two gestures succeeded.

## Combining gestures

- **Composing SwiftUI gestures**: Combine gestures to create complex interactions.
- **simultaneousGesture(_:including:)**: Attaches a gesture to the view to process simultaneously with gestures defined by the view.
- **simultaneousGesture(_:isEnabled:)**: Attaches a gesture to the view to process simultaneously with gestures defined by the view.
- **simultaneousGesture(_:name:isEnabled:)**: Attaches a gesture to the view to process simultaneously with gestures defined by the view.
- **SequenceGesture**: A gesture that’s a sequence of two gestures.
- **SimultaneousGesture**: A gesture containing two gestures that can happen at the same time with neither of them preceding the other.

## Conforms To

- Gesture

