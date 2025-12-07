---
来源： https://developer.apple.com/documentation/swiftui/unitpoint
抓取时间： 2025-12-03T06:35:42Z
---

# 单位点

**Structure**

视图坐标空间中归一化的二维点。

## 声明

```swift
@frozen struct UnitPoint
```

## 概览

使用单位点来表示视图中的某个位置，而无需知道视图的渲染尺寸。单位点会在每个维度中存储一个值，该值表示该点所在维度的尺寸占视图尺寸的比例（从视图原点开始测量）。例如，您可以为每个维度使用`0.5`值来创建一个单位点，代表任何视图的中心：

```swift
let unitPoint = UnitPoint(x: 0.5, y: 0.5)
```

要将单位点投影到渲染视图的坐标空间中，请将单位点的每个分量与视图尺寸的相应分量相乘：

```swift
let projectedPoint = CGPoint(
    x: unitPoint.x * size.width,
    y: unitPoint.y * size.height
)
```

如果您碰巧知道视图的大小，或者想将单位点用于某些自定义用途，您可以自己执行此计算，但 SwiftUI 通常会为您执行您要求的操作，例如当您执行以下操作时：

- 使用形状修改器变换形状。例如，使用 [rotation(_:anchor:)](Shape/rotation___anchor.zh-Hans.md) 旋转形状时，您需要指出一个要围绕其旋转的锚点。
- 使用[Grid](Grid.zh-Hans.md)视图修改器覆盖⟦单元格中视图的对齐方式。网格将单位点在视图上的投影与同一单位点在单元格上的投影对齐。
- 创建一个渐变，渐变的中心点或起点和止点应与您要样式化的形状相对应。请参阅 [ShapeStyle](ShapeStyle.zh-Hans.md) 中的渐变方法。

您可以创建具有明确值的自定义单位点（如上面的示例），也可以使用 SwiftUI 提供的内置单位点，如 [zero](UnitPoint/zero.zh-Hans.md)、[center](UnitPoint/center.zh-Hans.md) 或 [topTrailing](UnitPoint/topTrailing.zh-Hans.md)。内置值对应于名称相似的内置[Alignment](Alignment.zh-Hans.md) 类型的对齐位置。



### 布局方向

当用户将设备配置为使用从左到右的语言（如英语）时，系统会将视图的原点放在左上角，正 x 朝向视图的右边，正 y 朝向视图的底部。在从右到左的环境中，原点会移动到右上角，正 x 方向会变为向左。您通常不需要做任何事情来处理这种变化，因为 SwiftUI 会将这种变化应用到系统的各个方面。例如，请参阅 [HorizontalAlignment](HorizontalAlignment.zh-Hans.md) 中有关布局方向的讨论。

重要的是，要在发布应用程序的不同地区测试应用程序。有关本地化过程的更多信息，请参阅 [doc://com.apple.documentation/documentation/Xcode/localization]。

## 获取原点

- **zero**：视图的原点。

## 获取顶点

- **topLeading**：位于视图顶部前角的点。
- **top**：位于视图顶部边缘水平居中的点。
- **topTrailing**：位于视图顶部尾角的点。

## 获取中间点

- **leading**：位于视图前缘垂直中心的点。
- **center**：在视图中居中的点。
- **trailing**：视图后缘垂直居中的点。

## 获取底部点

- **bottomLeading**：位于视图底部前角的点。
- **bottom**：位于视图底部边缘水平居中的点。
- **bottomTrailing**：位于视图底部尾角的点。

## 创建点

- **init()**：在原点创建一个单位点。
- **init(x:y:)**：以指定的水平偏移和垂直偏移创建单位点。

## 获取点的坐标

- **x**：水平方向上从原点到点的归一化距离。
- **y**：从原点到点在垂直方向上的归一化距离。

## 访问几何结构

- **Axis**：二维坐标系中的水平或垂直维度。
- **Angle**：几何角度，可以用弧度或度表示。
- **UnitPoint3D**：视图坐标空间中的一个归一化 3D 点。
- **Anchor**：从锚点来源和特定视图导出的不透明值。
- **DepthAlignmentID**：从锚点源和特定视图导出的不透明值。
- **Alignment3D**：三个轴都对齐。
- **GeometryProxyCoordinateSpace3D**：`GeometryProxy3D`的表示，可用于基于`CoordinateSpace3D`的转换。

## 符合

- 可动画
- 比特可复制
- 可复制
- 可解码
- 可编码
- 等价
- 可散列
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/swiftui/unitpoint
crawled: 2025-12-03T06:35:42Z
---

# UnitPoint

**Structure**

A normalized 2D point in a view’s coordinate space.

## Declaration

```swift
@frozen struct UnitPoint
```

## Overview

Use a unit point to represent a location in a view without having to know the view’s rendered size. The point stores a value in each dimension that indicates the fraction of the view’s size in that dimension — measured from the view’s origin — where the point appears. For example, you can create a unit point that represents the center of any view by using the value `0.5` for each dimension:

```swift
let unitPoint = UnitPoint(x: 0.5, y: 0.5)
```

To project the unit point into the rendered view’s coordinate space, multiply each component of the unit point with the corresponding component of the view’s size:

```swift
let projectedPoint = CGPoint(
    x: unitPoint.x * size.width,
    y: unitPoint.y * size.height
)
```

You can perform this calculation yourself if you happen to know a view’s size, or if you want to use the unit point for some custom purpose, but SwiftUI typically does this for you to carry out operations that you request, like when you:

- Transform a shape using a shape modifier. For example, to rotate a shape with [rotation(_:anchor:)](Shape/rotation___anchor.zh-Hans.md), you indicate an anchor point that you want to rotate the shape around.
- Override the alignment of the view in a [Grid](Grid.zh-Hans.md) cell using the [gridCellAnchor(_:)](View/gridCellAnchor.zh-Hans.md) view modifier. The grid aligns the projection of a unit point onto the view with the projection of the same unit point onto the cell.
- Create a gradient that has a center, or start and stop points, relative to the shape that you are styling. See the gradient methods in [ShapeStyle](ShapeStyle.zh-Hans.md).

You can create custom unit points with explicit values, like the example above, or you can use one of the built-in unit points that SwiftUI provides, like [zero](UnitPoint/zero.zh-Hans.md), [center](UnitPoint/center.zh-Hans.md), or [topTrailing](UnitPoint/topTrailing.zh-Hans.md). The built-in values correspond to the alignment positions of the similarly named, built-in [Alignment](Alignment.zh-Hans.md) types.



### Layout direction

When a person configures their device to use a left-to-right language like English, the system places the view’s origin in its top-left corner, with positive x toward the right and positive y toward the bottom of the view. In a right-to-left environment, the origin moves to the upper-right corner, and the positive x direction changes to be toward the left. You don’t typically need to do anything to handle this change, because SwiftUI applies the change to all aspects of the system. For example, see the discussion about layout direction in [HorizontalAlignment](HorizontalAlignment.zh-Hans.md).

It’s important to test your app for the different locales that you distribute your app in. For more information about the localization process, see [doc://com.apple.documentation/documentation/Xcode/localization].

## Getting the origin

- **zero**: The origin of a view.

## Getting top points

- **topLeading**: A point that’s in the top, leading corner of a view.
- **top**: A point that’s centered horizontally on the top edge of a view.
- **topTrailing**: A point that’s in the top, trailing corner of a view.

## Getting middle points

- **leading**: A point that’s centered vertically on the leading edge of a view.
- **center**: A point that’s centered in a view.
- **trailing**: A point that’s centered vertically on the trailing edge of a view.

## Getting bottom points

- **bottomLeading**: A point that’s in the bottom, leading corner of a view.
- **bottom**: A point that’s centered horizontally on the bottom edge of a view.
- **bottomTrailing**: A point that’s in the bottom, trailing corner of a view.

## Creating a point

- **init()**: Creates a unit point at the origin.
- **init(x:y:)**: Creates a unit point with the specified horizontal and vertical offsets.

## Getting the point’s coordinates

- **x**: The normalized distance from the origin to the point in the horizontal direction.
- **y**: The normalized distance from the origin to the point in the vertical dimension.

## Accessing geometric constructs

- **Axis**: The horizontal or vertical dimension in a 2D coordinate system.
- **Angle**: A geometric angle whose value you access in either radians or degrees.
- **UnitPoint3D**: A normalized 3D point in a view’s coordinate space.
- **Anchor**: An opaque value derived from an anchor source and a particular view.
- **DepthAlignmentID**
- **Alignment3D**: An alignment in all three axes.
- **GeometryProxyCoordinateSpace3D**: A representation of a `GeometryProxy3D` which can be used for `CoordinateSpace3D` based conversions.

## Conforms To

- Animatable
- BitwiseCopyable
- Copyable
- Decodable
- Encodable
- Equatable
- Hashable
- Sendable
- SendableMetatype

