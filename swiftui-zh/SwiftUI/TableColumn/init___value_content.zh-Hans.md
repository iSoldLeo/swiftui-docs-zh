---
来源：https://developer.apple.com/documentation/SwiftUI/TableColumn/init(_:value:content:)
抓取时间： 2025-12-01T11:29:40Z
---

# init(_:value:content:)

**Initializer**

为布尔值创建带文本标签的可排序列。

## 声明

```swift
init(_ text: Text, value: KeyPath<RowValue, Bool>, @ViewBuilder content: @escaping (RowValue) -> Content)
```

## 参数

- **text**：列的标签。
- **value**：与列相关的属性的路径，该属性将用于更新和反映表格中的排序状态。
- **content**：为表格中每一行显示的视图内容。

## 讨论

这个初始化程序会代表你创建一个 [Text](../Text.zh-Hans.md) 视图，并处理与 [init(_:tableName:bundle:comment:)](../Text/init___tableName_bundle_comment.zh-Hans.md) 类似的本地化键。有关字符串本地化的更多信息，请参阅 [Text](../Text.zh-Hans.md)。

## 创建可排序列

- **init(_:value:comparator:)**：创建显示字符串属性并带有文本标签的可排序列。
- **init(_:value:comparator:content:)**：创建带有文本标签的可排序列。
- **init(_:sortUsing:content:)**：创建带文本标签的可排序列。


---
source: https://developer.apple.com/documentation/SwiftUI/TableColumn/init(_:value:content:)
crawled: 2025-12-01T11:29:40Z
---

# init(_:value:content:)

**Initializer**

Creates a sortable column for Boolean values with a text label.

## Declaration

```swift
init(_ text: Text, value: KeyPath<RowValue, Bool>, @ViewBuilder content: @escaping (RowValue) -> Content)
```

## Parameters

- **text**: The column’s label.
- **value**: The path to the property associated with the column, which will be used to update and reflect the sorting state in a table.
- **content**: The view content to display for each row in a table.

## Discussion

This initializer creates a [Text](../Text.zh-Hans.md) view on your behalf, and treats the localized key similar to [init(_:tableName:bundle:comment:)](../Text/init___tableName_bundle_comment.zh-Hans.md). See [Text](../Text.zh-Hans.md) for more information about localizing strings.

## Creating a sortable column

- **init(_:value:comparator:)**: Creates a sortable column that displays a string property and has a text label.
- **init(_:value:comparator:content:)**: Creates a sortable column with a text label.
- **init(_:sortUsing:content:)**: Creates a sortable column with text label.

