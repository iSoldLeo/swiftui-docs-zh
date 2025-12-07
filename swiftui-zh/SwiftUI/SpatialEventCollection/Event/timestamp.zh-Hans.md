---
来源： https://developer.apple.com/documentation/SwiftUI/SpatialEventCollection/Event/timestamp
抓取时间： 2025-12-04T13:37:42Z
---

# 时间戳

**实例属性**

事件被处理的时间。

## 声明

```swift
var timestamp: TimeInterval
```

## 识别事件

- **id**：唯一标识事件整个生命周期的标识符。
- **SpatialEventCollection.Event.ID**：在事件生命周期内唯一标识事件的值。
- **kind**：事件的输入源。
- **SpatialEventCollection.Event.Kind**：事件可能的输入源或模式。
- **modifierKeys**：事件发生时激活的修改键集。


---
source: https://developer.apple.com/documentation/SwiftUI/SpatialEventCollection/Event/timestamp
crawled: 2025-12-04T13:37:42Z
---

# timestamp

**Instance Property**

The time the event was processed.

## Declaration

```swift
var timestamp: TimeInterval
```

## Identifying the event

- **id**: An identifier that uniquely identifies the event over its lifetime.
- **SpatialEventCollection.Event.ID**: A value that uniquely identifies an event over the course of its lifetime.
- **kind**: The event’s input source.
- **SpatialEventCollection.Event.Kind**: The possible input sources or modes of an event.
- **modifierKeys**: The set of active modifier keys at the time of this event.

