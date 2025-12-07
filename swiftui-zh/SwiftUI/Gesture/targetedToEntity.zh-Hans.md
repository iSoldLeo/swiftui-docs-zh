--- 来源：https://developer.apple.com/documentation/SwiftUI/Gesture/targetedToEntity(_:)

抓取时间：2025-12-01T02:38:50Z

---

# targetedToEntity(_:)

**实例方法**

要求此手势指向一个实体或其子实体。

## 声明

```swift
@MainActor @preconcurrency func targetedToEntity(_ entity: Entity) -> some Gesture<EntityTargetValue<Self.Value>>

```

## 参数

- **entity**：手势指向的实体。

## 返回值

一个包含原始手势值和目标实体的 `RealityCoordinateSpaceConverting` 值。

## 将手势与 RealityKit 实体一起使用

- **targetedToAnyEntity()**：要求此手势指向一个实体。

- **targetedToEntity(where:)**：此手势需要指向查询结果中可找到的实体。


---
source: https://developer.apple.com/documentation/SwiftUI/Gesture/targetedToEntity(_:)
crawled: 2025-12-01T02:38:50Z
---

# targetedToEntity(_:)

**Instance Method**

Requires this gesture to target an entity or a descendant of entity.

## Declaration

```swift
@MainActor @preconcurrency func targetedToEntity(_ entity: Entity) -> some Gesture<EntityTargetValue<Self.Value>>

```

## Parameters

- **entity**: The entity the gesture targets.

## Return Value

A `RealityCoordinateSpaceConverting` value containing the original gesture value along with the targeted entity.

## Using a gesture with a RealityKit entity

- **targetedToAnyEntity()**: Requires this gesture to target an entity.
- **targetedToEntity(where:)**: Requires this gesture to target an entity that can be found in the results of the query.

