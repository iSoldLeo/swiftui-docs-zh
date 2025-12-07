---
来源： https://developer.apple.com/documentation/swiftui/alignment3d
抓取时间： 2025-12-03T06:35:44Z
---

# Alignment3D

**Structure**

三轴对齐。

## 声明

```swift
@frozen struct Alignment3D
```

## Initializers

- **init(horizontal:vertical:depth:)**：使用指定的水平、垂直和深度对齐导线创建自定义对齐值。

## 实例属性

- **depth**：深度轴上的对齐方式。
- **horizontal**：水平轴上的对齐方式。
- **vertical**：垂直轴上的对齐方式。

### 类型属性

- **back**：代表水平轴中心、垂直轴中心和深度轴背面的一个点的向导。
- **bottom**：代表水平轴中心、垂直轴底部和深度轴中心点的导线。
- **bottomBack**：代表位于水平轴中心、垂直轴底部和深度轴背面的点的导线。
- **bottomFront**：代表水平轴中心、垂直轴底部和深度轴前端的点的导线。
- **bottomLeading**：代表水平轴前缘、垂直轴底部和深度轴中心点的导线。
- **bottomLeadingBack**：代表水平轴前缘、垂直轴底部和深度轴后部的一个点的导线。
- **bottomLeadingFront**：代表水平轴前缘、垂直轴底部和深度轴前端的一个点的导线。
- **bottomTrailing**：代表水平轴后缘、垂直轴底部和深度轴中心点的导线。
- **bottomTrailingBack**：代表水平轴后缘、垂直轴底部和深度轴后部的一个点的导线。
- **bottomTrailingFront**：代表水平轴后缘、垂直轴底部和深度轴前端的一个点的导线。
- **center**：表示水平轴中心、垂直轴中心和深度轴中心点的导线。
- **front**：代表位于水平轴中心、垂直轴中心和深度轴前端的点的导线。
- **leading**：代表水平轴前缘、垂直轴中心和深度轴中心点的导线。
- **leadingBack**：代表水平轴前缘、垂直轴中心和深度轴后部的一个点的导线。
- **leadingFront**：代表水平轴前缘、垂直轴中心和深度轴前端的点的导线。
- **top**：代表水平轴中心、垂直轴顶端和深度轴中心点的导线。
- **topBack**：代表水平轴中心、垂直轴顶端和深度轴背面的一个点的导线。
- **topFront**：代表水平轴中心、垂直轴顶端和深度轴前端的一个点的导线。
- **topLeading**：代表水平轴中心、垂直轴顶端和深度轴中心点的导线。
- **topLeadingBack**：代表水平轴前缘、垂直轴顶部和深度轴后部的一个点的导线。
- **topLeadingFront**：代表水平轴前缘、垂直轴顶端和深度轴前端的点的导线。
- **topTrailing**：代表水平轴后缘、垂直轴顶端和深度轴中心点的导线。
- **topTrailingBack**：代表水平轴后缘、垂直轴顶部和深度轴后部的一个点的导线。
- **topTrailingFront**：代表水平轴后缘、垂直轴顶端和深度轴前端的一个点的导线。
- **trailing**：代表水平轴后缘、垂直轴中心和深度轴中心点的导线。
- **trailingBack**：代表水平轴后缘、垂直轴中心和深度轴后部的一个点的导线。
- **trailingFront**：代表水平轴后缘、垂直轴中心和深度轴前端的点的导轨。

## 访问几何结构体

- **Axis**：二维坐标系中的水平或垂直尺寸。
- **Angle**：几何角度，可以用弧度或度表示。
- **UnitPoint**：视图坐标空间中的一个归一化二维点。
- **UnitPoint3D**：视图坐标空间中的一个归一化 3D 点。
- **Anchor**：从锚点来源和特定视图导出的不透明值。
- **DepthAlignmentID**：从锚点源和特定视图导出的不透明值。
- **GeometryProxyCoordinateSpace3D**：`GeometryProxy3D`的表示，可用于基于`CoordinateSpace3D`的转换。

## 符合

- 等价
- 可发送
- 可发送元数据类型


---
source: https://developer.apple.com/documentation/swiftui/alignment3d
crawled: 2025-12-03T06:35:44Z
---

# Alignment3D

**Structure**

An alignment in all three axes.

## Declaration

```swift
@frozen struct Alignment3D
```

## Initializers

- **init(horizontal:vertical:depth:)**: Creates a custom alignment value with the specified horizontal, vertical and depth alignment guides.

## Instance Properties

- **depth**: The alignment on the depth axis.
- **horizontal**: The alignment on the horizontal axis.
- **vertical**: The alignment on the vertical axis.

## Type Properties

- **back**: A guide representing a point at the center of the horizontal axis, center of the vertical axis, and back of the depth axis.
- **bottom**: A guide representing a point at the center of the horizontal axis, bottom of the vertical axis, and center of the depth axis.
- **bottomBack**: A guide representing a point at the center of the horizontal axis, bottom of the vertical axis, and back of the depth axis.
- **bottomFront**: A guide representing a point at the center of the horizontal axis, bottom of the vertical axis, and front of the depth axis.
- **bottomLeading**: A guide representing a point at the leading edge of the horizontal axis, bottom of the vertical axis, and center of the depth axis.
- **bottomLeadingBack**: A guide representing a point at the leading edge of the horizontal axis, bottom of the vertical axis, and back of the depth axis.
- **bottomLeadingFront**: A guide representing a point at the leading edge of the horizontal axis, bottom of the vertical axis, and front of the depth axis.
- **bottomTrailing**: A guide representing a point at the trailing edge of the horizontal axis, bottom of the vertical axis, and center of the depth axis.
- **bottomTrailingBack**: A guide representing a point at the trailing edge of the horizontal axis, bottom of the vertical axis, and back of the depth axis.
- **bottomTrailingFront**: A guide representing a point at the trailing edge of the horizontal axis, bottom of the vertical axis, and front of the depth axis.
- **center**: A guide representing a point at the center of the horizontal axis, center of the vertical axis, and center of the depth axis.
- **front**: A guide representing a point at the center of the horizontal axis, center of the vertical axis, and front of the depth axis.
- **leading**: A guide representing a point at the leading edge of the horizontal axis, center of the vertical axis, and center of the depth axis.
- **leadingBack**: A guide representing a point at the leading edge of the horizontal axis, center of the vertical axis, and back of the depth axis.
- **leadingFront**: A guide representing a point at the leading edge of the horizontal axis, center of the vertical axis, and front of the depth axis.
- **top**: A guide representing a point at the center of the horizontal axis, top of the vertical axis, and center of the depth axis.
- **topBack**: A guide representing a point at the center of the horizontal axis, top of the vertical axis, and back of the depth axis.
- **topFront**: A guide representing a point at the center of the horizontal axis, top of the vertical axis, and front of the depth axis.
- **topLeading**: A guide representing a point at the center of the horizontal axis, top of the vertical axis, and center of the depth axis.
- **topLeadingBack**: A guide representing a point at the leading edge of the horizontal axis, top of the vertical axis, and back of the depth axis.
- **topLeadingFront**: A guide representing a point at the leading edge of the horizontal axis, top of the vertical axis, and front of the depth axis.
- **topTrailing**: A guide representing a point at the trailing edge of the horizontal axis, top of the vertical axis, and center of the depth axis.
- **topTrailingBack**: A guide representing a point at the trailing edge of the horizontal axis, top of the vertical axis, and back of the depth axis.
- **topTrailingFront**: A guide representing a point at the trailing edge of the horizontal axis, top of the vertical axis, and front of the depth axis.
- **trailing**: A guide representing a point at the trailing edge of the horizontal axis, center of the vertical axis, and center of the depth axis.
- **trailingBack**: A guide representing a point at the trailing edge of the horizontal axis, center of the vertical axis, and back of the depth axis.
- **trailingFront**: A guide representing a point at the trailing edge of the horizontal axis, center of the vertical axis, and front of the depth axis.

## Accessing geometric constructs

- **Axis**: The horizontal or vertical dimension in a 2D coordinate system.
- **Angle**: A geometric angle whose value you access in either radians or degrees.
- **UnitPoint**: A normalized 2D point in a view’s coordinate space.
- **UnitPoint3D**: A normalized 3D point in a view’s coordinate space.
- **Anchor**: An opaque value derived from an anchor source and a particular view.
- **DepthAlignmentID**
- **GeometryProxyCoordinateSpace3D**: A representation of a `GeometryProxy3D` which can be used for `CoordinateSpace3D` based conversions.

## Conforms To

- Equatable
- Sendable
- SendableMetatype

