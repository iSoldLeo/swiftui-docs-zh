--- 来源：https://developer.apple.com/documentation/SwiftUI/DynamicViewContent
抓取时间：2025-12-02T17:26:30Z

---

# DynamicViewContent

**Protocol**

一种视图类型，它根据底层数据集合生成视图。

## 声明

```swift
protocol DynamicViewContent<Data> : View
```

## 数据管理

- **data**：底层数据集合。

- **Data**：底层数据集合的类型。

## 响应更新

- **onDelete(perform:)**：设置动态视图的删除操作。您必须删除 `action` 中的对应项，因为它会在该行已从 [List](List.zh-Hans.md) 中移除后被调用。

- **onInsert(of:perform:)**：设置动态视图的插入操作。

- **onMove(perform:)**：设置动态视图的移动操作。

- **dropDestination(for:action:)**：设置动态视图的插入操作。

## 已弃用符号

- **onInsert(of:perform:)**：设置动态视图的插入操作。

## 实例方法

- **onInsert(of:perform:)**：设置动态视图的插入操作。

## 遍历动态数据

- **ForEach**：一种根据底层已识别数据集合按需计算视图的结构。 - **ForEachSectionCollection**：一个集合，允许在 foreach 循环中将视图视为其各个部分的集合。

- **ForEachSubviewCollection**：一个集合，允许在 foreach 循环中将视图视为其各个子视图的集合。

## 继承自

- View

## 符合的类型

- ForEach

- ModifiedContent


---
source: https://developer.apple.com/documentation/SwiftUI/DynamicViewContent
crawled: 2025-12-02T17:26:30Z
---

# DynamicViewContent

**Protocol**

A type of view that generates views from an underlying collection of data.

## Declaration

```swift
protocol DynamicViewContent<Data> : View
```

## Managing the data

- **data**: The collection of underlying data.
- **Data**: The type of the underlying collection of data.

## Responding to updates

- **onDelete(perform:)**: Sets the deletion action for the dynamic view. You must delete the corresponding item within `action`, as it will be called after the row has already been removed from the [List](List.zh-Hans.md).
- **onInsert(of:perform:)**: Sets the insert action for the dynamic view.
- **onMove(perform:)**: Sets the move action for the dynamic view.
- **dropDestination(for:action:)**: Sets the insert action for the dynamic view.

## Deprecated symbols

- **onInsert(of:perform:)**: Sets the insert action for the dynamic view.

## Instance Methods

- **onInsert(of:perform:)**: Sets the insert action for the dynamic view.

## Iterating over dynamic data

- **ForEach**: A structure that computes views on demand from an underlying collection of identified data.
- **ForEachSectionCollection**: A collection which allows a view to be treated as a collection of its sections in a for each loop.
- **ForEachSubviewCollection**: A collection which allows a view to be treated as a collection of its subviews in a for each loop.

## Inherits From

- View

## Conforming Types

- ForEach
- ModifiedContent

