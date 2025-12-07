---
来源： https://developer.apple.com/documentation/SwiftUI/TableColumn/init(_:value:comparator:)
抓取时间： 2025-12-01T11:29:41Z
---

# init(_:value:comparator:)

**Initializer**

创建显示字符串属性并带有文本标签的可排序列。

### 声明

```swift
init(_ text: Text, value: KeyPath<RowValue, String>, comparator: String.StandardComparator = .localizedStandard) where Content == Text
```

## 参数

- **text**：列的标签。
- **value**：与列相关联的属性的路径，在表格的每一行中以文本形式逐字显示，以及在对列进行排序时用于创建排序比较器的关键路径。
- **comparator**：用于对字符串值进行排序的`SortComparator`。

## 讨论

该初始化程序会为您创建一个 [Text](../Text.zh-Hans.md) 视图，其标题处理方式与 [init(_:)](../Text/init.zh-Hans.md)类似。有关字符串本地化的更多信息，请参阅 [Text](../Text.zh-Hans.md)。

## 创建可排序列

- **init(_:value:content:)**：为布尔值创建带文本标签的可排序列。
- **init(_:value:comparator:content:)**：创建带文本标签的可排序列。
- **init(_:sortUsing:content:)**：创建带文本标签的可排序列：创建带文本标签的可排序列。


---
source: https://developer.apple.com/documentation/SwiftUI/TableColumn/init(_:value:comparator:)
crawled: 2025-12-01T11:29:41Z
---

# init(_:value:comparator:)

**Initializer**

Creates a sortable column that displays a string property and has a text label.

## Declaration

```swift
init(_ text: Text, value: KeyPath<RowValue, String>, comparator: String.StandardComparator = .localizedStandard) where Content == Text
```

## Parameters

- **text**: The column’s label.
- **value**: The path to the property associated with the column, to display verbatim as text in each row of a table, and the key path used to create a sort comparator when sorting the column.
- **comparator**: The `SortComparator` used to order the string values.

## Discussion

This initializer creates a [Text](../Text.zh-Hans.md) view for you, and treats the title similar to [init(_:)](../Text/init.zh-Hans.md). For more information about localizing strings, see [Text](../Text.zh-Hans.md).

## Creating a sortable column

- **init(_:value:content:)**: Creates a sortable column for Boolean values with a text label.
- **init(_:value:comparator:content:)**: Creates a sortable column with a text label.
- **init(_:sortUsing:content:)**: Creates a sortable column with text label.

