---
来源： https://developer.apple.com/documentation/SwiftUI/TableColumnBuilder/buildExpression(_:)
抓取时间： 2025-12-03T06:40:46Z
---

# buildExpression(_:)

**类型方法**

创建通用的、不可排序的单列表达式。

## 声明

```swift
static func buildExpression<Column>(_ column: Column) -> Column where RowValue == Column.TableRowValue, Column : TableColumnContent, Column.TableColumnSortComparator == Never
```

## 创建列

- **buildBlock(_:)**：创建单个不可排序的列结果。
- **buildBlock(_:_:)**：从两个来源创建一个无法排序的列结果。
- **buildBlock(_:_:_:)**：从三个来源创建无法排序的列结果。
- **buildBlock(_:_:_:_:)**：从四个来源创建无法排序的列结果。
- **buildBlock(_:_:_:_:_:)**：从五个来源创建一个无法排序的列结果。
- **buildBlock(_:_:_:_:_:_:)**：从六个来源创建无法排序的列结果。
- **buildBlock(_:_:_:_:_:_:_:)**：从七个来源创建一个无法排序的列结果。
- **buildBlock(_:_:_:_:_:_:_:_:)**：从 8 个来源创建无法排序的列结果。
- **buildBlock(_:_:_:_:_:_:_:_:_:)**：从九个来源创建无法排序的列结果。
- **buildBlock(_:_:_:_:_:_:_:_:_:_:)**：从 10 个来源创建一个无法排序的列结果。


---
source: https://developer.apple.com/documentation/SwiftUI/TableColumnBuilder/buildExpression(_:)
crawled: 2025-12-03T06:40:46Z
---

# buildExpression(_:)

**Type Method**

Creates a generic, unsortable single column expression.

## Declaration

```swift
static func buildExpression<Column>(_ column: Column) -> Column where RowValue == Column.TableRowValue, Column : TableColumnContent, Column.TableColumnSortComparator == Never
```

## Building a column

- **buildBlock(_:)**: Creates a single, unsortable column result.
- **buildBlock(_:_:)**: Creates an unsortable column result from two sources.
- **buildBlock(_:_:_:)**: Creates an unsortable column result from three sources.
- **buildBlock(_:_:_:_:)**: Creates an unsortable column result from four sources.
- **buildBlock(_:_:_:_:_:)**: Creates an unsortable column result from five sources.
- **buildBlock(_:_:_:_:_:_:)**: Creates an unsortable column result from six sources.
- **buildBlock(_:_:_:_:_:_:_:)**: Creates an unsortable column result from seven sources.
- **buildBlock(_:_:_:_:_:_:_:_:)**: Creates an unsortable column result from eight sources.
- **buildBlock(_:_:_:_:_:_:_:_:_:)**: Creates an unsortable column result from nine sources.
- **buildBlock(_:_:_:_:_:_:_:_:_:_:)**: Creates an unsortable column result from ten sources.

