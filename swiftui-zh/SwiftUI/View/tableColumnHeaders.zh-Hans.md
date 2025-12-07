--- 来源：https://developer.apple.com/documentation/SwiftUI/View/tableColumnHeaders(_:)

抓取时间：2025-12-02T17:39:57Z

---

# tableColumnHeaders(_:)

**实例方法**

控制 `Table` 的列标题视图的可见性。

## 声明

```swift
nonisolated func tableColumnHeaders(_ visibility: Visibility) -> some View

```

## 参数

- **visibility**：值为 `visible` 将显示表格列，`hidden` 将移除列，`automatic` 将遵循默认行为。

## 讨论

默认情况下，`Table` 将显示一个全局表头视图，其中包含每个表格列的标签。用户也可以在此区域对列进行排序、调整大小和重新排列。对于不需要这些功能的简单情况，可以隐藏此表头。

这不会影响表格中任何 `Section` 的表头。

```swift
Table(article.authors) {
    TableColumn("Name", value: \.name)
    TableColumn("Title", value: \.title)
}
.tableColumnHeaders(.hidden)
```

## 自定义列

- **TableColumnCustomization**：表格中列状态的表示。

- **TableColumnCustomizationBehavior**：表格可以向用户提供的列自定义行为集。


---
source: https://developer.apple.com/documentation/SwiftUI/View/tableColumnHeaders(_:)
crawled: 2025-12-02T17:39:57Z
---

# tableColumnHeaders(_:)

**Instance Method**

Controls the visibility of a `Table`’s column header views.

## Declaration

```swift
nonisolated func tableColumnHeaders(_ visibility: Visibility) -> some View

```

## Parameters

- **visibility**: A value of `visible` will show table columns, `hidden` will remove them, and `automatic` will defer to default behavior.

## Discussion

By default, `Table` will display a global header view with the labels of each table column. This area is also where users can sort, resize, and rearrange the columns. For simple cases that don’t require those features, this header can be hidden.

This will not affect the header of any `Section`s in a table.

```swift
Table(article.authors) {
    TableColumn("Name", value: \.name)
    TableColumn("Title", value: \.title)
}
.tableColumnHeaders(.hidden)
```

## Customizing columns

- **TableColumnCustomization**: A representation of the state of the columns in a table.
- **TableColumnCustomizationBehavior**: A set of customization behaviors of a column that a table can offer to a user.

