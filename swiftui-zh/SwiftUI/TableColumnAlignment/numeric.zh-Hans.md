--- 来源：https://developer.apple.com/documentation/SwiftUI/TableColumnAlignment/numeric(_:)

抓取时间：2025-12-03T06:40:37Z

---

# numeric(_:)

**类型方法**

适用于数值内容的列对齐方式。

## 声明

```swift
static func numeric(_ numberingSystem: Locale.NumberingSystem) -> TableColumnAlignment
```

## 说明

当表格列主要显示数值内容时，请使用此对齐方式，以便于快速浏览和比较数值。

此方法使用提供的编号系统来确定对齐方式：

- 对于从左到右的编号系统，此对齐方式等效于向右对齐。

- 对于从右到左的编号系统，此对齐方式等效于向左对齐。

## 获取对齐方式

- **automatic**：默认列对齐方式。

- **leading**：前导列对齐方式。

- **center**：列居中对齐。

- **trailing**：列尾对齐。

- **numeric**：适用于数值内容的列对齐方式。


---
source: https://developer.apple.com/documentation/SwiftUI/TableColumnAlignment/numeric(_:)
crawled: 2025-12-03T06:40:37Z
---

# numeric(_:)

**Type Method**

Column alignment appropriate for numeric content.

## Declaration

```swift
static func numeric(_ numberingSystem: Locale.NumberingSystem) -> TableColumnAlignment
```

## Discussion

Use this alignment when a table column is primarily displaying numeric content, so that the values are easy to visually scan and compare.

This uses the provided numbering system to determine the alignment:

- For left to right numbering systems, this is equivalent to right.
- For right to left numbering systems, this is equivalent to left.

## Getting the alignment

- **automatic**: The default column alignment.
- **leading**: Leading column alignment.
- **center**: Center column alignment.
- **trailing**: Trailing column alignment.
- **numeric**: Column alignment appropriate for numeric content.

