--- 来源：https://developer.apple.com/documentation/SwiftUI/View/fontWeight(_:)

抓取时间：2025-12-02T17:34:42Z

---

# fontWeight(_:)

**实例方法**

设置此视图中文本的字体粗细。

## 声明

```swift
nonisolated func fontWeight(_ weight: Font.Weight?) -> some View

```

## 参数

- **weight**：可用的字体粗细之一。提供 `nil` 将移除视图层级中更高层应用的任何字体粗细修饰符的效果。

## 返回值

使用您指定的字体粗细的视图。

## 设置字体

- **将自定义字体应用于文本**：在您的应用中添加并使用可随动态类型缩放的字体。

- **font(_:)**：设置此视图中文本的默认字体。

- **fontDesign(_:)**：设置此视图中文本的字体样式。

- **fontWidth(_:)**：设置此视图中文本的字体宽度。

- **font**：此环境的默认字体。

- **Font**：与环境相关的字体。


---
source: https://developer.apple.com/documentation/SwiftUI/View/fontWeight(_:)
crawled: 2025-12-02T17:34:42Z
---

# fontWeight(_:)

**Instance Method**

Sets the font weight of the text in this view.

## Declaration

```swift
nonisolated func fontWeight(_ weight: Font.Weight?) -> some View

```

## Parameters

- **weight**: One of the available font weights. Providing `nil` removes the effect of any font weight modifier applied higher in the view hierarchy.

## Return Value

A view that uses the font weight you specify.

## Setting a font

- **Applying custom fonts to text**: Add and use a font in your app that scales with Dynamic Type.
- **font(_:)**: Sets the default font for text in this view.
- **fontDesign(_:)**: Sets the font design of the text in this view.
- **fontWidth(_:)**: Sets the font width of the text in this view.
- **font**: The default font of this environment.
- **Font**: An environment-dependent font.

