--- 来源：https://developer.apple.com/documentation/swiftui/unitpoint3d
抓取时间：2025-12-03T06:35:43Z

---

# UnitPoint3D

**Structure**

视图坐标空间中的归一化三维点。

## 声明

```swift
@frozen struct UnitPoint3D
```

## 概述

使用三维单位点可以在视图中表示三维位置，而无需知道视图的渲染大小。该点在每个维度上存储一个值，该值指示该点在视图该维度上的大小占视图大小的比例（从视图原点测量）。例如，您可以使用每个维度的值 `0.5` 创建一个表示任意视图中心的单位点：

```swift
let unitPoint = UnitPoint3D(x: 0.5, y: 0.5, z: 0.5)
```

要将单位点投影到渲染视图的坐标空间，请将单位点的每个分量乘以视图尺寸的对应分量：

```swift
let projectedPoint = Point3D(
    x: unitPoint.x * size.width,
    y: unitPoint.y * size.height,
    z: unitPoint.z * size.depth
)
```

如果您知道视图的尺寸，或者想将单位点用于某些自定义用途，则可以自行计算。但 SwiftUI 通常会为您执行此操作，例如，当您使用 [rotation3DEffect(_:anchor:)](View/rotation3DEffect___anchor.zh-Hans.md) 修饰符旋转视图并指定要围绕其旋转的锚点时。

您可以创建具有明确值的自定义单位点，如上例所示，也可以使用 SwiftUI 提供的内置单位点，例如 [zero](UnitPoint3D/zero.zh-Hans.md)、[center](UnitPoint3D/center.zh-Hans.md) 或 [topTrailing](UnitPoint3D/topTrailing.zh-Hans.md)。这些内置值对应于您可能需要引用的常用锚点，例如视图边缘的中心。

### 布局方向

当用户将设备配置为使用从左到右的语言（例如英语）时，系统会将视图的原点放置在左上角，x 轴正方向指向右侧，y 轴正方向指向底部，z 轴正方向指向前方。在从右到左的环境中，原点会移动到右上角，x 轴正方向会变为指向左侧。通常情况下，您无需进行任何操作来处理此更改，因为 SwiftUI 会将此更改应用于系统的所有方面。例如，请参阅 [HorizontalAlignment](HorizontalAlignment.zh-Hans.md) 中关于布局方向的讨论。

务必针对您发布应用的不同语言环境测试您的应用。有关本地化流程的更多信息，请参阅 [doc://com.apple.documentation/documentation/Xcode/localization]。

## 获取原点

- **origin**：视图的原点。

- **zero**：所有分量均为零的 3D 单位点。

## 获取顶点

- **topLeadingBack**：位于视图顶部后角的点。

- **topLeading**：位于视图顶部边缘深度方向中心的点。

- **topLeadingFront**：视图顶部前角处的点。

- **topBack**：视图顶部后边缘水平居中的点。

- **top**：视图顶面深度方向上水平居中的点。

- **topFront**：视图顶部前边缘水平居中的点。

- **topTrailingBack**：视图顶部后角处的点。

- **topTrailing**：视图顶部后边缘深度方向上居中的点。

- **topTrailingFront**：视图顶部后沿前角的点。

## 获取中心点

- **leadingBack**：视图前沿后边缘垂直居中的点。

- **leading**：视图前表面垂直居中且位于深度方向上的点。

- **leadingFront**：视图前沿前边缘垂直居中的点。

- **back**：视图后表面水平和垂直居中的点。

- **center**：视图中心点。

- **front**：视图前表面水平和垂直中心点。

- **trailingBack**：视图后边缘垂直中心点。

- **trailing**：视图后表面垂直和深度中心点。

- **trailingFront**：视图后边缘垂直中心点。

## 获取底部点

- **bottomLeadingBack**：视图后下角中心点。

- **bottomLeading**：视图前下边缘深度中心点。

- **bottomLeadingFront**：视图底部前角处的点。

- **bottomBack**：视图底部后缘水平中心处的点。

- **bottom**：视图底面深度方向上水平中心处的点。

- **bottomFront**：视图底部前缘水平中心处的点。

- **bottomTrailingBack**：视图底部后角处的点。

- **bottomTrailing**：视图底部后缘深度方向上中心处的点。

- **bottomTrailingFront**：视图底部后方角落的点。

## 创建点

- **init()**：在原点创建三维单位点。

- **init(x:y:z:)**：创建具有指定偏移量的三维单位点。

## 获取点的坐标

- **x**：从原点到该点的水平归一化距离。

- **y**：从原点到该点的垂直归一化距离。

- **z**：从原点到该点的深度归一化距离。

## 访问几何构造

- **Axis**：二维坐标系中的水平或垂直维度。

- **Angle**：几何角度，其值可以以弧度或角度访问。

- **UnitPoint**：视图坐标空间中的归一化二维点。

- **Anchor**：从锚点源和特定视图派生的不透明值。

- **DepthAlignmentID**

- **Alignment3D**：所有三个轴上的对齐方式。

- **GeometryProxyCoordinateSpace3D**：`GeometryProxy3D` 的表示形式，可用于基于 `CoordinateSpace3D` 的转换。

## 符合以下规范

- 可动画化

- 可按位复制

- 可复制

- 可解码

- 可编码

- 可等值化

- 可哈希化

- 可发送

- 可发送元数据


---
source: https://developer.apple.com/documentation/swiftui/unitpoint3d
crawled: 2025-12-03T06:35:43Z
---

# UnitPoint3D

**Structure**

A normalized 3D point in a view’s coordinate space.

## Declaration

```swift
@frozen struct UnitPoint3D
```

## Overview

Use a 3D unit point to represent a three-dimensional location in a view without having to know the view’s rendered size. The point stores a value in each dimension that indicates the fraction of the view’s size in that dimension — measured from the view’s origin — where the point appears. For example, you can create a unit point that represents the center of any view by using the value `0.5` for each dimension:

```swift
let unitPoint = UnitPoint3D(x: 0.5, y: 0.5, z: 0.5)
```



To project the unit point into the rendered view’s coordinate space, multiply each component of the unit point with the corresponding component of the view’s size:

```swift
let projectedPoint = Point3D(
    x: unitPoint.x * size.width,
    y: unitPoint.y * size.height,
    z: unitPoint.z * size.depth
)
```

You can perform this calculation yourself if you happen to know a view’s size, or if you want to use a unit point for some custom purpose, but SwiftUI typically does this for you to carry out operations that you request, like when you rotate a view with the [rotation3DEffect(_:anchor:)](View/rotation3DEffect___anchor.zh-Hans.md) modifier and indicate the anchor point that you want to rotate the view around.

You can create custom unit points with explicit values, like the example above, or you can use one of the built-in unit points that SwiftUI provides, like [zero](UnitPoint3D/zero.zh-Hans.md), [center](UnitPoint3D/center.zh-Hans.md), or [topTrailing](UnitPoint3D/topTrailing.zh-Hans.md). The built-in values correspond to common anchor points that you might want to refer to, like the center of one of a view’s edges.



### Layout direction

When a person configures their device to use a left-to-right language like English, the system places the view’s origin in its top-left-back corner, with positive x toward the right, positive y toward the bottom of the view, and positive z toward the front. In a right-to-left environment, the origin moves to the upper-right-back corner, and the positive x direction changes to be toward the left. You don’t typically need to do anything to handle this change, because SwiftUI applies the change to all aspects of the system. For example, see the discussion about layout direction in [HorizontalAlignment](HorizontalAlignment.zh-Hans.md).

It’s important to test your app for the different locales that you distribute your app in. For more information about the localization process, see [doc://com.apple.documentation/documentation/Xcode/localization].

## Getting the origin

- **origin**: The origin of a view.
- **zero**: A 3D unit point with all components equal to zero.

## Getting top points

- **topLeadingBack**: A point that’s in the top-leading-back corner of a view.
- **topLeading**: A point that’s centered in the depth dimension on the top-leading edge of a view.
- **topLeadingFront**: A point that’s in the top-leading-front corner of a view.
- **topBack**: A point that’s centered horizontally on the top-back edge of a view.
- **top**: A point that’s centered horizontally and in the depth dimension on the top face of a view.
- **topFront**: A point that’s centered horizontally on the top-front edge of a view.
- **topTrailingBack**: A point that’s in the top-trailing-back corner of a view.
- **topTrailing**: A point that’s centered in the depth dimension on the top-trailing edge of a view.
- **topTrailingFront**: A point that’s in the top-trailing-front corner of a view.

## Getting middle points

- **leadingBack**: A point that’s centered vertically on the leading-back edge of a view.
- **leading**: A point that’s centered vertically and in the depth dimension on the leading face of a view.
- **leadingFront**: A point that’s centered vertically on the leading-front edge of a view.
- **back**: A point that’s centered horizontally and vertically on the back face of a view.
- **center**: A point that’s centered in a view.
- **front**: A point that’s centered horizontally and vertically on the front face of a view.
- **trailingBack**: A point that’s centered vertically on the trailing-back edge of a view.
- **trailing**: A point that’s centered vertically and in the depth dimension on the trailing face of a view.
- **trailingFront**: A point that’s centered vertically on the trailing-front edge of a view.

## Getting bottom points

- **bottomLeadingBack**: A point that’s in the bottom-leading-back corner of a view.
- **bottomLeading**: A point that’s centered in the depth dimension on the bottom-leading edge of a view.
- **bottomLeadingFront**: A point that’s in the bottom-leading-front corner of a view.
- **bottomBack**: A point that’s centered horizontally on the bottom-back edge of a view.
- **bottom**: A point that’s centered horizontally and in the depth dimension on the bottom face of a view.
- **bottomFront**: A point that’s centered horizontally on the bottom-front edge of a view.
- **bottomTrailingBack**: A point that’s in the bottom-trailing-back corner of a view.
- **bottomTrailing**: A point that’s centered in the depth dimension on the bottom-trailing edge of a view.
- **bottomTrailingFront**: A point that’s in the bottom-trailing-front corner of a view.

## Creating a point

- **init()**: Creates a 3D unit point at the origin.
- **init(x:y:z:)**: Creates a 3D unit point with the specified offsets.

## Getting the point’s coordinates

- **x**: The normalized distance from the origin to the point in the horizontal direction.
- **y**: The normalized distance from the origin to the point in the vertical dimension.
- **z**: The normalized distance from the origin to the point in the depth dimension.

## Accessing geometric constructs

- **Axis**: The horizontal or vertical dimension in a 2D coordinate system.
- **Angle**: A geometric angle whose value you access in either radians or degrees.
- **UnitPoint**: A normalized 2D point in a view’s coordinate space.
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

