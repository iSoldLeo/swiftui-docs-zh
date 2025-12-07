---
来源：https://developer.apple.com/documentation/SwiftUI/DropSession/LocalSession-swift.struct/draggedItemIDs(for:)
抓取时间： 2025-12-04T13:39:08Z
---

# draggedItemIDs(for:)

**实例方法**

提供当前拖动项目的标识符数组（如果有的话）。

## 声明

```swift
func draggedItemIDs<ItemID>(for type: ItemID.Type) -> [ItemID] where ItemID : Hashable
```

## 讨论

如果在应用程序中开始拖动，拖动的项目具有标识符，且 SwiftUI 可以访问这些标识符，则可以使用此方法访问它们。

参数类型：标识符的类型。返回值包含拖动项目标识符的数组（如果提供）。如果没有拖动的指定类型的标识符，则返回空数组。


---
source: https://developer.apple.com/documentation/SwiftUI/DropSession/LocalSession-swift.struct/draggedItemIDs(for:)
crawled: 2025-12-04T13:39:08Z
---

# draggedItemIDs(for:)

**Instance Method**

Provides an array of identifiers of the currently dragged items if available.

## Declaration

```swift
func draggedItemIDs<ItemID>(for type: ItemID.Type) -> [ItemID] where ItemID : Hashable
```

## Discussion

If drag started within the application, the dragged items have identifiers, and SwiftUI has access to these identifiers, you can access them using this method.

Parameter type: The type of the identifiers. Returns: The array with the identifiers of the dragged items if provided. Returns an empty array if there are no dragged identifiers of a given type.

