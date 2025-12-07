---
来源：https://developer.apple.com/documentation/SwiftUI/TableColumnBuilder/buildEither(Second:)
抓取时间：2025-12-01T11:30:06Z
---

# buildEither(second:)

**类型方法**

为两个行内容选项中的第二个选项创建行结果。

## 声明

```swift
static func buildEither<T, F>(second: F) -> _ConditionalContent<T, F> where RowValue == T.TableRowValue, Sort == T.TableColumnSortComparator, T : TableColumnContent, F : TableColumnContent, T.TableColumnSortComparator == F.TableColumnSortComparator, T.TableRowValue == F.TableRowValue
```

## 讨论

本方法支持多语句闭包中的 "if "语句，为 "else "分支生成条件内容。


---
source: https://developer.apple.com/documentation/SwiftUI/TableColumnBuilder/buildEither(second:)
crawled: 2025-12-01T11:30:06Z
---

# buildEither(second:)

**Type Method**

Creates a row result for the second of two row content alternatives.

## Declaration

```swift
static func buildEither<T, F>(second: F) -> _ConditionalContent<T, F> where RowValue == T.TableRowValue, Sort == T.TableColumnSortComparator, T : TableColumnContent, F : TableColumnContent, T.TableColumnSortComparator == F.TableColumnSortComparator, T.TableRowValue == F.TableRowValue
```

## Discussion

This method provides support for “if” statements in multi-statement closures, producing conditional content for the “else” branch.

