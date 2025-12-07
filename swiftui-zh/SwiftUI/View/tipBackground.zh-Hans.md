--- 来源：https://developer.apple.com/documentation/SwiftUI/View/tipBackground(_:)

抓取时间：2025-11-30T21:11:14Z

---

# tipBackground(_:)

**实例方法**

将提示框的背景设置为指定样式。目前仅适用于内联提示框，不适用于弹出式提示框。

## 声明

```swift
nonisolated func tipBackground<S>(_ style: S) -> some View where S : ShapeStyle

```

## 参数

- **style**：符合 `ShapeStyle` 规范的 SwiftUI 对象实例，用于在修改后的视图后绘制背景。

## 返回值

一个应用指定样式绘制的视图。

## 提供提示

- **popoverTip(_:arrowEdge:action:)**：在修改后的视图上显示弹出式提示框。

- **tipCornerRadius(_:antialiased:)**：设置内联提示视图的圆角半径。

- **tipImageSize(_:)**：设置提示图像的大小。

- **tipViewStyle(_:)**：设置视图层级中提示视图的样式。

- **tipImageStyle(_:)**：设置提示图像的样式。

- **tipImageStyle(_:_:)**：设置提示图像的样式。

- **tipImageStyle(_:_:_:)**：设置提示图像的样式。


---
source: https://developer.apple.com/documentation/SwiftUI/View/tipBackground(_:)
crawled: 2025-11-30T21:11:14Z
---

# tipBackground(_:)

**Instance Method**

Sets the tip’s view background to a style. Currently this only applies to inline tips, not popover tips.

## Declaration

```swift
nonisolated func tipBackground<S>(_ style: S) -> some View where S : ShapeStyle

```

## Parameters

- **style**: An instance of a type that conforms to `ShapeStyle` that SwiftUI draws behind the modified view.

## Return Value

A view with the specified style drawn behind it.

## Providing tips

- **popoverTip(_:arrowEdge:action:)**: Presents a popover tip on the modified view.
- **tipCornerRadius(_:antialiased:)**: Sets the corner radius for an inline tip view.
- **tipImageSize(_:)**: Sets the size for a tip’s image.
- **tipViewStyle(_:)**: Sets the given style for TipView within the view hierarchy.
- **tipImageStyle(_:)**: Sets the style for a tip’s image.
- **tipImageStyle(_:_:)**: Sets the style for a tip’s image.
- **tipImageStyle(_:_:_:)**: Sets the style for a tip’s image.

