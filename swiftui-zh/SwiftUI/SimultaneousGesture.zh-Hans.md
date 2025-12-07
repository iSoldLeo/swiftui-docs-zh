--- 来源：https://developer.apple.com/documentation/SwiftUI/SimultaneousGesture
抓取时间：2025-12-02T16:24:28Z

---

# SimultaneousGesture

**Structure**

一个包含两个手势的手势，这两个手势可以同时执行，互不先后。

## 声明

```swift
@frozen struct SimultaneousGesture<First, Second> where First : Gesture, Second : Gesture
```

## 概述

同步手势是一个容器事件处理程序，它同时执行两个子手势。它的值是一个结构体，包含两个可选值，分别代表两个手势的阶段。

## 创建手势

- **init(_:_:)**：创建一个包含两个手势的手势，这两个手势可以独立地接收更新或执行。

- **first**：两个可同时发生的手势中的第一个。

- **second**：两个可同时发生的手势中的第二个。

## 获取手势的值

- **SimultaneousGesture.Value**：同时发生的手势的值，指示其两个手势中哪一个会接收事件。

## 组合手势

- **组合 SwiftUI 手势**：组合手势以创建复杂的交互。

- **simultaneousGesture(_:including:)**：将一个手势附加到视图，以便与视图定义的其他手势同时处理。

- **simultaneousGesture(_:isEnabled:)**：将一个手势附加到视图，以便与视图定义的其他手势同时处理。

- **simultaneousGesture(_:name:isEnabled:)**：将一个手势附加到视图，以便与视图定义的其他手势同时处理。

- **SequenceGesture**：由两个手势组成的序列手势。

- **ExclusiveGesture**：由两个手势组成，但只能成功完成其中一个的手势。

## 符合

- 手势


---
source: https://developer.apple.com/documentation/SwiftUI/SimultaneousGesture
crawled: 2025-12-02T16:24:28Z
---

# SimultaneousGesture

**Structure**

A gesture containing two gestures that can happen at the same time with neither of them preceding the other.

## Declaration

```swift
@frozen struct SimultaneousGesture<First, Second> where First : Gesture, Second : Gesture
```

## Overview

A simultaneous gesture is a container-event handler that evaluates its two child gestures at the same time. Its value is a struct with two optional values, each representing the phases of one of the two gestures.

## Creating the gesture

- **init(_:_:)**: Creates a gesture with two gestures that can receive updates or succeed independently of each other.
- **first**: The first of two gestures that can happen simultaneously.
- **second**: The second of two gestures that can happen simultaneously.

## Getting the gesture’s values

- **SimultaneousGesture.Value**: The value of a simultaneous gesture that indicates which of its two gestures receives events.

## Combining gestures

- **Composing SwiftUI gestures**: Combine gestures to create complex interactions.
- **simultaneousGesture(_:including:)**: Attaches a gesture to the view to process simultaneously with gestures defined by the view.
- **simultaneousGesture(_:isEnabled:)**: Attaches a gesture to the view to process simultaneously with gestures defined by the view.
- **simultaneousGesture(_:name:isEnabled:)**: Attaches a gesture to the view to process simultaneously with gestures defined by the view.
- **SequenceGesture**: A gesture that’s a sequence of two gestures.
- **ExclusiveGesture**: A gesture that consists of two gestures where only one of them can succeed.

## Conforms To

- Gesture

