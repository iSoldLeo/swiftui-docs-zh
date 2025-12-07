---
来源：https://developer.apple.com/documentation/SwiftUI/VisualEffect/layerEffect(_:maxSampleOffset:isEnabled:)
抓取时间：2025-12-03T06:30:03Z
---

# layerEffect(_:maxSampleOffset:isEnabled:)

**实例方法**

返回一个新的视觉效果，在由`self`创建的栅格图层上将`shader`作为滤镜应用到`self`。

## 声明

```swift
func layerEffect(_ shader: Shader, maxSampleOffset: CGSize, isEnabled: Bool = true) -> some VisualEffect

```

## 参数

- **shader**：要作为图层效果应用的着色器。
- **maxSampleOffset**：**maxSampleOffset**： 如果着色器函数在与目标位置不相等的位置对图层进行采样，则此值必须指定所有源像素在每个轴上的最大采样距离。
- **isEnabled**：是否启用效果。

## 返回值

渲染`self` 的新视图，该视图应用了着色器的扭曲效果。

## 讨论

着色器函数要作为图层效果，必须具有与之匹配的函数签名：

```swift
[[ stitchable ]] half4 name(float2 position,
  SwiftUI::Layer layer, args...)
```

其中，`position` 是应用到着色器的目标像素的用户空间坐标，`layer` 是`self` 光栅化内容的子区域。`args...`应与绑定到`shader`的统一参数兼容。

`SwiftUI::Layer`类型是在`<SwiftUI/SwiftUI.h>`头文件中定义的。它导出一个`sample()`函数，从源内容中的某个位置返回经过线性滤波的像素值，作为预乘法的 RGBA 像素值：

```swift
namespace SwiftUI {
  struct Layer {
    half4 sample(float2 position) const;
  };
};
```

该函数应返回目标像素的颜色映射，通常是通过在从`layer` 提取的位置从`position` 中抽取一个或多个像素，然后应用某种变换来生成新的颜色。



## 应用其他效果

- **blur(radius:opaque:)**：对视图应用高斯模糊。
- **distortionEffect(_:maxSampleOffset:isEnabled:)**：返回一个新的视觉效果，将`shader` 应用到`self`，作为每个像素位置的几何扭曲效果。


---
source: https://developer.apple.com/documentation/SwiftUI/VisualEffect/layerEffect(_:maxSampleOffset:isEnabled:)
crawled: 2025-12-03T06:30:03Z
---

# layerEffect(_:maxSampleOffset:isEnabled:)

**Instance Method**

Returns a new visual effect that applies `shader` to `self` as a filter on the raster layer created from `self`.

## Declaration

```swift
func layerEffect(_ shader: Shader, maxSampleOffset: CGSize, isEnabled: Bool = true) -> some VisualEffect

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



## Applying other effects

- **blur(radius:opaque:)**: Applies a Gaussian blur to the view.
- **distortionEffect(_:maxSampleOffset:isEnabled:)**: Returns a new visual effect that applies `shader` to `self` as a geometric distortion effect on the location of each pixel.

