---
来源： https://developer.apple.com/documentation/SwiftUI/SpatialEventCollection/Event/ID-swift.struct
抓取时间： 2025-12-04T13:37:44Z
---

# SpatialEventCollection.Event.ID

**Structure**

在事件生命周期内唯一标识该事件的值。

## 声明

```swift
struct ID
```

## 识别事件

- **timestamp**：事件被处理的时间。
- **id**：唯一标识事件整个生命周期的标识符。
- **kind**：事件的输入源。
- **SpatialEventCollection.Event.Kind**：事件可能的输入源或模式。
- **modifierKeys**：事件发生时激活的修改键集。

## 符合

- 等价
- 可散列


---
source: https://developer.apple.com/documentation/SwiftUI/SpatialEventCollection/Event/ID-swift.struct
crawled: 2025-12-04T13:37:44Z
---

# SpatialEventCollection.Event.ID

**Structure**

A value that uniquely identifies an event over the course of its lifetime.

## Declaration

```swift
struct ID
```

## Identifying the event

- **timestamp**: The time the event was processed.
- **id**: An identifier that uniquely identifies the event over its lifetime.
- **kind**: The event’s input source.
- **SpatialEventCollection.Event.Kind**: The possible input sources or modes of an event.
- **modifierKeys**: The set of active modifier keys at the time of this event.

## Conforms To

- Equatable
- Hashable

