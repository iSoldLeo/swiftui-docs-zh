---
来源： https://developer.apple.com/documentation/SwiftUI/SpatialEventCollection
抓取时间： 2025-12-02T17:40:57Z
---

# 空间事件集合

**Structure**

针对特定视图的空间输入事件集合。

## 声明

```swift
struct SpatialEventCollection
```

## 概览

作为[onChanged(_:)](Gesture/onChanged.zh-Hans.md) 或[onEnded(_:)](Gesture/onEnded.zh-Hans.md) 方法的输入，您将收到一个此类型的结构体。该结构包含一个[Event](SpatialEventCollection/Event.zh-Hans.md) 值集合，这些值与正在发生的输入事件相对应。您可以通过[id-swift.property](SpatialEventCollection/Event/id-swift_property.zh-Hans.md) 值查找集合中的特定事件，也可以遍历集合中的所有事件，根据事件的状态应用逻辑。

## 访问事件集合

- **SpatialEventCollection.Event**：由触摸或点击等输入产生的空间事件，可在系统中驱动手势。
- **subscript(_:)**：使用事件的唯一标识符检索事件。

## 遍历集合中的事件

- **makeIterator()**：对集合中的所有事件进行迭代。
- **SpatialEventCollection.Iterator**：对集合中的所有事件进行迭代。

## 识别空间事件

- **SpatialEventGesture**：一种手势，可提供有关正在发生的空间事件（如点击和触摸）的信息。
- **Chirality**：姿势的手性或手掌性。

## 符合

- 收集
- 可复制
- 等价
- 序列


---
source: https://developer.apple.com/documentation/SwiftUI/SpatialEventCollection
crawled: 2025-12-02T17:40:57Z
---

# SpatialEventCollection

**Structure**

A collection of spatial input events that target a specific view.

## Declaration

```swift
struct SpatialEventCollection
```

## Overview

You receive a structure of this type as an input to the [onChanged(_:)](Gesture/onChanged.zh-Hans.md) or [onEnded(_:)](Gesture/onEnded.zh-Hans.md) method of a [SpatialEventGesture](SpatialEventGesture.zh-Hans.md). The structure contains a collection of [Event](SpatialEventCollection/Event.zh-Hans.md) values that correspond to ongoing input events. You can look up a specific event in the collection by its [id-swift.property](SpatialEventCollection/Event/id-swift_property.zh-Hans.md) value or iterate over all events in the collection to apply logic depending on the event’s state.

## Accessing the collection’s events

- **SpatialEventCollection.Event**: A spatial event generated from an input like a touch or click that can drive gestures in the system.
- **subscript(_:)**: Retrieves an event using its unique identifier.

## Iterating over events in the collection

- **makeIterator()**: Makes an iterator over all events in the collection.
- **SpatialEventCollection.Iterator**: An iterator over all events in the collection.

## Recognizing spatial events

- **SpatialEventGesture**: A gesture that provides information about ongoing spatial events like clicks and touches.
- **Chirality**: The chirality, or handedness, of a pose.

## Conforms To

- Collection
- Copyable
- Equatable
- Sequence

