---
来源：https://developer.apple.com/documentation/SwiftUI/TableColumn/init(_:sortUsing:content:)
抓取时间： 2025-12-03T06:40:22Z
---

# init(_:sortUsing:content:)

**Initializer**

创建带文本标签的可排序列。

## 声明

```swift
nonisolated init(_ text: Text, sortUsing comparator: Sort, @ViewBuilder content: @escaping (RowValue) -> Content)
```

## 参数

- **text**：列的标签。
- **comparator**：表示此列时使用的原型排序比较器。当用户点击或单击列标题时，包含表格的`sortOrder` 将包含此值，可能会翻转顺序。
- **content**：表格中每一行要显示的视图内容。

## 讨论

此初始化程序会为您创建一个 [Text](../Text.zh-Hans.md) 视图，并将标题处理为类似于 [init(_:)](../Text/init.zh-Hans.md)。有关字符串本地化的更多信息，请参阅 [Text](../Text.zh-Hans.md)。

## 创建可排序列

- **init(_:value:content:)**：为布尔值创建带文本标签的可排序列。
- **init(_:value:comparator:)**：创建显示字符串属性并带有文本标签的可排序列。
- **init(_:value:comparator:content:)**：创建带有文本标签的可排序列。


---
source: https://developer.apple.com/documentation/SwiftUI/TableColumn/init(_:sortUsing:content:)
crawled: 2025-12-03T06:40:22Z
---

# init(_:sortUsing:content:)

**Initializer**

Creates a sortable column with text label.

## Declaration

```swift
nonisolated init(_ text: Text, sortUsing comparator: Sort, @ViewBuilder content: @escaping (RowValue) -> Content)
```

## Parameters

- **text**: The column’s label.
- **comparator**: The prototype sort comparator to use when representing this column. When a person taps or clicks the column header, the containing table’s `sortOrder` incorporates this value, potentially with a flipped order.
- **content**: The view content to display for each row in a table.

## Discussion

This initializer creates a [Text](../Text.zh-Hans.md) view for you, and treats the title similar to [init(_:)](../Text/init.zh-Hans.md). For more information about localizing strings, see [Text](../Text.zh-Hans.md).

## Creating a sortable column

- **init(_:value:content:)**: Creates a sortable column for Boolean values with a text label.
- **init(_:value:comparator:)**: Creates a sortable column that displays a string property and has a text label.
- **init(_:value:comparator:content:)**: Creates a sortable column with a text label.

