--- 来源：https://developer.apple.com/documentation/SwiftUI/View/layerEffect(_:maxSampleOffset:isEnabled:)

抓取时间：2025-11-30T21:22:56Z

---

# layerEffect(_:maxSampleOffset:isEnabled:)

**实例方法**

返回一个新视图，该视图将 `shader` 应用于 `self` 作为滤镜，并应用于由 `self` 创建的栅格图层。

## 声明

```swift
nonisolated func layerEffect(_ shader: Shader, maxSampleOffset: CGSize, isEnabled: Bool = true) -> some View

```

## 参数

- **shader**：要作为图层效果应用的着色器。

- **maxSampleOffset**：如果着色器函数从图层中采样的位置与目标位置不相等，则此值必须指定每个轴上所有源像素的最大采样距离。

- **isEnabled**：效果是否启用。

## 返回值

一个新视图，渲染应用了作为扭曲效果的着色器 `self`。

## 说明

要使着色器函数作为图层效果，其函数签名必须匹配以下内容：

```swift
[[ stitchable ]] half4 name(float2 position,
  SwiftUI::Layer layer, args...)
```

其中 `position` 是应用于着色器的目标像素的用户空间坐标，`layer` 是 `self` 的光栅化内容的子区域。 `args...` 应与绑定到 `shader` 的统一参数兼容。

`SwiftUI::Layer` 类型定义在 `<SwiftUI/SwiftUI.h>` 头文件中。它导出一个 `sample()` 函数，该函数返回源内容中指定位置的线性滤波像素值，作为预乘 RGBA 像素值：

```swift
namespace SwiftUI {
  struct Layer {
    half4 sample(float2 position) const;
  };
};
```

该函数应返回到目标像素的颜色映射，通常是通过从 `layer` 中采样一个或多个像素（采样位置由 `position` 导出），然后应用某种变换来生成新的颜色。

## 访问 Metal 着色器

- **colorEffect(_:isEnabled:)**：返回一个新视图，该视图将 `shader` 到 `self` 应用于每个像素的颜色，作为滤镜效果。

- **distortionEffect(_:maxSampleOffset:isEnabled:)**：返回一个新视图，该视图将 `shader` 到 `self` 应用于每个像素的位置，作为几何扭曲效果。

- **Shader**：指向 Metal 着色器库中函数的引用，以及其绑定的 uniform 参数值。

- **ShaderFunction**：指向 Metal 着色器库中函数的引用。

- **ShaderLibrary**：一个 Metal 着色器库。


---
source: https://developer.apple.com/documentation/SwiftUI/View/layerEffect(_:maxSampleOffset:isEnabled:)
crawled: 2025-11-30T21:22:56Z
---

# layerEffect(_:maxSampleOffset:isEnabled:)

**Instance Method**

Returns a new view that applies `shader` to `self` as a filter on the raster layer created from `self`.

## Declaration

```swift
nonisolated func layerEffect(_ shader: Shader, maxSampleOffset: CGSize, isEnabled: Bool = true) -> some View

```

## Parameters

- **shader**: The shader to apply as a layer effect.
- **maxSampleOffset**: If the shader function samples from the layer at locations not equal to the destination position, this value must specify the maximum sampling distance in each axis, for all source pixels.
- **isEnabled**: Whether the effect is enabled or not.

## Return Value

A new view that renders `self` with the shader applied as a distortion effect.

## Discussion

For a shader function to act as a layer effect it must have a function signature matching:

```swift
[[ stitchable ]] half4 name(float2 position,
  SwiftUI::Layer layer, args...)
```

where `position` is the user-space coordinates of the destination pixel applied to the shader, and `layer` is a subregion of the rasterized contents of `self`. `args...` should be compatible with the uniform arguments bound to `shader`.

The `SwiftUI::Layer` type is defined in the `<SwiftUI/SwiftUI.h>` header file. It exports a single `sample()` function that returns a linearly-filtered pixel value from a position in the source content, as a premultiplied RGBA pixel value:

```swift
namespace SwiftUI {
  struct Layer {
    half4 sample(float2 position) const;
  };
};
```

The function should return the color mapping to the destination pixel, typically by sampling one or more pixels from `layer` at location(s) derived from `position` and them applying some kind of transformation to produce a new color.



## Accessing Metal shaders

- **colorEffect(_:isEnabled:)**: Returns a new view that applies `shader` to `self` as a filter effect on the color of each pixel.
- **distortionEffect(_:maxSampleOffset:isEnabled:)**: Returns a new view that applies `shader` to `self` as a geometric distortion effect on the location of each pixel.
- **Shader**: A reference to a function in a Metal shader library, along with its bound uniform argument values.
- **ShaderFunction**: A reference to a function in a Metal shader library.
- **ShaderLibrary**: A Metal shader library.

