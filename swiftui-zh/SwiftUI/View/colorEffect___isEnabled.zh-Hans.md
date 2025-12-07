--- 来源：https://developer.apple.com/documentation/SwiftUI/View/colorEffect(_:isEnabled:)

抓取时间：2025-11-30T21:22:54Z

---

# colorEffect(_:isEnabled:)

**实例方法**

返回一个新视图，该视图将 `shader` 应用于 `self` 作为滤镜效果，并应用于每个像素的颜色。

## 声明

```swift
nonisolated func colorEffect(_ shader: Shader, isEnabled: Bool = true) -> some View

```

## 参数

- **shader**：要应用于 `self` 作为颜色滤镜的着色器。

- **isEnabled**：效果是否启用。

## 返回值

一个新视图，渲染应用了着色器作为颜色滤镜的 `self`。

## 讨论

要使着色器函数能够作为颜色滤镜，其函数签名必须符合以下要求：

```swift
[[ stitchable ]] half4 name(float2 position, half4 color, args...)
```

其中 `position` 是应用着色器的像素的用户空间坐标，`color` 是其源颜色，作为目标颜色空间中的预乘颜色。`args...` 应与绑定到 `shader` 的 uniform 参数兼容。该函数应返回修改后的颜色值。

## 访问 Metal 着色器

- **distortionEffect(_:maxSampleOffset:isEnabled:)**：返回一个新视图，该视图将 `shader` 到 `self` 应用于每个像素的位置，作为几何扭曲效果。

- **layerEffect(_:maxSampleOffset:isEnabled:)**：返回一个新视图，该视图将 `shader` 到 `self` 应用于由 `self` 创建的栅格图层，作为滤镜。

- **Shader**：指向 Metal 着色器库中函数的引用，以及其绑定的 uniform 参数值。

- **ShaderFunction**：指向 Metal 着色器库中函数的引用。

- **ShaderLibrary**：一个 Metal 着色器库。


---
source: https://developer.apple.com/documentation/SwiftUI/View/colorEffect(_:isEnabled:)
crawled: 2025-11-30T21:22:54Z
---

# colorEffect(_:isEnabled:)

**Instance Method**

Returns a new view that applies `shader` to `self` as a filter effect on the color of each pixel.

## Declaration

```swift
nonisolated func colorEffect(_ shader: Shader, isEnabled: Bool = true) -> some View

```

## Parameters

- **shader**: The shader to apply to `self` as a color filter.
- **isEnabled**: Whether the effect is enabled or not.

## Return Value

A new view that renders `self` with the shader applied as a color filter.

## Discussion

For a shader function to act as a color filter it must have a function signature matching:

```swift
[[ stitchable ]] half4 name(float2 position, half4 color, args...)
```

where `position` is the user-space coordinates of the pixel applied to the shader and `color` its source color, as a pre-multiplied color in the destination color space. `args...` should be compatible with the uniform arguments bound to `shader`. The function should return the modified color value.



## Accessing Metal shaders

- **distortionEffect(_:maxSampleOffset:isEnabled:)**: Returns a new view that applies `shader` to `self` as a geometric distortion effect on the location of each pixel.
- **layerEffect(_:maxSampleOffset:isEnabled:)**: Returns a new view that applies `shader` to `self` as a filter on the raster layer created from `self`.
- **Shader**: A reference to a function in a Metal shader library, along with its bound uniform argument values.
- **ShaderFunction**: A reference to a function in a Metal shader library.
- **ShaderLibrary**: A Metal shader library.

