---
来源：https://developer.apple.com/documentation/SwiftUI/TableColumn/init(_:value:)
抓取时间：2025-12-03T06:40:18Z
---

# init(_:value:)

**Initializer**

创建不可排序列，显示带有文本标签的字符串属性。

### 声明

```swift
nonisolated init(_ text: Text, value: KeyPath<RowValue, String>) where Content == Text
```

## 参数

- **text**：列的标签。
- **value**：与列相关联的属性的路径。表格使用该路径在表格的每一行中以逐字文本的形式显示属性。

### 讨论

此初始化程序会为您创建一个 [Text](../Text.zh-Hans.md) 视图，并处理与 [init(_:tableName:bundle:comment:)](../Text/init___tableName_bundle_comment.zh-Hans.md) 类似的本地化键。有关字符串本地化的更多信息，请参阅 [Text](../Text.zh-Hans.md)。

## 创建不可排序列

- **init(_:content:)**：创建带文本标签的不可排序列


---
source: https://developer.apple.com/documentation/SwiftUI/TableColumn/init(_:value:)
crawled: 2025-12-03T06:40:18Z
---

# init(_:value:)

**Initializer**

Creates an unsortable column that displays a string property with a text label.

## Declaration

```swift
nonisolated init(_ text: Text, value: KeyPath<RowValue, String>) where Content == Text
```

## Parameters

- **text**: The column’s label.
- **value**: The path to the property associated with the column. The table uses this to display the property as verbatim text in each row of the table.

## Discussion

This initializer creates a [Text](../Text.zh-Hans.md) view for you, and treats the localized key similar to [init(_:tableName:bundle:comment:)](../Text/init___tableName_bundle_comment.zh-Hans.md). For more information about localizing strings, see [Text](../Text.zh-Hans.md).

## Creating an unsortable column

- **init(_:content:)**: Creates an unsortable column with a text label

