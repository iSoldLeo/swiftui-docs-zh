--- 来源：https://developer.apple.com/documentation/SwiftUI/Gesture/targetedToAnyEntity()

抓取时间：2025-11-30T20:08:23Z

---

# targetedToAnyEntity()

**实例方法**

此手势用于指定目标实体。

## 声明

```swift
@MainActor @preconcurrency func targetedToAnyEntity() -> some Gesture<EntityTargetValue<Self.Value>>

```

## 返回值

一个包含原始手势值和目标实体的 `RealityCoordinateSpaceConvertible` 值。

## 将手势与 RealityKit 实体一起使用

- **targetedToEntity(_:)**：此手势用于指定目标实体或其子实体。

- **targetedToEntity(where:)**：此手势用于指定可在查询结果中找到的实体。


---
source: https://developer.apple.com/documentation/SwiftUI/Gesture/targetedToAnyEntity()
crawled: 2025-11-30T20:08:23Z
---

# targetedToAnyEntity()

**Instance Method**

Requires this gesture to target an entity.

## Declaration

```swift
@MainActor @preconcurrency func targetedToAnyEntity() -> some Gesture<EntityTargetValue<Self.Value>>

```

## Return Value

A `RealityCoordinateSpaceConvertible`value containing the original gesture value along with the targeted entity.

## Using a gesture with a RealityKit entity

- **targetedToEntity(_:)**: Requires this gesture to target an entity or a descendant of entity.
- **targetedToEntity(where:)**: Requires this gesture to target an entity that can be found in the results of the query.

