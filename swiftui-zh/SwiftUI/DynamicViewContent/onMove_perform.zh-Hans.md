--- 来源：https://developer.apple.com/documentation/SwiftUI/DynamicViewContent/onMove(perform:)

抓取时间：2025-12-03T05:37:29Z

---

# onMove(perform:)

**实例方法**

设置动态视图的移动操作。

## 声明

```swift
nonisolated func onMove(perform action: Optional<(IndexSet, Int) -> Void>) -> some DynamicViewContent

```

## 参数

- **action**：当动态视图中的元素移动时，SwiftUI 会调用此闭包。此闭包接受两个参数，分别表示相对于动态视图底层数据集合的偏移量。传递 `nil` 可禁用移动元素的功能。

## 返回值

一个视图，当元素在原始视图内移动时，该视图会调用 `action`。

## 响应更新

- **onDelete(perform:)**：设置动态视图的删除操作。您必须删除 `action` 中的相应项，因为该操作会在 [List](../List.zh-Hans.md) 中的行被移除后调用。

- **onInsert(of:perform:)**：设置动态视图的插入操作。

- **dropDestination(for:action:)**：设置动态视图的插入操作。


---
source: https://developer.apple.com/documentation/SwiftUI/DynamicViewContent/onMove(perform:)
crawled: 2025-12-03T05:37:29Z
---

# onMove(perform:)

**Instance Method**

Sets the move action for the dynamic view.

## Declaration

```swift
nonisolated func onMove(perform action: Optional<(IndexSet, Int) -> Void>) -> some DynamicViewContent

```

## Parameters

- **action**: A closure that SwiftUI invokes when elements in the dynamic view are moved. The closure takes two arguments that represent the offset relative to the dynamic view’s underlying collection of data. Pass `nil` to disable the ability to move items.

## Return Value

A view that calls `action` when elements are moved within the original view.

## Responding to updates

- **onDelete(perform:)**: Sets the deletion action for the dynamic view. You must delete the corresponding item within `action`, as it will be called after the row has already been removed from the [List](../List.zh-Hans.md).
- **onInsert(of:perform:)**: Sets the insert action for the dynamic view.
- **dropDestination(for:action:)**: Sets the insert action for the dynamic view.

