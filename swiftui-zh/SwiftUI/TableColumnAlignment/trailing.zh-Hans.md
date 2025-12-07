--- 来源：https://developer.apple.com/documentation/SwiftUI/TableColumnAlignment/trailing
抓取时间：2025-12-03T06:40:36Z

---

# 尾部对齐

**类型属性**

尾部列对齐方式。

## 声明

```swift
static var trailing: TableColumnAlignment { get }
```

## 说明

当 `layoutDirection` 为 `leftToRight` 时，此属性等效于右对齐；当 `layoutDirection` 为 `rightToLeft` 时，此属性等效于左对齐。

## 获取对齐方式

- **automatic**：默认列对齐方式。

- **leading**：前导列对齐方式。

- **center**：居中对齐。

- **numeric**：适合数值内容的列对齐方式。

- **numeric(_:)**：适合数值内容的列对齐方式。


---
source: https://developer.apple.com/documentation/SwiftUI/TableColumnAlignment/trailing
crawled: 2025-12-03T06:40:36Z
---

# trailing

**Type Property**

Trailing column alignment.

## Declaration

```swift
static var trailing: TableColumnAlignment { get }
```

## Discussion

With a `layoutDirection` of `leftToRight`, this is equivalent to right; and with a `layoutDirection` of `rightToLeft`, this is equivalent to left.

## Getting the alignment

- **automatic**: The default column alignment.
- **leading**: Leading column alignment.
- **center**: Center column alignment.
- **numeric**: Column alignment appropriate for numeric content.
- **numeric(_:)**: Column alignment appropriate for numeric content.

