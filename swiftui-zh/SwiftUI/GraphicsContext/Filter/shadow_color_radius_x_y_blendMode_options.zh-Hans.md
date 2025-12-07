---
來源：https://developer.apple.com/documentation/SwiftUI/GraphicsContext/Filter/shadow(color:radius:x:y:blendMode:options:)
抓取时间：2025-12-03T17:20:35Z


# shadow(color:radius:x:y:blendMode:options:)

**类型方法**

返回添加阴影的过滤器。

## 声明

```swift
static func shadow(color: Color = Color(.sRGBLinear, white: 0, opacity: 0.33), radius: CGFloat, x: CGFloat = 0, y: CGFloat = 0, blendMode: GraphicsContext.BlendMode = .normal, options: GraphicsContext.ShadowOptions = ShadowOptions()) -> GraphicsContext.Filter
```

## 参数

- **color**：为阴影着色的[Color](../../Color.zh-Hans.md)。
- **radius**：阴影从接收阴影的内容边缘延伸多远的量度。
- **x**：水平平移阴影的量。
- **y**：垂直平移阴影的量。
- **blendMode**：将阴影混合到背景图层时使用的[BlendMode-swift.struct](../BlendMode-swift_struct.zh-Hans.md)。
- **options**：一组选项，可用于自定义添加阴影的过程。使用[ShadowOptions](../ShadowOptions.zh-Hans.md) 中的一个或多个选项。

## 返回值

添加阴影样式的过滤器。

## 讨论

SwiftUI 通过模糊接收阴影对象的 alpha 通道、将结果乘以颜色、选择性地将阴影平移一定量，然后将产生的阴影混合到源基元下面的新图层中，从而生成阴影。您可以通过添加一个或多个阴影选项来自定义其中的一些步骤。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/Filter/shadow(color:radius:x:y:blendMode:options:)
crawled: 2025-12-03T17:20:35Z
---

# shadow(color:radius:x:y:blendMode:options:)

**Type Method**

Returns a filter that adds a shadow.

## Declaration

```swift
static func shadow(color: Color = Color(.sRGBLinear, white: 0, opacity: 0.33), radius: CGFloat, x: CGFloat = 0, y: CGFloat = 0, blendMode: GraphicsContext.BlendMode = .normal, options: GraphicsContext.ShadowOptions = ShadowOptions()) -> GraphicsContext.Filter
```

## Parameters

- **color**: A [Color](../../Color.zh-Hans.md) that tints the shadow.
- **radius**: A measure of how far the shadow extends from the edges of the content receiving the shadow.
- **x**: An amount to translate the shadow horizontally.
- **y**: An amount to translate the shadow vertically.
- **blendMode**: The [BlendMode-swift.struct](../BlendMode-swift_struct.zh-Hans.md) to use when blending the shadow into the background layer.
- **options**: A set of options that you can use to customize the process of adding the shadow. Use one or more of the options in [ShadowOptions](../ShadowOptions.zh-Hans.md).

## Return Value

A filter that adds a shadow style.

## Discussion

SwiftUI produces the shadow by blurring the alpha channel of the object receiving the shadow, multiplying the result by a color, optionally translating the shadow by an amount, and then blending the resulting shadow into a new layer below the source primitive. You can customize some of these steps by adding one or more shadow options.

