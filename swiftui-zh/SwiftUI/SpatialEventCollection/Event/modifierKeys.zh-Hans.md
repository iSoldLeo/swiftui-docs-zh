---
来源： https://developer.apple.com/documentation/SwiftUI/SpatialEventCollection/Event/modifierKeys
抓取时间： 2025-12-04T13:37:47Z
---

# 修饰符键

**实例属性**

事件发生时激活的修改器键集。

## 声明

```swift
var modifierKeys: EventModifiers
```

## 识别事件

- **timestamp**：事件被处理的时间。
- **id**：唯一标识事件整个生命周期的标识符。
- **SpatialEventCollection.Event.ID**：在事件生命周期内唯一标识事件的值。
- **kind**：事件的输入源。
- **SpatialEventCollection.Event.Kind**：事件可能的输入源或模式。


---
source: https://developer.apple.com/documentation/SwiftUI/SpatialEventCollection/Event/modifierKeys
crawled: 2025-12-04T13:37:47Z
---

# modifierKeys

**Instance Property**

The set of active modifier keys at the time of this event.

## Declaration

```swift
var modifierKeys: EventModifiers
```

## Identifying the event

- **timestamp**: The time the event was processed.
- **id**: An identifier that uniquely identifies the event over its lifetime.
- **SpatialEventCollection.Event.ID**: A value that uniquely identifies an event over the course of its lifetime.
- **kind**: The event’s input source.
- **SpatialEventCollection.Event.Kind**: The possible input sources or modes of an event.

