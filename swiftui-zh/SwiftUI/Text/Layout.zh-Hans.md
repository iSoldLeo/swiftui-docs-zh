--- 来源：https://developer.apple.com/documentation/SwiftUI/Text/Layout
抓取时间：2025-12-02T21:48:44Z

---

# Text.Layout

**Structure**

描述视图树的布局和自定义属性的值。`Text`

## 声明

```swift
struct Layout
```

## 结构体

- **Text.Layout.CharacterIndex**：源文本中字符的索引。这是一个不透明类型，用于确定布局中元素的相对位置，而不是它们如何映射到源字符串。

- **Text.Layout.DrawingOptions**：在图形上下文中绘制线条或运行时使用的选项标志。`Text.Layout`

- **Text.Layout.Line**：文本布局中的单行：一组已放置的字形。

- **Text.Layout.Run**：文本布局中的一段已放置的字形。

- **Text.Layout.RunSlice**：文本布局中一段已放置的字形的切片。

- **Text.Layout.TypographicBounds**：文本布局中元素的排版边界。

## 实例属性

- **isTruncated**：指示此文本是否被截断。

## 符合以下类型：

- BidirectionalCollection

- Collection

- Equatable

- RandomAccessCollection

- Sequence


---
source: https://developer.apple.com/documentation/SwiftUI/Text/Layout
crawled: 2025-12-02T21:48:44Z
---

# Text.Layout

**Structure**

A value describing the layout and custom attributes of a tree of `Text` views.

## Declaration

```swift
struct Layout
```

## Structures

- **Text.Layout.CharacterIndex**: The index of a character in the source text. An opaque type, this is intended to be used to determine relative locations of elements in the layout, rather than how they map to the source strings.
- **Text.Layout.DrawingOptions**: Option flags used when drawing `Text.Layout` lines or runs into a graphics context.
- **Text.Layout.Line**: A single line in a text layout: a collection of runs of placed glyphs.
- **Text.Layout.Run**: A run of placed glyphs in a text layout.
- **Text.Layout.RunSlice**: A slice of a run of placed glyphs in a text layout.
- **Text.Layout.TypographicBounds**: The typographic bounds of an element in a text layout.

## Instance Properties

- **isTruncated**: Indicates if this text is truncated.

## Conforms To

- BidirectionalCollection
- Collection
- Equatable
- RandomAccessCollection
- Sequence

