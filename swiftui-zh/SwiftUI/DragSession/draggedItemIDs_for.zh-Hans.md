---
来源：https://developer.apple.com/documentation/SwiftUI/DragSession/draggedItemIDs(for:)
抓取时间： 2025-12-03T06:46:58Z
---

# draggedItemIDs(for:)

**实例方法**

在项目符合`Identifiable` 协议或标识符已单独提供给 SwiftUI 的情况下，提供当前拖动项目的标识符数组。

### 声明

```swift
func draggedItemIDs<ItemID>(for type: ItemID.Type) -> [ItemID] where ItemID : Hashable
```

## 讨论

参数类型：标识符类型。返回值包含拖动项目标识符的数组（如果提供）。如果不存在给定类型的拖动标识符，则返回空数组。


---
source: https://developer.apple.com/documentation/SwiftUI/DragSession/draggedItemIDs(for:)
crawled: 2025-12-03T06:46:58Z
---

# draggedItemIDs(for:)

**Instance Method**

Provides an array of identifiers of the currently dragged items in a case when the items conform to the `Identifiable` protocol, or identifiers were provided to SwiftUI separately.

## Declaration

```swift
func draggedItemIDs<ItemID>(for type: ItemID.Type) -> [ItemID] where ItemID : Hashable
```

## Discussion

Parameter type: The type of the identifiers. Returns: The array with the identifiers of the dragged items if provided. Returns an empty array if no dragged identifiers of a given type exist.

