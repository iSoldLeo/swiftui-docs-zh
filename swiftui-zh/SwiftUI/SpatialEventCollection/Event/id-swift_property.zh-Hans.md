---
来源： https://developer.apple.com/documentation/SwiftUI/SpatialEventCollection/Event/id-swift.property
抓取时间： 2025-12-04T13:37:43Z
---

# id

**实例属性**

唯一标识事件生命周期的标识符。

## 声明

```swift
var id: SpatialEventCollection.Event.ID
```

## 识别事件

- **timestamp**：事件被处理的时间。
- **SpatialEventCollection.Event.ID**：在事件生命周期内唯一标识事件的值。
- **kind**：事件的输入源。
- **SpatialEventCollection.Event.Kind**：事件可能的输入源或模式。
- **modifierKeys**：事件发生时激活的修改键集。


---
source: https://developer.apple.com/documentation/SwiftUI/SpatialEventCollection/Event/id-swift.property
crawled: 2025-12-04T13:37:43Z
---

# id

**Instance Property**

An identifier that uniquely identifies the event over its lifetime.

## Declaration

```swift
var id: SpatialEventCollection.Event.ID
```

## Identifying the event

- **timestamp**: The time the event was processed.
- **SpatialEventCollection.Event.ID**: A value that uniquely identifies an event over the course of its lifetime.
- **kind**: The event’s input source.
- **SpatialEventCollection.Event.Kind**: The possible input sources or modes of an event.
- **modifierKeys**: The set of active modifier keys at the time of this event.

