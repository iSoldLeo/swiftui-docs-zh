---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/Filter/colorShader(_:)
抓取时间： 2025-12-01T22:05:54Z
---

# colorShader(_:)

**类型方法**

返回对每个源像素的颜色应用`shader` 的过滤器。

## 声明

```swift
static func colorShader(_ shader: Shader) -> GraphicsContext.Filter
```

## 参数

- **shader**：作为滤色器应用于`self` 的着色器。

## 返回值

将着色器作为滤色器应用的过滤器。

## 讨论

要将着色器函数用作滤色器，它必须有一个与之匹配的函数签名：

```swift
[[ stitchable ]] half4 name(float2 position, half4 color, args...)
```

其中，`position` 是应用到着色器的像素的用户空间坐标，`color` 是源颜色，作为目标颜色空间中的预乘颜色。`args...`应与绑定到`shader`的统一参数兼容。函数应返回修改后的颜色值。

## 使用自定义的 Metal 着色器

- **distortionShader(_:maxSampleOffset:)**：返回一个过滤器，在每个像素的位置上应用 `shader` 作为几何扭曲效果。
- **layerShader(_:maxSampleOffset:)**：返回对源图层内容应用`shader` 的滤波器。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/Filter/colorShader(_:)
crawled: 2025-12-01T22:05:54Z
---

# colorShader(_:)

**Type Method**

Returns a filter that applies `shader` to the color of each source pixel.

## Declaration

```swift
static func colorShader(_ shader: Shader) -> GraphicsContext.Filter
```

## Parameters

- **shader**: The shader to apply to `self` as a color filter.

## Return Value

A filter that applies the shader  as a color filter.

## Discussion

For a shader function to act as a color filter it must have a function signature matching:

```swift
[[ stitchable ]] half4 name(float2 position, half4 color, args...)
```

where `position` is the user-space coordinates of the pixel applied to the shader and `color` its source color, as a pre-multiplied color in the destination color space. `args...` should be compatible with the uniform arguments bound to `shader`. The function should return the modified color value.

## Using a custom Metal shader

- **distortionShader(_:maxSampleOffset:)**: Returns a filter that applies `shader` as a geometric distortion effect on the location of each pixel.
- **layerShader(_:maxSampleOffset:)**: Returns a filter that applies `shader` to the contents of the source layer.

