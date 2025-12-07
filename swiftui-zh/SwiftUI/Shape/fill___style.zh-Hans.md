---
来源：https://developer.apple.com/documentation/SwiftUI/Shape/fill(_:style:)
抓取时间： 2025-12-02T21:41:57Z
---

# fill(_:style:)

**实例方法**

用颜色或渐变填充此形状。

## 声明

```swift
nonisolated func fill<S>(_ content: S = .foreground, style: FillStyle = FillStyle()) -> _ShapeView<Self, S> where S : ShapeStyle
```

## 参数

- **content**：填充此形状时要使用的颜色或梯度。
- **style**：决定填充渲染方式的样式选项。

## 返回值

一个用你提供的颜色或渐变填充的形状。

## 填充形状

- **fill(style:)**：用前景色填充该形状。


---
source: https://developer.apple.com/documentation/SwiftUI/Shape/fill(_:style:)
crawled: 2025-12-02T21:41:57Z
---

# fill(_:style:)

**Instance Method**

Fills this shape with a color or gradient.

## Declaration

```swift
nonisolated func fill<S>(_ content: S = .foreground, style: FillStyle = FillStyle()) -> _ShapeView<Self, S> where S : ShapeStyle
```

## Parameters

- **content**: The color or gradient to use when filling this shape.
- **style**: The style options that determine how the fill renders.

## Return Value

A shape filled with the color or gradient you supply.

## Filling a shape

- **fill(style:)**: Fills this shape with the foreground color.

