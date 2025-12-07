--- 来源：https://developer.apple.com/documentation/SwiftUI/View/luminanceToAlpha()

抓取时间：2025-11-30T21:22:07Z

---

# luminanceToAlpha()

**实例方法**

为该视图添加亮度到透明度（Alpha）效果。

## 声明

```swift
nonisolated func luminanceToAlpha() -> some View

```

## 返回值

应用了亮度到透明度（Alpha）效果的视图。

## 说明

使用此方法可以创建半透明蒙版，修改后的视图中每个部分的透明度由原始视图中对应部分的亮度控制。亮度较低的区域会变得更加透明，而亮度较高的区域则会增加透明度。

具体来说，该修饰符将每个输入像素颜色的红、绿、蓝分量映射到一个灰度值，该值成为输出中黑色像素的 alpha 分量。此修饰符产生的效果等同于使用带有 `luminanceToAlpha` type 属性的 `feColorMatrix` 滤镜图元，如 [https://www.w3.org/TR/SVG2/] 规范中所定义。

以下示例将 `Palette` 视图定义为一系列矩形，每个矩形由具有特定白色值的 [Color](../Color.zh-Hans.md) 组成，然后在蓝色背景上显示调色板的两个版本：

```swift
struct Palette: View {
    var body: some View {
        HStack(spacing: 0) {
            ForEach(0..<10) { index in
                Color(white: Double(index) / Double(9))
                    .frame(width: 20, height: 40)
            }
        }
    }
}

struct LuminanceToAlphaExample: View {
    var body: some View {
        VStack(spacing: 20) {
            Palette()

            Palette()
                .luminanceToAlpha()
        }
        .padding()
        .background(.blue)
    }
}
```

未修改的调色板版本包含从纯黑色到纯白色的矩形，亮度逐渐增加。第二个调色板版本应用了 `luminanceToAlpha()` 修饰符，允许背景以与输入亮度成反比的程度显示出来。

## 颜色变换

- **brightness(_:)**：按指定量提亮此视图。

- **contrast(_:)**：设置此视图中相似颜色之间的对比度和分离度。

- **colorInvert()**：反转此视图中的颜色。

- **colorMultiply(_:)**：为此视图添加颜色乘法效果。

- **saturation(_:)**：调整此视图的颜色饱和度。

- **grayscale(_:)**：为此视图添加灰度效果。

- **hueRotation(_:)**：为此视图应用色调旋转效果。

- **materialActiveAppearance(_:)**：为此视图中的材质设置明确的激活外观。

- **materialActiveAppearance**：材质在其激活状态下应使用的行为，默认值为 `automatic`。

- **MaterialActiveAppearance**：材质激活和非激活状态下的外观行为。


---
source: https://developer.apple.com/documentation/SwiftUI/View/luminanceToAlpha()
crawled: 2025-11-30T21:22:07Z
---

# luminanceToAlpha()

**Instance Method**

Adds a luminance to alpha effect to this view.

## Declaration

```swift
nonisolated func luminanceToAlpha() -> some View

```

## Return Value

A view with the luminance to alpha effect applied.

## Discussion

Use this modifier to create a semitransparent mask, with the opacity of each part of the modified view controlled by the luminance of the corresponding part of the original view. Regions of lower luminance become more transparent, while higher luminance yields greater opacity.

In particular, the modifier maps the red, green, and blue components of each input pixel’s color to a grayscale value, and that value becomes the alpha component of a black pixel in the output. This modifier produces an effect that’s equivalent to using the `feColorMatrix` filter primitive with the `luminanceToAlpha` type attribute, as defined by the [https://www.w3.org/TR/SVG2/] specification.

The example below defines a `Palette` view as a series of rectangles, each composed as a [Color](../Color.zh-Hans.md) with a particular white value, and then displays two versions of the palette over a blue background:

```swift
struct Palette: View {
    var body: some View {
        HStack(spacing: 0) {
            ForEach(0..<10) { index in
                Color(white: Double(index) / Double(9))
                    .frame(width: 20, height: 40)
            }
        }
    }
}

struct LuminanceToAlphaExample: View {
    var body: some View {
        VStack(spacing: 20) {
            Palette()

            Palette()
                .luminanceToAlpha()
        }
        .padding()
        .background(.blue)
    }
}
```

The unmodified version of the palette contains rectangles that range from solid black to solid white, thus with increasing luminance. The second version of the palette, which has the `luminanceToAlpha()` modifier applied, allows the background to show through in an amount that corresponds inversely to the luminance of the input.



## Transforming colors

- **brightness(_:)**: Brightens this view by the specified amount.
- **contrast(_:)**: Sets the contrast and separation between similar colors in this view.
- **colorInvert()**: Inverts the colors in this view.
- **colorMultiply(_:)**: Adds a color multiplication effect to this view.
- **saturation(_:)**: Adjusts the color saturation of this view.
- **grayscale(_:)**: Adds a grayscale effect to this view.
- **hueRotation(_:)**: Applies a hue rotation effect to this view.
- **materialActiveAppearance(_:)**: Sets an explicit active appearance for materials in this view.
- **materialActiveAppearance**: The behavior materials should use for their active state, defaulting to `automatic`.
- **MaterialActiveAppearance**: The behavior for how materials appear active and inactive.

