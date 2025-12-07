--- 来源：https://developer.apple.com/documentation/SwiftUI/View/tipImageStyle(_:_:)

抓取时间：2025-12-02T17:26:11Z

---

# tipImageStyle(_:_:)

**实例方法**

设置提示图像的样式。

## 声明

```swift
nonisolated func tipImageStyle<S1, S2>(_ primary: S1, _ secondary: S2) -> some View where S1 : ShapeStyle, S2 : ShapeStyle

```

## 提供提示

- **popoverTip(_:arrowEdge:action:)**：在修改后的视图上显示弹出式提示。

- **tipBackground(_:)**：设置提示视图的背景样式。目前仅适用于内联提示，不适用于弹出式提示。

- **tipCornerRadius(_:antialiased:)**：设置内联提示视图的圆角半径。

- **tipImageSize(_:)**：设置提示图片的尺寸。

- **tipViewStyle(_:)**：设置提示视图在视图层级结构中的样式。

- **tipImageStyle(_:)**：设置提示图片的样式。

- **tipImageStyle(_:_:_:)**：设置提示图片的样式。


---
source: https://developer.apple.com/documentation/SwiftUI/View/tipImageStyle(_:_:)
crawled: 2025-12-02T17:26:11Z
---

# tipImageStyle(_:_:)

**Instance Method**

Sets the style for a tip’s image.

## Declaration

```swift
nonisolated func tipImageStyle<S1, S2>(_ primary: S1, _ secondary: S2) -> some View where S1 : ShapeStyle, S2 : ShapeStyle

```

## Providing tips

- **popoverTip(_:arrowEdge:action:)**: Presents a popover tip on the modified view.
- **tipBackground(_:)**: Sets the tip’s view background to a style. Currently this only applies to inline tips, not popover tips.
- **tipCornerRadius(_:antialiased:)**: Sets the corner radius for an inline tip view.
- **tipImageSize(_:)**: Sets the size for a tip’s image.
- **tipViewStyle(_:)**: Sets the given style for TipView within the view hierarchy.
- **tipImageStyle(_:)**: Sets the style for a tip’s image.
- **tipImageStyle(_:_:_:)**: Sets the style for a tip’s image.

