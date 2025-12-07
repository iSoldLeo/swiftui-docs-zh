--- 来源：https://developer.apple.com/documentation/SwiftUI/View/fontDesign(_:)

抓取时间：2025-12-02T17:34:41Z

---

# fontDesign(_:)

**实例方法**

设置此视图中文本的字体样式。

## 声明

```swift
nonisolated func fontDesign(_ design: Font.Design?) -> some View

```

## 参数

- **design**：可用的字体样式之一。提供 `nil` 将移除视图层级结构中更高层级应用的任何字体样式修饰符的效果。

## 返回值

使用您指定的字体样式的视图。

## 设置字体

- **将自定义字体应用于文本**：在您的应用中添加并使用可随动态类型缩放的字体。

- **font(_:)**：设置此视图中文本的默认字体。

- **fontWeight(_:)**：设置此视图中文本的字重。

- **fontWidth(_:)**：设置此视图中文本的字宽。

- **font**：此环境的默认字体。

- **Font**：与环境相关的字体。


---
source: https://developer.apple.com/documentation/SwiftUI/View/fontDesign(_:)
crawled: 2025-12-02T17:34:41Z
---

# fontDesign(_:)

**Instance Method**

Sets the font design of the text in this view.

## Declaration

```swift
nonisolated func fontDesign(_ design: Font.Design?) -> some View

```

## Parameters

- **design**: One of the available font designs. Providing `nil` removes the effect of any font design modifier applied higher in the view hierarchy.

## Return Value

A view that uses the font design you specify.

## Setting a font

- **Applying custom fonts to text**: Add and use a font in your app that scales with Dynamic Type.
- **font(_:)**: Sets the default font for text in this view.
- **fontWeight(_:)**: Sets the font weight of the text in this view.
- **fontWidth(_:)**: Sets the font width of the text in this view.
- **font**: The default font of this environment.
- **Font**: An environment-dependent font.

