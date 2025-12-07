--- 来源：https://developer.apple.com/documentation/SwiftUI/TableColumnAlignment/leading
抓取时间：2025-12-03T06:40:34Z

---

# 前导列对齐

**类型属性**

前导列对齐方式。

## 声明

```swift
static var leading: TableColumnAlignment { get }
```

## 说明

当 `layoutDirection` 为 `leftToRight` 时，此属性等效于左对齐；当 `layoutDirection` 为 `rightToLeft` 时，此属性等效于右对齐。

## 获取对齐方式

- **automatic**：默认列对齐方式。

- **center**：居中对齐。

- **trailing**：列尾对齐。

- **numeric**：适用于数值内容的列对齐方式。

- **numeric(_:)**：适用于数值内容的列对齐方式。


---
source: https://developer.apple.com/documentation/SwiftUI/TableColumnAlignment/leading
crawled: 2025-12-03T06:40:34Z
---

# leading

**Type Property**

Leading column alignment.

## Declaration

```swift
static var leading: TableColumnAlignment { get }
```

## Discussion

With a `layoutDirection` of `leftToRight`, this is equivalent to left; and with a `layoutDirection` of `rightToLeft`, this is equivalent to right.

## Getting the alignment

- **automatic**: The default column alignment.
- **center**: Center column alignment.
- **trailing**: Trailing column alignment.
- **numeric**: Column alignment appropriate for numeric content.
- **numeric(_:)**: Column alignment appropriate for numeric content.

