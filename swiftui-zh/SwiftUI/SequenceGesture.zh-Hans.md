--- 来源：https://developer.apple.com/documentation/SwiftUI/SequenceGesture
抓取时间：2025-12-02T17:41:13Z

---

# SequenceGesture

**Structure**

一个由两个手势组成的序列手势。

## 声明

```swift
@frozen struct SequenceGesture<First, Second> where First : Gesture, Second : Gesture
```

## 概述

阅读 [Composing-SwiftUI-Gestures](Composing-SwiftUI-Gestures.zh-Hans.md) 了解如何创建由两个手势组成的序列手势。

## 创建手势

- **init(_:_:)**：创建一个包含两个手势的序列手势。

- **first**：序列手势中的第一个手势。

- **second**：序列手势中的第二个手势。

## 获取手势的值

- **SequenceGesture.Value**：序列手势的值，用于检测第一个手势是否成功，以便启动第二个手势。

## 组合手势

- **组合 SwiftUI 手势**：组合手势以创建复杂的交互。

- **simultaneousGesture(_:including:)**：将手势附加到视图，以便与视图定义的其他手势同时处理。

- **simultaneousGesture(_:isEnabled:)**：将手势附加到视图，以便与视图定义的其他手势同时处理。

- **simultaneousGesture(_:name:isEnabled:)**：将手势附加到视图，以便与视图定义的其他手势同时处理。

- **SimultaneousGesture**：包含两个手势的手势，这两个手势可以同时发生，互不先后。

- **ExclusiveGesture**：一种由两个手势组成的动作，其中只有一个动作能够成功。

## 符合

- 手势


---
source: https://developer.apple.com/documentation/SwiftUI/SequenceGesture
crawled: 2025-12-02T17:41:13Z
---

# SequenceGesture

**Structure**

A gesture that’s a sequence of two gestures.

## Declaration

```swift
@frozen struct SequenceGesture<First, Second> where First : Gesture, Second : Gesture
```

## Overview

Read [Composing-SwiftUI-Gestures](Composing-SwiftUI-Gestures.zh-Hans.md) to learn how you can create a sequence of two gestures.

## Creating the gesture

- **init(_:_:)**: Creates a sequence gesture with two gestures.
- **first**: The first gesture in a sequence of two gestures.
- **second**: The second gesture in a sequence of two gestures.

## Getting the gesture’s values

- **SequenceGesture.Value**: The value of a sequence gesture that helps to detect whether the first gesture succeeded, so the second gesture can start.

## Combining gestures

- **Composing SwiftUI gestures**: Combine gestures to create complex interactions.
- **simultaneousGesture(_:including:)**: Attaches a gesture to the view to process simultaneously with gestures defined by the view.
- **simultaneousGesture(_:isEnabled:)**: Attaches a gesture to the view to process simultaneously with gestures defined by the view.
- **simultaneousGesture(_:name:isEnabled:)**: Attaches a gesture to the view to process simultaneously with gestures defined by the view.
- **SimultaneousGesture**: A gesture containing two gestures that can happen at the same time with neither of them preceding the other.
- **ExclusiveGesture**: A gesture that consists of two gestures where only one of them can succeed.

## Conforms To

- Gesture

