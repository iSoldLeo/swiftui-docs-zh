---
来源： https://developer.apple.com/documentation/SwiftUI/SpatialEventCollection/Event/kind-swift.property
抓取时间： 2025-12-04T13:37:45Z
---

# 种类

**实例属性**

事件的输入源。

## 声明

```swift
var kind: SpatialEventCollection.Event.Kind
```

## 识别事件

- **timestamp**：事件被处理的时间。
- **id**：唯一标识事件整个生命周期的标识符。
- **SpatialEventCollection.Event.ID**：在事件生命周期内唯一标识事件的值。
- **SpatialEventCollection.Event.Kind**：事件的可能输入源或模式。
- **modifierKeys**：事件发生时激活的修改键集。


---
source: https://developer.apple.com/documentation/SwiftUI/SpatialEventCollection/Event/kind-swift.property
crawled: 2025-12-04T13:37:45Z
---

# kind

**Instance Property**

The event’s input source.

## Declaration

```swift
var kind: SpatialEventCollection.Event.Kind
```

## Identifying the event

- **timestamp**: The time the event was processed.
- **id**: An identifier that uniquely identifies the event over its lifetime.
- **SpatialEventCollection.Event.ID**: A value that uniquely identifies an event over the course of its lifetime.
- **SpatialEventCollection.Event.Kind**: The possible input sources or modes of an event.
- **modifierKeys**: The set of active modifier keys at the time of this event.

