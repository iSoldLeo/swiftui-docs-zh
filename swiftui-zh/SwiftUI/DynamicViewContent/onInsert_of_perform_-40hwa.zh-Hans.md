--- 来源：https://developer.apple.com/documentation/SwiftUI/DynamicViewContent/onInsert(of:perform:)-40hwa

抓取时间：2025-12-03T05:37:30Z

---

# onInsert(of:perform:)

**实例方法**

设置动态视图的插入操作。

## 声明

```swift
func onInsert(of acceptedTypeIdentifiers: [String], perform action: @escaping (Int, [NSItemProvider]) -> Void) -> some DynamicViewContent

```

## 参数

- **acceptedTypeIdentifiers**：动态视图支持的 UTI 类型数组。

- **action**：SwiftUI 在向视图添加元素时调用的闭包。该闭包接受两个参数：第一个参数是相对于动态视图底层数据集合的偏移量。第二个参数是一个数组 `NSItemProvider`，代表你要插入的数据。

## 返回值

返回一个视图，当元素插入到原始视图中时，该视图会调用 `action`。


---
source: https://developer.apple.com/documentation/SwiftUI/DynamicViewContent/onInsert(of:perform:)-40hwa
crawled: 2025-12-03T05:37:30Z
---

# onInsert(of:perform:)

**Instance Method**

Sets the insert action for the dynamic view.

## Declaration

```swift
func onInsert(of acceptedTypeIdentifiers: [String], perform action: @escaping (Int, [NSItemProvider]) -> Void) -> some DynamicViewContent

```

## Parameters

- **acceptedTypeIdentifiers**: An array of UTI types that the dynamic view supports.
- **action**: A closure that SwiftUI invokes when elements are added to the view. The closure takes two arguments: The first argument is the offset relative to the dynamic view’s underlying collection of data. The second argument is an array of `NSItemProvider` that represents the data that you want to insert.

## Return Value

A view that calls `action` when elements are inserted into the original view.

