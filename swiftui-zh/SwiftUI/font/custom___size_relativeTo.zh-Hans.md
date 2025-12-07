--- 来源：https://developer.apple.com/documentation/SwiftUI/Font/custom(_:size:relativeTo:)

抓取时间：2025-12-03T06:18:03Z

---

# custom(_:size:relativeTo:)

**类型方法**

使用给定的 `name` 和 `size` 创建一个自定义字体，该字体相对于给定的 `textStyle` 进行缩放。

## 声明

```swift
static func custom(_ name: String, size: CGFloat, relativeTo textStyle: Font.TextStyle) -> Font
```

## 创建自定义字体

- **custom(_:fixedSize:)**：使用给定的 `name` 和一个固定的 `size` 创建一个自定义字体，该字体不会随动态字体缩放。

- **custom(_:size:)**：使用给定的 `name` 和 `size` 创建一个自定义字体，使其能够随正文样式缩放。


---
source: https://developer.apple.com/documentation/SwiftUI/Font/custom(_:size:relativeTo:)
crawled: 2025-12-03T06:18:03Z
---

# custom(_:size:relativeTo:)

**Type Method**

Create a custom font with the given `name` and `size` that scales relative to the given `textStyle`.

## Declaration

```swift
static func custom(_ name: String, size: CGFloat, relativeTo textStyle: Font.TextStyle) -> Font
```

## Creating custom fonts

- **custom(_:fixedSize:)**: Create a custom font with the given `name` and a fixed `size` that does not scale with Dynamic Type.
- **custom(_:size:)**: Create a custom font with the given `name` and `size` that scales with the body text style.

