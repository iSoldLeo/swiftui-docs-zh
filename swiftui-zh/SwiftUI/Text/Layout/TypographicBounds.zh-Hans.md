--- 来源：https://developer.apple.com/documentation/SwiftUI/Text/Layout/TypographicBounds

抓取时间：2025-12-03T19:59:35Z

---

# Text.Layout.TypographicBounds

**Structure**

文本布局中元素的排版边界。

## 声明

```swift
@frozen struct TypographicBounds
```

## 初始化

- **init()**：初始化为空边界，原点为零。

## 实例属性

- **ascent**：元素的上升高度。

- **descent**：元素的下降高度。

- **leading**：元素的起始高度。

- **origin**：元素基线左边缘相对于文本视图的位置。

- **rect**：返回一个包含边界的矩形。

- **width**：元素的宽度。

## 符合以下规范

- BitwiseCopyable

- Copyable

- Equatable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/Text/Layout/TypographicBounds
crawled: 2025-12-03T19:59:35Z
---

# Text.Layout.TypographicBounds

**Structure**

The typographic bounds of an element in a text layout.

## Declaration

```swift
@frozen struct TypographicBounds
```

## Initializers

- **init()**: Initializes to an empty bounds with zero origin.

## Instance Properties

- **ascent**: The ascent of the element.
- **descent**: The descent of the element.
- **leading**: The leading of the element.
- **origin**: The position of the left edge of the element’s baseline, relative to the text view.
- **rect**: Returns a rectangle encapsulating the bounds.
- **width**: The width of the element.

## Conforms To

- BitwiseCopyable
- Copyable
- Equatable
- Sendable
- SendableMetatype

