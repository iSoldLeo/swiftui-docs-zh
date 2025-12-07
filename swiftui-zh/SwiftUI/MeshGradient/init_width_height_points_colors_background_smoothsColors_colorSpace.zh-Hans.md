--- 来源：https://developer.apple.com/documentation/SwiftUI/MeshGradient/init(width:height:points:colors:background:smoothsColors:colorSpace:)

抓取时间：2025-12-03T05:43:01Z

---

# init(width:height:points:colors:background:smoothsColors:colorSpace:)

**Initializer**

创建一个新的渐变网格，指定为由彩色点组成的二维网格。

## 声明

```swift
init(width: Int, height: Int, points: [SIMD2<Float>], colors: [Color], background: Color = .clear, smoothsColors: Bool = true, colorSpace: Gradient.ColorSpace = .device)
```

## 参数

- **width**：网格的宽度，即每行的顶点数。

- **height**：网格高度，即每列的顶点数。

- **points**：点数组，包含 `width x height` 个元素。

- **colors**：颜色数组，包含 `width x height` 个元素。

- **background**：背景色，用于填充定义顶点网格之外的所有点。

- **smoothsColors**：是否对网格颜色（而不仅仅是网格形状）使用三次（平滑）插值。

- **colorSpace**：用于插值顶点颜色的颜色空间。


---
source: https://developer.apple.com/documentation/SwiftUI/MeshGradient/init(width:height:points:colors:background:smoothsColors:colorSpace:)
crawled: 2025-12-03T05:43:01Z
---

# init(width:height:points:colors:background:smoothsColors:colorSpace:)

**Initializer**

Creates a new gradient mesh specified as a 2D grid of colored points.

## Declaration

```swift
init(width: Int, height: Int, points: [SIMD2<Float>], colors: [Color], background: Color = .clear, smoothsColors: Bool = true, colorSpace: Gradient.ColorSpace = .device)
```

## Parameters

- **width**: The width of the mesh, i.e. the number of vertices per row.
- **height**: The height of the mesh, i.e. the number of vertices per column.
- **points**: The array of points, containing `width x height` elements.
- **colors**: The array of colors, containing `width x height` elements.
- **background**: The background color, this fills any points outside the defined vertex mesh.
- **smoothsColors**: Whether cubic (smooth) interpolation should be used for the colors in the mesh (rather than only for the shape of the mesh).
- **colorSpace**: The color space in which to interpolate vertex colors.

