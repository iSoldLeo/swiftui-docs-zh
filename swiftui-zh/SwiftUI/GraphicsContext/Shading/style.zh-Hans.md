---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/Shading/style(_:)
抓取时间： 2025-12-03T17:19:47Z
---

# style(_:)

**类型方法**

返回使用给定形状样式填充的阴影实例。

## 声明

```swift
static func style<S>(_ style: S) -> GraphicsContext.Shading where S : ShapeStyle
```

## 参数

- **style**：要使用的[ShapeStyle](../../ShapeStyle.zh-Hans.md) 实例。

## 返回值

填充了形状样式的阴影实例。

## 讨论

在单位坐标空间中定义了几何体的样式会将该空间映射到与绘制对象相关的矩形中。您可以使用[in(_:)](../../ShapeStyle/in.zh-Hans.md) 方法对其进行调整。形状样式可能会影响绘制对象的混合模式和不透明度。

## 其他形状样式

- **foreground**：使用图形上下文环境中的前景样式填充的着色实例。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/Shading/style(_:)
crawled: 2025-12-03T17:19:47Z
---

# style(_:)

**Type Method**

Returns a shading instance that fills with the given shape style.

## Declaration

```swift
static func style<S>(_ style: S) -> GraphicsContext.Shading where S : ShapeStyle
```

## Parameters

- **style**: A [ShapeStyle](../../ShapeStyle.zh-Hans.md) instance to draw with.

## Return Value

A shading instance filled with a shape style.

## Discussion

Styles with geometry defined in a unit coordinate space map that space to the rectangle associated with the drawn object. You can adjust that using the [in(_:)](../../ShapeStyle/in.zh-Hans.md) method. The shape style might affect the blend mode and opacity of the drawn object.

## Other shape styles

- **foreground**: A shading instance that fills with the foreground style from the graphics context’s environment.

