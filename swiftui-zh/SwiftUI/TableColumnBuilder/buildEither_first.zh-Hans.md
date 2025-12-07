---
来源：https://developer.apple.com/documentation/SwiftUI/TableColumnBuilder/buildEither(first:)
抓取时间： 2025-12-03T06:40:47Z
---

# buildEither(first:)

**类型方法**

为两个列内容选项中的第一个创建一个列结果。

## 声明

```swift
static func buildEither<T, F>(first: T) -> _ConditionalContent<T, F> where RowValue == T.TableRowValue, Sort == T.TableColumnSortComparator, T : TableColumnContent, F : TableColumnContent, T.TableColumnSortComparator == F.TableColumnSortComparator, T.TableRowValue == F.TableRowValue
```

## 讨论

本方法支持多语句闭包中的 "if "语句，为 "then "分支生成条件内容。


---
source: https://developer.apple.com/documentation/SwiftUI/TableColumnBuilder/buildEither(first:)
crawled: 2025-12-03T06:40:47Z
---

# buildEither(first:)

**Type Method**

Creates a column result for the first of two column content alternatives.

## Declaration

```swift
static func buildEither<T, F>(first: T) -> _ConditionalContent<T, F> where RowValue == T.TableRowValue, Sort == T.TableColumnSortComparator, T : TableColumnContent, F : TableColumnContent, T.TableColumnSortComparator == F.TableColumnSortComparator, T.TableRowValue == F.TableRowValue
```

## Discussion

This method provides support for “if” statements in multi-statement closures, producing conditional content for the “then” branch.

