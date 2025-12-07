--- 来源：https://developer.apple.com/documentation/SwiftUI/Font/custom(_:size:)

抓取时间：2025-12-01T11:07:10Z

---

# custom(_:size:)

**类型方法**

使用给定的 `name` 和 `size` 创建一个自定义字体，该字体会随正文文本样式缩放。

## 声明

```swift
static func custom(_ name: String, size: CGFloat) -> Font
```

## 创建自定义字体

- **custom(_:fixedSize:)**：使用给定的 `name` 和一个固定的 `size` 创建一个自定义字体，该字体不会随动态字体缩放。

- **custom(_:size:relativeTo:)**：使用给定的 `name` 和 `size` 创建一个自定义字体，使其相对于给定的 `textStyle` 进行缩放。


---
source: https://developer.apple.com/documentation/SwiftUI/Font/custom(_:size:)
crawled: 2025-12-01T11:07:10Z
---

# custom(_:size:)

**Type Method**

Create a custom font with the given `name` and `size` that scales with the body text style.

## Declaration

```swift
static func custom(_ name: String, size: CGFloat) -> Font
```

## Creating custom fonts

- **custom(_:fixedSize:)**: Create a custom font with the given `name` and a fixed `size` that does not scale with Dynamic Type.
- **custom(_:size:relativeTo:)**: Create a custom font with the given `name` and `size` that scales relative to the given `textStyle`.

