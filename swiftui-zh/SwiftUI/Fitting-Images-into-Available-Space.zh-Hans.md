---
来源： https://developer.apple.com/documentation/SwiftUI/Fitting-Images-into-Available-Space
抓取时间： 2025-12-02T17:35:46Z
---

# 将图像放入可用空间

**Article**

通过应用视图修改器，调整应用程序用户界面中图像的大小和形状。

### 概览

从单像素的 PNG 文件到数百万像素的数码摄影图像，图像的大小千差万别。由于设备尺寸也各不相同，应用程序通常需要在运行时调整图片大小，使其适合可见的用户界面。SwiftUI 提供了修改器来缩放、剪切和变换图像，使其完全适合您的界面。

### 使用调整大小来缩放大图像以适应其容器

请看图片 `Landscape_4.jpg`，这是一张尺寸为 4032 x 3024 的照片，显示了一个水车、周围的建筑和上方的天空。



下面的示例将图像直接加载到[Image](Image.zh-Hans.md) 视图中，然后将其放置在一个 300 x 400 点的边框中，边框为蓝色：

```swift
    Image("Landscape_4")
        .frame(width: 300, height: 400, alignment: .topLeading)
        .border(.blue)
```

从下面的截图中可以看到，图像数据以全尺寸加载到视图中，因此只能看到原始图像左上方的云层。由于图像以全尺寸渲染，而蓝色边框比原始图像小，因此图像超出了边框的边界。



要解决这个问题，需要对 `Image`应用两个修改器：

- [resizable(capInsets:resizingMode:)](Image/resizable_capInsets_resizingMode.zh-Hans.md)告诉图像视图调整图像表示法以匹配视图的大小。默认情况下，该修改器通过缩小较大图像的尺寸和放大小于视图尺寸的图像来缩放图像。此修改器本身可独立缩放图像的每个轴。
- [aspectRatio(_:contentMode:)](View/aspectRatio___contentMode.zh-Hans.md)可纠正每个轴的图像缩放比例不同的行为。这可以使用[ContentMode](ContentMode.zh-Hans.md)枚举定义的两种策略之一来保持图像的原始纵横比。[fit](ContentMode/fit.zh-Hans.md)沿一个轴缩放图像以适应视图大小，可能沿另一个轴留出空白。[fill](ContentMode/fill.zh-Hans.md)缩放图像以填充整个视图。

```swift
  Image("Landscape_4")
      .resizable()
      .aspectRatio(contentMode: .fit)
      .frame(width: 300, height: 400, alignment: .topLeading)
      .border(.blue)
```



### 使用剪切功能将图像数据保持在视图范围内

如果在缩放图像时使用[fill](ContentMode/fill.zh-Hans.md)，图像的一部分可能会超出视图的边界，除非视图与图像的纵横比完全匹配。下面的示例说明了这个问题：

```swift
    Image("Landscape_4")
        .resizable()
        .aspectRatio(contentMode: .fill)
        .frame(width: 300, height: 400, alignment: .topLeading)
        .border(.blue)
```



为防止出现此问题，请添加 [clipped(antialiased:)](View/clipped_antialiased.zh-Hans.md) 修改器。该修改器只需在视图的边界框处切断多余的图像渲染。您还可以选择添加抗锯齿行为，对剪切矩形的边缘进行平滑处理；该参数默认为 `false`。下面的示例显示了在前面的填充模式示例中添加削边的效果：

```swift
    Image("Landscape_4")
        .resizable()
        .aspectRatio(contentMode: .fill)
        .frame(width: 300, height: 400, alignment: .topLeading)
        .border(.blue)
        .clipped()
```



### 使用插值标志调整渲染图像质量

以原始尺寸以外的任何尺寸渲染图像都需要*插值*：使用现有图像数据来近似呈现不同尺寸的图像。执行插值的不同方法在计算复杂度和渲染图像的视觉质量之间有不同的权衡。您可以使用[interpolation(_:)](Image/interpolation.zh-Hans.md)修饰符为 SwiftUI 渲染行为提供提示。

在将较小的图像缩放到较大的空间时，更容易看到插值的效果，因为渲染的图像需要的图像数据比可用的要多。请看下面的示例，它将名为 `dot_green` 的 34 x 34 图像渲染到与之前相同的 300 x 400 容器框架中：

```swift
    Image("dot_green")
        .resizable()
        .interpolation(.none)
        .aspectRatio(contentMode: .fit)
        .frame(width: 300, height: 400, alignment: .topLeading)
        .border(.blue)
```

将 [none](Image/Interpolation/none.zh-Hans.md) 值传递给 [interpolation(_:)](Image/interpolation.zh-Hans.md) 会产生像素化程度很高的渲染图像。



如果将插值改为 [medium](Image/Interpolation/medium.zh-Hans.md)，SwiftUI 就会平滑像素数据，从而生成像素化程度不高的图像：





###使用平铺法用重复图像填充空间

当你的图像远小于你想要渲染的空间时，另一种填充空间的方法是*平铺*：重复绘制相同的图像。要平铺图像，可将[tile](Image/ResizingMode/tile.zh-Hans.md)参数传递给[resizable(capInsets:resizingMode:)](Image/resizable_capInsets_resizingMode.zh-Hans.md)修改器：

```swift
    Image("dot_green")
        .resizable(resizingMode: .tile)
        .frame(width: 300, height: 400, alignment: .topLeading)
        .border(.blue)
```



平铺法在使用图像时特别有用，当图像与自身的副本端对端放置时，就会形成一个更大的图案，而不会出现视觉上的不连续性。

## 配置图像

- **imageScale(_:)**：根据可用的相对尺寸（包括小、中、大图像尺寸）缩放视图中的图像。
- **imageScale**：此环境的图像比例。
- **Image.Scale**：相对于文本应用于矢量图像的比例。
- **Image.Orientation**：图像的方向。
- **Image.ResizingMode**：SwiftUI 用来调整图像大小以适合其包含的视图的模式。


---
source: https://developer.apple.com/documentation/SwiftUI/Fitting-Images-into-Available-Space
crawled: 2025-12-02T17:35:46Z
---

# Fitting images into available space

**Article**

Adjust the size and shape of images in your app’s user interface by applying view modifiers.

## Overview

Image sizes vary widely, from single-pixel PNG files to digital photography images with millions of pixels. Because device sizes also vary, apps commonly need to make runtime adjustments to image sizes so they fit within the visible user interface. SwiftUI provides modifiers to scale, clip, and transform images to fit your interface perfectly.

### Scale a large image to fit its container using resizing

Consider the image `Landscape_4.jpg`, a photograph with the dimensions 4032 x 3024, showing a water wheel, the surrounding building, and the sky above.



The following example loads the image directly into an [Image](Image.zh-Hans.md) view, and then places it in a 300 x 400 point frame, with a blue border:

```swift
    Image("Landscape_4")
        .frame(width: 300, height: 400, alignment: .topLeading)
        .border(.blue)
```

As seen in the following screenshot, the image data loads at full size into the view, so only the clouds from the upper left of the original image are visible. Because the image renders at full size, and the blue frame is smaller than the original image, the image extends beyond the frame’s boundaries.



To fix this, you need to apply two modifiers to the `Image`:

- [resizable(capInsets:resizingMode:)](Image/resizable_capInsets_resizingMode.zh-Hans.md) tells the image view to adjust the image representation to match the size of the view. By default, this modifier scales the image by reducing the size of larger images and enlarges images smaller than the view. By itself, this modifier scales each axis of the image independently.
- [aspectRatio(_:contentMode:)](View/aspectRatio___contentMode.zh-Hans.md) corrects the behavior where the image scaling is different for each axis. This preserves the image’s original aspect ratio, using one of two strategies defined by the [ContentMode](ContentMode.zh-Hans.md) enumeration. [fit](ContentMode/fit.zh-Hans.md) scales the image to fit the view size along one axis, possibly leaving empty space along the other axis. [fill](ContentMode/fill.zh-Hans.md) scales the image to fill the entire view.

```swift
  Image("Landscape_4")
      .resizable()
      .aspectRatio(contentMode: .fit)
      .frame(width: 300, height: 400, alignment: .topLeading)
      .border(.blue)
```



### Keep image data inside the view’s bounds using clipping

If you use [fill](ContentMode/fill.zh-Hans.md) when scaling an image, a portion of an image may extend beyond the view’s bounds, unless the view matches the image’s aspect ratio exactly. The following example illustrates this problem:

```swift
    Image("Landscape_4")
        .resizable()
        .aspectRatio(contentMode: .fill)
        .frame(width: 300, height: 400, alignment: .topLeading)
        .border(.blue)
```



To prevent this problem, add the [clipped(antialiased:)](View/clipped_antialiased.zh-Hans.md) modifier. This modifier simply cuts off excess image rendering at the bounding frame of the view. Optionally, you can add an antialiasing behavior to apply smoothing to the edges of the clipping rectangle; this parameter defaults to `false`. The following example shows the effect of adding clipping to the previous fill-mode example:

```swift
    Image("Landscape_4")
        .resizable()
        .aspectRatio(contentMode: .fill)
        .frame(width: 300, height: 400, alignment: .topLeading)
        .border(.blue)
        .clipped()
```



### Use interpolation flags to adjust rendered image quality

Rendering an image at anything other than its original size requires *interpolation*: using the existing image data to approximate a representation at a different size. Different approaches to performing interpolation have different trade-offs between computational complexity and visual quality of the rendered image. You can use the [interpolation(_:)](Image/interpolation.zh-Hans.md) modifier to provide a hint for SwiftUI rendering behavior.

It’s easier to see the effect of interpolation when scaling a smaller image into a larger space, because the rendered image requires more image data than is available. Consider the following example, which renders a 34 x 34 image named `dot_green` into the same 300 x 400 container frame as before:

```swift
    Image("dot_green")
        .resizable()
        .interpolation(.none)
        .aspectRatio(contentMode: .fit)
        .frame(width: 300, height: 400, alignment: .topLeading)
        .border(.blue)
```

Passing the [none](Image/Interpolation/none.zh-Hans.md) value to [interpolation(_:)](Image/interpolation.zh-Hans.md) results in a highly pixelated rendered image.



If you change the interpolation value to [medium](Image/Interpolation/medium.zh-Hans.md), SwiftUI smoothes out the pixel data to produce an image that isn’t as pixelated:





### Fill a space with a repeating image using tiling

When you have an image that’s much smaller than the space you want to render it into, another option  to fill the space is *tiling*: repeating the same image over and over again. To tile an image, pass the [tile](Image/ResizingMode/tile.zh-Hans.md) parameter to the [resizable(capInsets:resizingMode:)](Image/resizable_capInsets_resizingMode.zh-Hans.md) modifier:

```swift
    Image("dot_green")
        .resizable(resizingMode: .tile)
        .frame(width: 300, height: 400, alignment: .topLeading)
        .border(.blue)
```



Tiling can be particuarly useful when using an image that, when placed end-to-end with copies of itself, creates a larger pattern with no visual discontinuities.

## Configuring an image

- **imageScale(_:)**: Scales images within the view according to one of the relative sizes available including small, medium, and large images sizes.
- **imageScale**: The image scale for this environment.
- **Image.Scale**: A scale to apply to vector images relative to text.
- **Image.Orientation**: The orientation of an image.
- **Image.ResizingMode**: The modes that SwiftUI uses to resize an image to fit within its containing view.

