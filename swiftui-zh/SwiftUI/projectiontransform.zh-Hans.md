---
来源： https://developer.apple.com/documentation/swiftui/projectiontransform
抓取时间： 2025-12-04T13:24:35Z
---

# ProjectionTransform | 苹果开发者文档

- [ SwiftUI ](/documentation/swiftui)

- [ 投影变换 ](/documentation/swiftui/projectiontransform)

- 投影变换

结构# ProjectionTransform

iOS 13.0+iPadOS 13.0+Mac Catalyst 13.0+macOS 10.15+tvOS 13.0+visionOS 1.0+watchOS 6.0+

```
@frozen
struct ProjectionTransform
```

## [主题](/documentation/swiftui/projectiontransform#topics)

### [创建转换](/documentation/swiftui/projectiontransform#Creating-a-transform)

[`init()`](/documentation/swiftui/projectiontransform/init())[`init(_:)`](/documentation/swiftui/projectiontransform/init(_:))### [Getting transform characteristics](/documentation/swiftui/projectiontransform#Getting-transform-characteristics)

[`var isAffine: Bool`](/documentation/swiftui/projectiontransform/isaffine)[`var isIdentity: Bool`](/documentation/swiftui/projectiontransform/isidentity)### [Manipulating transforms](/documentation/swiftui/projectiontransform#Manipulating-transforms)

[`func invert() -> Bool`](/documentation/swiftui/projectiontransform/invert())[`func inverted() -> ProjectionTransform`](/documentation/swiftui/projectiontransform/inverted())[`func concatenating(ProjectionTransform) -> ProjectionTransform`](/documentation/swiftui/projectiontransform/concatenating(_:))### [Accessing the transform’s coefficients](/documentation/swiftui/projectiontransform#Accessing-the-transforms-coefficients)

[`var m11: CGFloat`](/documentation/swiftui/projectiontransform/m11)[`var m12: CGFloat`](/documentation/swiftui/projectiontransform/m12)[`var m13: CGFloat`](/documentation/swiftui/projectiontransform/m13)[`var m21: CGFloat`](/documentation/swiftui/projectiontransform/m21)[`var m22: CGFloat`](/documentation/swiftui/projectiontransform/m22)[`var m23: CGFloat`](/documentation/swiftui/projectiontransform/m23)[`var m31: CGFloat`](/documentation/swiftui/projectiontransform/m31)[`var m32: CGFloat`](/documentation/swiftui/projectiontransform/m32)[`var m33: CGFloat`](/documentation/swiftui/projectiontransform/m33)##[关系](/documentation/swiftui/projectiontransform#relationships)

### [Conforms To](/documentation/swiftui/projectiontransform#conforms-to)

- [⟦ic_0021⟧](⟦lu_0059⟧)

- [⟦ic_0020⟧](⟦lu_0058⟧)

- [⟦ic_0019⟧](⟦lu_0057⟧)

- [⟦ic_0018⟧](⟦lu_0056⟧)

- [⟦ic_0017⟧](⟦lu_0055⟧)

## [See Also](/documentation/swiftui/projectiontransform#see-also)

### [缩放、旋转或变换视图](/documentation/swiftui/projectiontransform#Scaling-rotating-or-transforming-a-view)

[`func scaledToFill() -> some View`](/documentation/swiftui/view/scaledtofill()缩放此视图以填充其父视图。 [`func scaledToFit() -> some View`](/documentation/swiftui/view/scaledtofit())缩放此视图以适应其父视图。[`func scaleEffect(x: CGFloat, y: CGFloat, anchor: UnitPoint) -> some View`](/documentation/swiftui/view/scaleeffect(x:y:anchor:))相对于锚点，按给定的水平和垂直方向量缩放此视图的渲染输出。[`func scaleEffect(x: CGFloat, y: CGFloat, z: CGFloat, anchor: UnitPoint3D) -> some View`](/documentation/swiftui/view/scaleeffect(x:y:z:anchor:)相对于锚点，按指定的水平、垂直和深度系数缩放此视图。 [`func aspectRatio(_:contentMode:)`](/documentation/swiftui/view/aspectratio(_:contentmode:))Constrains this view's dimensions to the specified aspect ratio.[`func aspectRatio(_:contentMode:)`](/documentation/swiftui/view/aspectratio(_:contentmode:)将此视图的尺寸限制为指定的纵横比。[`func rotationEffect(Angle, anchor: UnitPoint) -> some View`](/documentation/swiftui/view/rotationeffect(_:anchor:))将视图的渲染输出围绕指定点进行二维旋转。 [`func rotation3DEffect(Angle, axis: (x: CGFloat, y: CGFloat, z: CGFloat), anchor: UnitPoint, anchorZ: CGFloat, perspective: CGFloat) -> some View`](/documentation/swiftui/view/rotation3deffect(_:axis:anchor:anchorz:perspective:))Renders a view's content as if it's rotated in three dimensions around the specified axis.[`func rotation3DEffect(Angle, axis: (x: CGFloat, y: CGFloat, z: CGFloat), anchor: UnitPoint, anchorZ: CGFloat, perspective: CGFloat) -> some View`](/documentation/swiftui/view/rotation3deffect(_:axis:anchor:anchorz:perspective:))将视图的内容渲染为围绕指定轴进行三维旋转。[`func perspectiveRotationEffect(Angle, axis: (x: CGFloat, y: CGFloat, z: CGFloat), anchor: UnitPoint, anchorZ: CGFloat, perspective: CGFloat) -> some View`](/documentation/swiftui/view/perspectiverotationeffect(_:axis:anchor:anchorz:perspective:))Renders a view's content as if it's rotated in three dimensions around the specified axis.[`func rotation3DEffect(Rotation3D, anchor: UnitPoint3D) -> some View`](/documentation/swiftui/view/rotation3deffect(_:anchor:))按指定的三维旋转值旋转视图内容。[`func rotation3DEffect(_:axis:anchor:)`](/documentation/swiftui/view/rotation3deffect(_:axis:anchor:))将视图内容围绕您指定为元素元组的轴旋转一个角度。 [`func transformEffect(CGAffineTransform) -> some View`](/documentation/swiftui/view/transformeffect(_:))对该视图的渲染输出应用仿射变换。[`func transform3DEffect(AffineTransform3D) -> some View`](/documentation/swiftui/view/transform3deffect(_:))Applies a 3D transformation to this view's rendered output.[`func projectionEffect(ProjectionTransform) -> some View`](/documentation/swiftui/view/projectioneffect(_:))将投影变换应用到此视图的渲染输出。

---
source: https://developer.apple.com/documentation/swiftui/projectiontransform
crawled: 2025-12-04T13:24:35Z
---

# ProjectionTransform | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ ProjectionTransform ](/documentation/swiftui/projectiontransform)

-  ProjectionTransform 

Structure# ProjectionTransform

iOS 13.0+iPadOS 13.0+Mac Catalyst 13.0+macOS 10.15+tvOS 13.0+visionOS 1.0+watchOS 6.0+

```
@frozen
struct ProjectionTransform
```

## [Topics](/documentation/swiftui/projectiontransform#topics)

### [Creating a transform](/documentation/swiftui/projectiontransform#Creating-a-transform)

[`init()`](/documentation/swiftui/projectiontransform/init())[`init(_:)`](/documentation/swiftui/projectiontransform/init(_:))### [Getting transform characteristics](/documentation/swiftui/projectiontransform#Getting-transform-characteristics)

[`var isAffine: Bool`](/documentation/swiftui/projectiontransform/isaffine)[`var isIdentity: Bool`](/documentation/swiftui/projectiontransform/isidentity)### [Manipulating transforms](/documentation/swiftui/projectiontransform#Manipulating-transforms)

[`func invert() -> Bool`](/documentation/swiftui/projectiontransform/invert())[`func inverted() -> ProjectionTransform`](/documentation/swiftui/projectiontransform/inverted())[`func concatenating(ProjectionTransform) -> ProjectionTransform`](/documentation/swiftui/projectiontransform/concatenating(_:))### [Accessing the transform’s coefficients](/documentation/swiftui/projectiontransform#Accessing-the-transforms-coefficients)

[`var m11: CGFloat`](/documentation/swiftui/projectiontransform/m11)[`var m12: CGFloat`](/documentation/swiftui/projectiontransform/m12)[`var m13: CGFloat`](/documentation/swiftui/projectiontransform/m13)[`var m21: CGFloat`](/documentation/swiftui/projectiontransform/m21)[`var m22: CGFloat`](/documentation/swiftui/projectiontransform/m22)[`var m23: CGFloat`](/documentation/swiftui/projectiontransform/m23)[`var m31: CGFloat`](/documentation/swiftui/projectiontransform/m31)[`var m32: CGFloat`](/documentation/swiftui/projectiontransform/m32)[`var m33: CGFloat`](/documentation/swiftui/projectiontransform/m33)## [Relationships](/documentation/swiftui/projectiontransform#relationships)

### [Conforms To](/documentation/swiftui/projectiontransform#conforms-to)

- [`BitwiseCopyable`](/documentation/Swift/BitwiseCopyable)

- [`Copyable`](/documentation/Swift/Copyable)

- [`Equatable`](/documentation/Swift/Equatable)

- [`Sendable`](/documentation/Swift/Sendable)

- [`SendableMetatype`](/documentation/Swift/SendableMetatype)

## [See Also](/documentation/swiftui/projectiontransform#see-also)

### [Scaling, rotating, or transforming a view](/documentation/swiftui/projectiontransform#Scaling-rotating-or-transforming-a-view)

[`func scaledToFill() -> some View`](/documentation/swiftui/view/scaledtofill())Scales this view to fill its parent.[`func scaledToFit() -> some View`](/documentation/swiftui/view/scaledtofit())Scales this view to fit its parent.[`func scaleEffect(_:anchor:)`](/documentation/swiftui/view/scaleeffect(_:anchor:))Scales this view’s rendered output by the given amount in both the horizontal and vertical directions, relative to an anchor point.[`func scaleEffect(_:anchor:)`](/documentation/swiftui/view/scaleeffect(_:anchor:))Scales this view’s rendered output by the given amount in both the horizontal and vertical directions, relative to an anchor point.[`func scaleEffect(x: CGFloat, y: CGFloat, anchor: UnitPoint) -> some View`](/documentation/swiftui/view/scaleeffect(x:y:anchor:))Scales this view’s rendered output by the given horizontal and vertical amounts, relative to an anchor point.[`func scaleEffect(x: CGFloat, y: CGFloat, z: CGFloat, anchor: UnitPoint3D) -> some View`](/documentation/swiftui/view/scaleeffect(x:y:z:anchor:))Scales this view by the specified horizontal, vertical, and depth factors, relative to an anchor point.[`func aspectRatio(_:contentMode:)`](/documentation/swiftui/view/aspectratio(_:contentmode:))Constrains this view’s dimensions to the specified aspect ratio.[`func rotationEffect(Angle, anchor: UnitPoint) -> some View`](/documentation/swiftui/view/rotationeffect(_:anchor:))Rotates a view’s rendered output in two dimensions around the specified point.[`func rotation3DEffect(Angle, axis: (x: CGFloat, y: CGFloat, z: CGFloat), anchor: UnitPoint, anchorZ: CGFloat, perspective: CGFloat) -> some View`](/documentation/swiftui/view/rotation3deffect(_:axis:anchor:anchorz:perspective:))Renders a view’s content as if it’s rotated in three dimensions around the specified axis.[`func perspectiveRotationEffect(Angle, axis: (x: CGFloat, y: CGFloat, z: CGFloat), anchor: UnitPoint, anchorZ: CGFloat, perspective: CGFloat) -> some View`](/documentation/swiftui/view/perspectiverotationeffect(_:axis:anchor:anchorz:perspective:))Renders a view’s content as if it’s rotated in three dimensions around the specified axis.[`func rotation3DEffect(Rotation3D, anchor: UnitPoint3D) -> some View`](/documentation/swiftui/view/rotation3deffect(_:anchor:))Rotates the view’s content by the specified 3D rotation value.[`func rotation3DEffect(_:axis:anchor:)`](/documentation/swiftui/view/rotation3deffect(_:axis:anchor:))Rotates the view’s content by an angle about an axis that you specify as a tuple of elements.[`func transformEffect(CGAffineTransform) -> some View`](/documentation/swiftui/view/transformeffect(_:))Applies an affine transformation to this view’s rendered output.[`func transform3DEffect(AffineTransform3D) -> some View`](/documentation/swiftui/view/transform3deffect(_:))Applies a 3D transformation to this view’s rendered output.[`func projectionEffect(ProjectionTransform) -> some View`](/documentation/swiftui/view/projectioneffect(_:))Applies a projection transformation to this view’s rendered output.