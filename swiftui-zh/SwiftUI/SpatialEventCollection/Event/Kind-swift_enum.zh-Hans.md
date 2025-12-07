---
来源： https://developer.apple.com/documentation/SwiftUI/SpatialEventCollection/Event/Kind-swift.enum
抓取时间： 2025-12-04T13:37:46Z
---

# SpatialEventCollection.Event.Kind

**Enumeration**

事件可能的输入源或模式。

## 声明

```swift
enum Kind
```

## 获取事件类型

- **SpatialEventCollection.Event.Kind.directPinch**：手在靠近内容时捏住产生的事件。
- **SpatialEventCollection.Event.Kind.indirectPinch**：间接目标捏手产生的事件。
- **SpatialEventCollection.Event.Kind.pointer**：代表基于点击的间接输入设备的事件，描述从点击到点击释放的输入序列。
- **SpatialEventCollection.Event.Kind.touch**：由直接针对内容的触摸产生的事件。

## 枚举案例

- **SpatialEventCollection.Event.Kind.pencil**：铅笔与内容接触产生的事件。

## 识别事件

- **timestamp**：事件被处理的时间。
- **id**：唯一标识事件整个生命周期的标识符。
- **SpatialEventCollection.Event.ID**：在事件生命周期内唯一标识事件的值。
- **kind**：事件的输入源。
- **modifierKeys**：事件的输入源：事件发生时的活动修改键集。

## 符合

- 等价
- 可散列


---
source: https://developer.apple.com/documentation/SwiftUI/SpatialEventCollection/Event/Kind-swift.enum
crawled: 2025-12-04T13:37:46Z
---

# SpatialEventCollection.Event.Kind

**Enumeration**

The possible input sources or modes of an event.

## Declaration

```swift
enum Kind
```

## Getting the event type

- **SpatialEventCollection.Event.Kind.directPinch**: An event generated from a pinching hand in close proximity to content.
- **SpatialEventCollection.Event.Kind.indirectPinch**: An event generated from an indirectly targeted pinching hand.
- **SpatialEventCollection.Event.Kind.pointer**: An event representing a click-based, indirect input device describing the input sequence from click to click release.
- **SpatialEventCollection.Event.Kind.touch**: An event generated from a touch directly targeting content.

## Enumeration Cases

- **SpatialEventCollection.Event.Kind.pencil**: An event generated from a pencil making contact with content.

## Identifying the event

- **timestamp**: The time the event was processed.
- **id**: An identifier that uniquely identifies the event over its lifetime.
- **SpatialEventCollection.Event.ID**: A value that uniquely identifies an event over the course of its lifetime.
- **kind**: The event’s input source.
- **modifierKeys**: The set of active modifier keys at the time of this event.

## Conforms To

- Equatable
- Hashable

