--- 来源：https://developer.apple.com/documentation/SwiftUI/Gesture/targetedToEntity(where:)

抓取时间：2025-12-01T02:38:50Z

---

# targetedToEntity(where:)

**实例方法**

要求此手势指向查询结果中存在的实体。

## 声明

```swift
@MainActor @preconcurrency func targetedToEntity(where query: QueryPredicate<Entity>) -> some Gesture<EntityTargetValue<Self.Value>>

```

## 参数

- **query**：用于筛选手势指向的实体的查询。

## 返回值

`RealityCoordinateSpaceConverting` 包含原始手势值以及目标实体的值。

## 将手势与 RealityKit 实体一起使用

- **targetedToAnyEntity()**：要求此手势指向一个实体。

- **targetedToEntity(_:)**：此手势需要指定一个实体或其子实体。


---
source: https://developer.apple.com/documentation/SwiftUI/Gesture/targetedToEntity(where:)
crawled: 2025-12-01T02:38:50Z
---

# targetedToEntity(where:)

**Instance Method**

Requires this gesture to target an entity that can be found in the results of the query.

## Declaration

```swift
@MainActor @preconcurrency func targetedToEntity(where query: QueryPredicate<Entity>) -> some Gesture<EntityTargetValue<Self.Value>>

```

## Parameters

- **query**: A query to filter which entity the gesture targets.

## Return Value

A `RealityCoordinateSpaceConverting` value containing the original gesture value along with the targeted entity.

## Using a gesture with a RealityKit entity

- **targetedToAnyEntity()**: Requires this gesture to target an entity.
- **targetedToEntity(_:)**: Requires this gesture to target an entity or a descendant of entity.

