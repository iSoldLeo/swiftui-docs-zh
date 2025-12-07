---
来源： https://developer.apple.com/documentation/SwiftUI/DynamicTableRowContent/onInsert(of:perform:)
抓取时间： 2025-12-01T11:30:43Z
---

# onInsert(of:perform:)

**实例方法**

设置动态表行的插入操作。

## 声明

```swift
func onInsert(of supportedContentTypes: [UTType], perform action: @escaping (Int, [NSItemProvider]) -> Void) -> ModifiedContent<Self, OnInsertTableRowModifier>
```

## 参数

- **supportedContentTypes**：行支持的通用类型标识符类型数组。
- **action**：SwiftUI 向行集合添加元素时调用的闭包。闭包需要两个参数。第一个参数是相对于动态视图底层数据集合的偏移量。第二个参数是一个[doc://com.apple.documentation/documentation/Foundation/NSItemProvider] 项数组，表示要插入的数据。

## 返回值

一个视图，在向原视图插入元素时调用`action`。

## 插入行

- **OnInsertTableRowModifier**：表格行修改器，可在某些基本行内容中插入数据。


---
source: https://developer.apple.com/documentation/SwiftUI/DynamicTableRowContent/onInsert(of:perform:)
crawled: 2025-12-01T11:30:43Z
---

# onInsert(of:perform:)

**Instance Method**

Sets the insert action for the dynamic table rows.

## Declaration

```swift
func onInsert(of supportedContentTypes: [UTType], perform action: @escaping (Int, [NSItemProvider]) -> Void) -> ModifiedContent<Self, OnInsertTableRowModifier>
```

## Parameters

- **supportedContentTypes**: An array of universal type identifiers types that the rows supports.
- **action**: A closure that SwiftUI invokes when adding elements to the collection of rows. The closure takes two arguments. The first argument is the offset relative to the dynamic view’s underlying collection of data. The second argument is an array of [doc://com.apple.documentation/documentation/Foundation/NSItemProvider] items that represents the data that you want to insert.

## Return Value

A view that calls `action` when inserting elements into the original view.

## Inserting rows

- **OnInsertTableRowModifier**: A table row modifier that adds the ability to insert data in some base row content.

