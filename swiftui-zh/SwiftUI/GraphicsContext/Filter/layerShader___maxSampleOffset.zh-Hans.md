---
来源: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/Filter/layerShader(_:maxSampleOffset:)
抓取时间：2025-12-03T17:20:39Z
---

# layerShader(_:maxSampleOffset:)

**类型方法**

返回对源图层内容应用 `shader` 的过滤器。

## 声明

```swift
static func layerShader(_ shader: Shader, maxSampleOffset: CGSize) -> GraphicsContext.Filter
```

## 参数

- **shader**：要作为图层效果应用的着色器。
- **maxSampleOffset**：**maxSampleOffset**： 如果着色器函数在与目标位置不相等的位置对图层进行采样，则此值必须指定所有源像素在每个轴上的最大采样距离。

## 返回值

滤镜将着色器作为图层效果应用。

## 讨论

着色器函数要作为图层效果，必须有一个与之匹配的函数签名：

```swift
[[ stitchable ]] half4 name(float2 position,
  SwiftUI::Layer layer, args...)
```

其中，`position` 是应用到着色器的目标像素的用户空间坐标，`layer` 是源图层的光栅化子区域。`args...`应与绑定到`shader`的统一参数兼容。

`SwiftUI::Layer`类型是在`<SwiftUI/SwiftUI.h>`头文件中定义的。它导出一个`sample()`函数，从源内容中的某个位置返回经过线性滤波的像素值，作为预乘法的 RGBA 像素值：

```swift
namespace SwiftUI {
  struct Layer {
    half4 sample(float2 position) const;
  };
};
```

该函数应返回目标像素的颜色映射，通常是通过在从`layer` 提取的位置从`position` 中抽取一个或多个像素，然后应用某种变换来生成新的颜色。

## 使用自定义金属着色器

- **colorShader(_:)**：返回对每个源像素的颜色应用`shader` 的滤镜。
- **distortionShader(_:maxSampleOffset:)**：返回对每个像素的位置应用 `shader` 作为几何扭曲效果的滤波器。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/Filter/layerShader(_:maxSampleOffset:)
crawled: 2025-12-03T17:20:39Z
---

# layerShader(_:maxSampleOffset:)

**Type Method**

Returns a filter that applies `shader` to the contents of the source layer.

## Declaration

```swift
static func layerShader(_ shader: Shader, maxSampleOffset: CGSize) -> GraphicsContext.Filter
```

## Parameters

- **shader**: The shader to apply as a layer effect.
- **maxSampleOffset**: If the shader function samples from the layer at locations not equal to the destination position, this value must specify the maximum sampling distance in each axis, for all source pixels.

## Return Value

A filter applies the shader as a layer effect.

## Discussion

For a shader function to act as a layer effect it must have a function signature matching:

```swift
[[ stitchable ]] half4 name(float2 position,
  SwiftUI::Layer layer, args...)
```

where `position` is the user-space coordinates of the destination pixel applied to the shader, and `layer` is a rasterized subregion of the source layer. `args...` should be compatible with the uniform arguments bound to `shader`.

The `SwiftUI::Layer` type is defined in the `<SwiftUI/SwiftUI.h>` header file. It exports a single `sample()` function that returns a linearly-filtered pixel value from a position in the source content, as a premultiplied RGBA pixel value:

```swift
namespace SwiftUI {
  struct Layer {
    half4 sample(float2 position) const;
  };
};
```

The function should return the color mapping to the destination pixel, typically by sampling one or more pixels from `layer` at location(s) derived from `position` and them applying some kind of transformation to produce a new color.

## Using a custom Metal shader

- **colorShader(_:)**: Returns a filter that applies `shader` to the color of each source pixel.
- **distortionShader(_:maxSampleOffset:)**: Returns a filter that applies `shader` as a geometric distortion effect on the location of each pixel.

