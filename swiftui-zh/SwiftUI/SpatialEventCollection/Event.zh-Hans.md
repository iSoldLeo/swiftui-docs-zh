---
来源： https://developer.apple.com/documentation/SwiftUI/SpatialEventCollection/Event
抓取时间： 2025-12-03T06:43:27Z
---

# SpatialEventCollection.Event

**Structure**

由触摸或点击等输入产生的空间事件，可在系统中驱动手势。

## 声明

```swift
struct Event
```

## 概览

您会以[SpatialEventCollection](../SpatialEventCollection.zh-Hans.md) 的形式收到这些事件的集合，该集合是[onChanged(_:)](../Gesture/onChanged.zh-Hans.md) 或[onEnded(_:)](../Gesture/onEnded.zh-Hans.md) 方法的输入。检查单个事件以跟踪交互，从而在应用程序中创建复杂的多点触控体验。

## 识别事件

- **timestamp**：处理事件的时间。
- **id**：在事件生命周期内唯一标识该事件的标识符。
- **SpatialEventCollection.Event.ID**：在事件生命周期内唯一标识事件的值。
- **kind**：事件的输入源。
- **SpatialEventCollection.Event.Kind**：事件可能的输入源或模式。
- **modifierKeys**：事件发生时激活的修改键集。

## 定位事件

- **location**：事件的 2D 位置。
- **location3D**：触摸的 3D 位置。
- **selectionRay**：用于定位触摸的 3D 射线。
- **inputDevicePose**：控制触摸的设备的 3D 位置和方向（如果存在）。
- **SpatialEventCollection.Event.InputDevicePose**：描述输入设备（如控制事件的手）的姿势。
- **targetedEntity**：这次触摸的实体目标（如果存在）。

## 获取事件的当前阶段

- **phase**：事件的阶段。
- **SpatialEventCollection.Event.Phase**：事件可能具有的状态。

### 实例属性

- **chirality**：事件的手性（左或右），适用于相关事件类型。
- **trackingAreaIdentifier**：如果手势附在`CompositorLayer`上，则为事件的追踪区域标识符；如果事件未击中追踪区域或手势未附在`CompositorLayer`上，则为`nil`。

## 访问事件集合

- **subscript(_:)**：使用事件的唯一标识符检索事件。

## 符合

- 等价
- 可散列
- 可识别


---
source: https://developer.apple.com/documentation/SwiftUI/SpatialEventCollection/Event
crawled: 2025-12-03T06:43:27Z
---

# SpatialEventCollection.Event

**Structure**

A spatial event generated from an input like a touch or click that can drive gestures in the system.

## Declaration

```swift
struct Event
```

## Overview

You receive a collection of these events in the form of a [SpatialEventCollection](../SpatialEventCollection.zh-Hans.md) that’s the input to the [onChanged(_:)](../Gesture/onChanged.zh-Hans.md) or [onEnded(_:)](../Gesture/onEnded.zh-Hans.md) method of a [SpatialEventGesture](../SpatialEventGesture.zh-Hans.md). Inspect individual events to track interactions that enable you to create complex, multi-touch experiences in your app.

## Identifying the event

- **timestamp**: The time the event was processed.
- **id**: An identifier that uniquely identifies the event over its lifetime.
- **SpatialEventCollection.Event.ID**: A value that uniquely identifies an event over the course of its lifetime.
- **kind**: The event’s input source.
- **SpatialEventCollection.Event.Kind**: The possible input sources or modes of an event.
- **modifierKeys**: The set of active modifier keys at the time of this event.

## Locating the event

- **location**: The 2D location of the event.
- **location3D**: The 3D location of the touch.
- **selectionRay**: The 3D ray used to target the touch.
- **inputDevicePose**: The 3D position and orientation of the device controlling the touch, if one exists.
- **SpatialEventCollection.Event.InputDevicePose**: A pose describing the input device like a hand controlling the event.
- **targetedEntity**: The entity target for this touch, if one exists.

## Getting the event’s current phase

- **phase**: The phase of the event.
- **SpatialEventCollection.Event.Phase**: The states that an event can have.

## Instance Properties

- **chirality**: The hand chirality (left or right) of this event, for relevant event kinds.
- **trackingAreaIdentifier**: The tracking area identifier of the event, if the gesture is attached to a `CompositorLayer`, or `nil` if the event didn’t hit a tracking area or the gesture isn’t attached to a `CompositorLayer`.

## Accessing the collection’s events

- **subscript(_:)**: Retrieves an event using its unique identifier.

## Conforms To

- Equatable
- Hashable
- Identifiable

