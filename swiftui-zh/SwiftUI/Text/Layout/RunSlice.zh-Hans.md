--- 来源：https://developer.apple.com/documentation/SwiftUI/Text/Layout/RunSlice
抓取时间：2025-12-03T19:59:34Z

---

# Text.Layout.RunSlice

**Structure**

文本布局中已放置字形序列的切片。

## 声明

```swift
struct RunSlice
```

## 初始化器

- **init(run:indices:)**

## 实例属性

- **characterIndices**：对应于 `self` 中字形的字符索引数组。

- **run**

- **typographicBounds**：部分字形序列的排版边界。

## 下标

- **subscript(_:)**：与字形序列关联的自定义属性，类型为 `T`，如果为空则为 nil。

## 符合以下标准

- BidirectionalCollection

- Collection

- Equatable

- RandomAccessCollection

- Sequence


---
source: https://developer.apple.com/documentation/SwiftUI/Text/Layout/RunSlice
crawled: 2025-12-03T19:59:34Z
---

# Text.Layout.RunSlice

**Structure**

A slice of a run of placed glyphs in a text layout.

## Declaration

```swift
struct RunSlice
```

## Initializers

- **init(run:indices:)**

## Instance Properties

- **characterIndices**: The array of character indices corresponding to the glyphs in `self`.
- **run**
- **typographicBounds**: The typographic bounds of the partial run of glyphs.

## Subscripts

- **subscript(_:)**: The custom attribute of type `T` associated with the run of glyphs, or nil.

## Conforms To

- BidirectionalCollection
- Collection
- Equatable
- RandomAccessCollection
- Sequence

