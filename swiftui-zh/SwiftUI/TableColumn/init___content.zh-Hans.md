---
来源： https://developer.apple.com/documentation/SwiftUI/TableColumn/init(_:content:)
抓取时间： 2025-12-03T06:40:19Z
---

# init(_:content:)

**Initializer**

创建带文本标签的不可排序列

## 声明

```swift
nonisolated init(_ text: Text, @ViewBuilder content: @escaping (RowValue) -> Content)
```

## 参数

- **text**：列的标签。
- **content**：表格中每一行要显示的视图内容。

## 讨论

该初始化程序将为您创建一个 [Text](../Text.zh-Hans.md) 视图，并将标题处理为类似于 [init(_:)](../Text/init.zh-Hans.md)。有关字符串本地化的信息，请参阅 [Text](../Text.zh-Hans.md)。

## 创建不可排序列

- **init(_:value:)**：创建不可排序列，显示带有文本标签的字符串属性。


---
source: https://developer.apple.com/documentation/SwiftUI/TableColumn/init(_:content:)
crawled: 2025-12-03T06:40:19Z
---

# init(_:content:)

**Initializer**

Creates an unsortable column with a text label

## Declaration

```swift
nonisolated init(_ text: Text, @ViewBuilder content: @escaping (RowValue) -> Content)
```

## Parameters

- **text**: The column’s label.
- **content**: The view content to display for each row in a table.

## Discussion

This initializer creates a [Text](../Text.zh-Hans.md) view for you, and treats the title similar to [init(_:)](../Text/init.zh-Hans.md). For information about localizing strings, see [Text](../Text.zh-Hans.md).

## Creating an unsortable column

- **init(_:value:)**: Creates an unsortable column that displays a string property with a text label.

