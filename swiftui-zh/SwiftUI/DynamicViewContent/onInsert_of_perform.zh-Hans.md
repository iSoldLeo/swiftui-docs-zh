--- 来源：https://developer.apple.com/documentation/SwiftUI/DynamicViewContent/onInsert(of:perform:)

抓取时间：2025-12-01T10:26:40Z

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

- **action**：SwiftUI 在向视图添加元素时调用的闭包。该闭包接受两个参数：第一个参数是相对于动态视图底层数据集合的偏移量。第二个参数是一个 [doc://com.apple.documentation/documentation/Foundation/NSItemProvider] 项数组，表示要插入的数据。

## 返回值

当元素插入到原始视图中时，会调用 `action` 的视图。


---
source: https://developer.apple.com/documentation/SwiftUI/DynamicViewContent/onInsert(of:perform:)
crawled: 2025-12-01T10:26:40Z
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

