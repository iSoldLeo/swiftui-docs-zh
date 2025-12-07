--- 来源：https://developer.apple.com/documentation/SwiftUI/DynamicViewContent/onDelete(perform:)

抓取时间：2025-12-03T05:37:27Z

---

# onDelete(perform:)

**实例方法**

设置动态视图的删除操作。您必须删除 `action` 中的对应项，因为此方法会在行从 [List](../List.zh-Hans.md) 中移除后调用。

## 声明

```swift
nonisolated func onDelete(perform action: Optional<(IndexSet) -> Void>) -> some DynamicViewContent

```

## 参数

- **action**：您希望 SwiftUI 在视图中的元素被删除时执行的操作。SwiftUI 会将一组相对于动态视图底层数据集合的索引传递给闭包。

## 返回值

当原始视图中的元素被删除时，会调用 `action` 的视图。

## 响应更新

- **onInsert(of:perform:)**：设置动态视图的插入操作。

- **onMove(perform:)**：设置动态视图的移动操作。

- **dropDestination(for:action:)**：设置动态视图的插入操作。


---
source: https://developer.apple.com/documentation/SwiftUI/DynamicViewContent/onDelete(perform:)
crawled: 2025-12-03T05:37:27Z
---

# onDelete(perform:)

**Instance Method**

Sets the deletion action for the dynamic view. You must delete the corresponding item within `action`, as it will be called after the row has already been removed from the [List](../List.zh-Hans.md).

## Declaration

```swift
nonisolated func onDelete(perform action: Optional<(IndexSet) -> Void>) -> some DynamicViewContent

```

## Parameters

- **action**: The action that you want SwiftUI to perform when elements in the view are deleted. SwiftUI passes a set of indices to the closure that’s relative to the dynamic view’s underlying collection of data.

## Return Value

A view that calls `action` when elements are deleted from the original view.

## Responding to updates

- **onInsert(of:perform:)**: Sets the insert action for the dynamic view.
- **onMove(perform:)**: Sets the move action for the dynamic view.
- **dropDestination(for:action:)**: Sets the insert action for the dynamic view.

