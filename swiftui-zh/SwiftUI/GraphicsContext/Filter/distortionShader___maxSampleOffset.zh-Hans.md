---
来源: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/Filter/distortionShader(_:maxSampleOffset:)
抓取时间：2025-12-01T22:05:55Z
---

# distortionShader(_:maxSampleOffset:)

**类型方法**

返回对每个像素的位置应用 `shader` 作为几何扭曲效果的过滤器。

## 声明

```swift
static func distortionShader(_ shader: Shader, maxSampleOffset: CGSize) -> GraphicsContext.Filter
```

## 参数

- **shader**：作为扭曲效果应用的着色器。
- **maxSampleOffset**：对于所有源像素，返回的源像素位置与目标像素位置之间在每个轴上的最大距离。

## 返回值

一个新的滤镜，将着色器应用为扭曲效果。

## 讨论

着色器函数若要作为扭曲效果，必须具有与之匹配的函数签名：

```swift
[[ stitchable ]] float2 name(float2 position, args...)
```

其中，`position` 是应用到着色器的目标像素的用户空间坐标。`args...`应与绑定到`shader`的统一参数兼容。函数应返回相应源像素的用户空间坐标。

## 使用自定义的 Metal 着色器

- **colorShader(_:)**：返回对每个源像素的颜色应用`shader` 的过滤器。
- **layerShader(_:maxSampleOffset:)**：返回对源图层内容应用 `shader` 的滤镜。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/Filter/distortionShader(_:maxSampleOffset:)
crawled: 2025-12-01T22:05:55Z
---

# distortionShader(_:maxSampleOffset:)

**Type Method**

Returns a filter that applies `shader` as a geometric distortion effect on the location of each pixel.

## Declaration

```swift
static func distortionShader(_ shader: Shader, maxSampleOffset: CGSize) -> GraphicsContext.Filter
```

## Parameters

- **shader**: The shader to apply as a distortion effect.
- **maxSampleOffset**: The maximum distance in each axis between the returned source pixel position and the destination pixel position, for all source pixels.

## Return Value

A new filter that applies the shader as a distortion effect.

## Discussion

For a shader function to act as a distortion effect it must have a function signature matching:

```swift
[[ stitchable ]] float2 name(float2 position, args...)
```

where `position` is the user-space coordinates of the destination pixel applied to the shader. `args...` should be compatible with the uniform arguments bound to `shader`. The function should return the user-space coordinates of the corresponding source pixel.

## Using a custom Metal shader

- **colorShader(_:)**: Returns a filter that applies `shader` to the color of each source pixel.
- **layerShader(_:maxSampleOffset:)**: Returns a filter that applies `shader` to the contents of the source layer.

