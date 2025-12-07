--- 来源：https://developer.apple.com/documentation/SwiftUI/Text/Layout/Run
抓取时间：2025-12-03T19:59:33Z

---

# Text.Layout.Run

**Structure**

文本布局中已放置字形的序列。

## 声明

```swift
struct Run
```

## 实例属性

- **characterIndices**：对应于 `self` 中字形的字符索引数组。

- **layoutDirection**：文本序列的布局方向。

- **typographicBounds**：字形序列的排版边界。

## 下标

- **subscript(_:)**：与字形序列关联的类型为 `T` 的自定义属性，如果为空则为 nil。如果任何序列都不包含此自定义属性，我们还会检查其附件的序列。

## 符合以下标准

- BidirectionalCollection

- Collection

- Equatable

- RandomAccessCollection

- Sequence


---
source: https://developer.apple.com/documentation/SwiftUI/Text/Layout/Run
crawled: 2025-12-03T19:59:33Z
---

# Text.Layout.Run

**Structure**

A run of placed glyphs in a text layout.

## Declaration

```swift
struct Run
```

## Instance Properties

- **characterIndices**: The array of character indices corresponding to the glyphs in `self`.
- **layoutDirection**: The layout direction of the text run.
- **typographicBounds**: The typographic bounds of the run of glyphs.

## Subscripts

- **subscript(_:)**: The custom attribute of type `T` associated with the run of glyphs, or nil. If no run contains the custom attribute we also check its attachment’s runs.

## Conforms To

- BidirectionalCollection
- Collection
- Equatable
- RandomAccessCollection
- Sequence

