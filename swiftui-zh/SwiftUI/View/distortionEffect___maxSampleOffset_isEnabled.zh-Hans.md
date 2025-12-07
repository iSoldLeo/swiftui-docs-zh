--- 来源：https://developer.apple.com/documentation/SwiftUI/View/distortionEffect(_:maxSampleOffset:isEnabled:)

抓取时间：2025-11-30T21:22:55Z

---

# distortionEffect(_:maxSampleOffset:isEnabled:)

**实例方法**

返回一个新的视图，该视图将 `shader` 到 `self` 应用于每个像素位置，作为几何扭曲效果。

## 声明

```swift
nonisolated func distortionEffect(_ shader: Shader, maxSampleOffset: CGSize, isEnabled: Bool = true) -> some View

```

## 参数

- **shader**：要应用为扭曲效果的着色器。

- **maxSampleOffset**：返回的源像素位置和目标像素位置之间在每个轴上的最大距离，适用于所有源像素。

- **isEnabled**：效果是否启用。

## 返回值

一个新视图，渲染应用了扭曲效果的着色器 `self`。

## 说明

要使着色器函数能够作为扭曲效果，其函数签名必须符合以下要求：

```swift
[[ stitchable ]] float2 name(float2 position, args...)
```

其中 `position` 是应用着色器的目标像素的用户空间坐标。`args...` 应与绑定到 `shader` 的 uniform 参数兼容。该函数应返回对应源像素的用户空间坐标。

## 访问 Metal 着色器

- **colorEffect(_:isEnabled:)**：返回一个新视图，该视图将 `shader` 到 `self` 应用于每个像素的颜色，作为滤镜效果。

- **layerEffect(_:maxSampleOffset:isEnabled:)**：返回一个新视图，该视图将 `shader` 到 `self` 应用于由 `self` 创建的栅格图层，作为滤镜效果。

- **Shader**：指向 Metal 着色器库中函数的引用，以及其绑定的 uniform 参数值。

- **ShaderFunction**：指向 Metal 着色器库中函数的引用。

- **ShaderLibrary**：一个 Metal 着色器库。


---
source: https://developer.apple.com/documentation/SwiftUI/View/distortionEffect(_:maxSampleOffset:isEnabled:)
crawled: 2025-11-30T21:22:55Z
---

# distortionEffect(_:maxSampleOffset:isEnabled:)

**Instance Method**

Returns a new view that applies `shader` to `self` as a geometric distortion effect on the location of each pixel.

## Declaration

```swift
nonisolated func distortionEffect(_ shader: Shader, maxSampleOffset: CGSize, isEnabled: Bool = true) -> some View

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



## Accessing Metal shaders

- **colorEffect(_:isEnabled:)**: Returns a new view that applies `shader` to `self` as a filter effect on the color of each pixel.
- **layerEffect(_:maxSampleOffset:isEnabled:)**: Returns a new view that applies `shader` to `self` as a filter on the raster layer created from `self`.
- **Shader**: A reference to a function in a Metal shader library, along with its bound uniform argument values.
- **ShaderFunction**: A reference to a function in a Metal shader library.
- **ShaderLibrary**: A Metal shader library.

