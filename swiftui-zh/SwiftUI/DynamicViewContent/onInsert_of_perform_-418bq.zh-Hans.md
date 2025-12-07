--- 来源：https://developer.apple.com/documentation/SwiftUI/DynamicViewContent/onInsert(of:perform:)-418bq

抓取时间：2025-12-03T05:37:28Z

---

# onInsert(of:perform:)

**实例方法**

设置动态视图的插入操作。

## 声明

```swift
nonisolated func onInsert(of supportedContentTypes: [UTType], perform action: @escaping (Int, [NSItemProvider]) -> Void) -> some DynamicViewContent

```

## 参数

- **supportedContentTypes**：动态视图支持的 UTI 类型数组。

- **action**：SwiftUI 在向视图添加元素时调用的闭包。该闭包接受两个参数：第一个参数是相对于动态视图底层数据集合的偏移量。第二个参数是一个包含 [doc://com.apple.documentation/documentation/Foundation/NSItemProvider] 项的数组，代表您要插入的数据。

## 返回值

当元素插入到原始视图中时，会调用 `action` 的视图。

## 响应更新

- **onDelete(perform:)**：设置动态视图的删除操作。您必须删除 `action` 中的相应项，因为该操作会在行已从 [List](../List.zh-Hans.md) 中移除后调用。

- **onMove(perform:)**：设置动态视图的移动操作。

- **dropDestination(for:action:)**：设置动态视图的插入操作。


---
source: https://developer.apple.com/documentation/SwiftUI/DynamicViewContent/onInsert(of:perform:)-418bq
crawled: 2025-12-03T05:37:28Z
---

# onInsert(of:perform:)

**Instance Method**

Sets the insert action for the dynamic view.

## Declaration

```swift
nonisolated func onInsert(of supportedContentTypes: [UTType], perform action: @escaping (Int, [NSItemProvider]) -> Void) -> some DynamicViewContent

```

## Parameters

- **supportedContentTypes**: An array of UTI types that the dynamic view supports.
- **action**: A closure that SwiftUI invokes when elements are added to the view. The closure takes two arguments: The first argument is the offset relative to the dynamic view’s underlying collection of data. The second argument is an array of [doc://com.apple.documentation/documentation/Foundation/NSItemProvider] items that represents the data that you want to insert.

## Return Value

A view that calls `action` when elements are inserted into the original view.

## Responding to updates

- **onDelete(perform:)**: Sets the deletion action for the dynamic view. You must delete the corresponding item within `action`, as it will be called after the row has already been removed from the [List](../List.zh-Hans.md).
- **onMove(perform:)**: Sets the move action for the dynamic view.
- **dropDestination(for:action:)**: Sets the insert action for the dynamic view.

