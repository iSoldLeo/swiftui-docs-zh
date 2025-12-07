---
来源： https://developer.apple.com/documentation/SwiftUI/TableColumnBuilder/buildBlock(_:_:_:_:_:_:)
抓取时间：2025-12-03T06:40:42Z


# buildBlock(_:_:_:_:_:_:)

**类型方法**

从五个来源创建一个不可排序列结果。

## 声明

```swift
static func buildBlock<C0, C1, C2, C3, C4>(_ c0: C0, _ c1: C1, _ c2: C2, _ c3: C3, _ c4: C4) -> TupleTableColumnContent<RowValue, Never, (C0, C1, C2, C3, C4)> where RowValue == C0.TableRowValue, C0 : TableColumnContent, C1 : TableColumnContent, C2 : TableColumnContent, C3 : TableColumnContent, C4 : TableColumnContent, C0.TableColumnSortComparator == Never, C0.TableRowValue == C1.TableRowValue, C1.TableColumnSortComparator == Never, C1.TableRowValue == C2.TableRowValue, C2.TableColumnSortComparator == Never, C2.TableRowValue == C3.TableRowValue, C3.TableColumnSortComparator == Never, C3.TableRowValue == C4.TableRowValue, C4.TableColumnSortComparator == Never
```

## 创建列

- **buildBlock(_:)**：创建单个不可排序的列结果。
- **buildBlock(_:_:)**：从两个来源创建一个无法排序的列结果。
- **buildBlock(_:_:_:)**：从三个来源创建无法排序的列结果。
- **buildBlock(_:_:_:_:)**：从四个来源创建无法排序的列结果。
- **buildBlock(_:_:_:_:_:_:)**：从六个来源创建一个无法排序的列结果。
- **buildBlock(_:_:_:_:_:_:_:)**：从七个来源创建一个无法排序的列结果。
- **buildBlock(_:_:_:_:_:_:_:_:)**：从 8 个来源创建无法排序的列结果。
- **buildBlock(_:_:_:_:_:_:_:_:_:)**：从九个来源创建无法排序的列结果。
- **buildBlock(_:_:_:_:_:_:_:_:_:_:)**：从 10 个来源创建一个无法排序的列结果。
- **buildExpression(_:)**：创建通用的、不可排序的单列表达式。


---
source: https://developer.apple.com/documentation/SwiftUI/TableColumnBuilder/buildBlock(_:_:_:_:_:)
crawled: 2025-12-03T06:40:42Z
---

# buildBlock(_:_:_:_:_:)

**Type Method**

Creates an unsortable column result from five sources.

## Declaration

```swift
static func buildBlock<C0, C1, C2, C3, C4>(_ c0: C0, _ c1: C1, _ c2: C2, _ c3: C3, _ c4: C4) -> TupleTableColumnContent<RowValue, Never, (C0, C1, C2, C3, C4)> where RowValue == C0.TableRowValue, C0 : TableColumnContent, C1 : TableColumnContent, C2 : TableColumnContent, C3 : TableColumnContent, C4 : TableColumnContent, C0.TableColumnSortComparator == Never, C0.TableRowValue == C1.TableRowValue, C1.TableColumnSortComparator == Never, C1.TableRowValue == C2.TableRowValue, C2.TableColumnSortComparator == Never, C2.TableRowValue == C3.TableRowValue, C3.TableColumnSortComparator == Never, C3.TableRowValue == C4.TableRowValue, C4.TableColumnSortComparator == Never
```

## Building a column

- **buildBlock(_:)**: Creates a single, unsortable column result.
- **buildBlock(_:_:)**: Creates an unsortable column result from two sources.
- **buildBlock(_:_:_:)**: Creates an unsortable column result from three sources.
- **buildBlock(_:_:_:_:)**: Creates an unsortable column result from four sources.
- **buildBlock(_:_:_:_:_:_:)**: Creates an unsortable column result from six sources.
- **buildBlock(_:_:_:_:_:_:_:)**: Creates an unsortable column result from seven sources.
- **buildBlock(_:_:_:_:_:_:_:_:)**: Creates an unsortable column result from eight sources.
- **buildBlock(_:_:_:_:_:_:_:_:_:)**: Creates an unsortable column result from nine sources.
- **buildBlock(_:_:_:_:_:_:_:_:_:_:)**: Creates an unsortable column result from ten sources.
- **buildExpression(_:)**: Creates a generic, unsortable single column expression.

