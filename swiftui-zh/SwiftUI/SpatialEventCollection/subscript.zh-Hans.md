---
来源： https://developer.apple.com/documentation/SwiftUI/SpatialEventCollection/subscript(_:)
抓取时间： 2025-12-01T11:32:45Z
---

# 下标(_:)

**实例下标**

使用事件的唯一标识符检索事件。

## 声明

```swift
subscript(index: SpatialEventCollection.Event.ID) -> SpatialEventCollection.Event? { get }
```

## 概览

如果`Event` 已不存在于集合中，则返回 `nil`。

## 访问集合事件

- **SpatialEventCollection.Event**：由触摸或点击等输入产生的空间事件，可在系统中驱动手势。


---
source: https://developer.apple.com/documentation/SwiftUI/SpatialEventCollection/subscript(_:)
crawled: 2025-12-01T11:32:45Z
---

# subscript(_:)

**Instance Subscript**

Retrieves an event using its unique identifier.

## Declaration

```swift
subscript(index: SpatialEventCollection.Event.ID) -> SpatialEventCollection.Event? { get }
```

## Overview

Returns `nil` if the `Event` no longer exists in the collection.

## Accessing the collection’s events

- **SpatialEventCollection.Event**: A spatial event generated from an input like a touch or click that can drive gestures in the system.

