---
来源：https://developer.apple.com/documentation/SwiftUI/VisualEffect/distortionEffect(_:maxSampleOffset:isEnabled:)
抓取时间：2025-12-01T11:19:11Z
---

# distortionEffect(_:maxSampleOffset:isEnabled:)

**实例方法**

返回一个新的视觉效果，将`shader`应用到`self`，作为每个像素位置的几何扭曲效果。

## 声明

```swift
func distortionEffect(_ shader: Shader, maxSampleOffset: CGSize, isEnabled: Bool = true) -> some VisualEffect

```

## 参数

- **shader**：作为扭曲效果应用的着色器。
- **maxSampleOffset**：对于所有源像素，返回的源像素位置与目标像素位置之间在每个轴上的最大距离。
- **isEnabled**：是否启用效果。

## 返回值

渲染`self` 的新视图，该视图应用了着色器的扭曲效果。

## 讨论

着色器函数必须具有与函数特征匹配的函数特征，才能作为扭曲效果使用：

```swift
[[ stitchable ]] float2 name(float2 position, args...)
```

其中，`position` 是应用到着色器的目标像素的用户空间坐标。`args...`应与绑定到`shader`的统一参数兼容。函数应返回相应源像素的用户空间坐标。



## 应用其他效果

- **blur(radius:opaque:)**：对视图应用高斯模糊。
- **layerEffect(_:maxSampleOffset:isEnabled:)**：返回一个新的视觉效果，将`shader` 作为滤镜应用到由`self` 创建的栅格图层上的`self`。


---
source: https://developer.apple.com/documentation/SwiftUI/VisualEffect/distortionEffect(_:maxSampleOffset:isEnabled:)
crawled: 2025-12-01T11:19:11Z
---

# distortionEffect(_:maxSampleOffset:isEnabled:)

**Instance Method**

Returns a new visual effect that applies `shader` to `self` as a geometric distortion effect on the location of each pixel.

## Declaration

```swift
func distortionEffect(_ shader: Shader, maxSampleOffset: CGSize, isEnabled: Bool = true) -> some VisualEffect

```

## Parameters

- **shader**: The shader to apply as a distortion effect.
- **maxSampleOffset**: The maximum distance in each axis between the returned source pixel position and the destination pixel position, for all source pixels.
- **isEnabled**: Whether the effect is enabled or not.

## Return Value

A new view that renders `self` with the shader applied as a distortion effect.

## Discussion

For a shader function to act as a distortion effect it must have a function signature matching:

```swift
[[ stitchable ]] float2 name(float2 position, args...)
```

where `position` is the user-space coordinates of the destination pixel applied to the shader. `args...` should be compatible with the uniform arguments bound to `shader`. The function should return the user-space coordinates of the corresponding source pixel.



## Applying other effects

- **blur(radius:opaque:)**: Applies a Gaussian blur to the view.
- **layerEffect(_:maxSampleOffset:isEnabled:)**: Returns a new visual effect that applies `shader` to `self` as a filter on the raster layer created from `self`.

