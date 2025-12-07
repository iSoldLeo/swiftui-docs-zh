---
来源：https://developer.apple.com/documentation/SwiftUI/Color/init(_:红色:绿色:蓝色:不透明度:)
抓取时间：2025-12-01T10:28:41Z


# init(_:red:green:blue:opacity:)

**Initializer**

用红色、绿色和蓝色分量值创建常量颜色。

## 声明

```swift
init(_ colorSpace: Color.RGBColorSpace = .sRGB, red: Double, green: Double, blue: Double, opacity: Double = 1)
```

## 参数

- **colorSpace**：指定如何解释显示颜色的配置文件。默认值为 [sRGB](RGBColorSpace/sRGB.zh-Hans.md)。
- **red**：颜色中红色的含量。
- **green**：颜色中绿色的含量。
- **blue**：颜色中蓝色的含量。
- **opacity**：可选的不透明度，范围为 `0` 至 `1`。`0` 表示 100% 透明度，而 `1` 表示 100% 不透明度。默认值为 `1`。

## 讨论

该初始化程序会创建一个常量颜色，不会根据上下文而改变。例如，它不像各种系统定义的颜色，或使用 [init(_:bundle:)](init___bundle.zh-Hans.md) 从资产目录载入的颜色那样，有明显的明暗显示。

标准 sRGB 色彩空间将每个色彩分量（`red`、`green` 和`blue`）限制在`0` 到`1` 的范围内、但 SwiftUI 颜色使用的是扩展的 sRGB 色彩空间，因此您可以使用该范围之外的分量值。这样就可以使用 [sRGB](RGBColorSpace/sRGB.zh-Hans.md) 或 [sRGBLinear](RGBColorSpace/sRGBLinear.zh-Hans.md) 色彩空间创建色彩，充分利用支持 [displayP3](RGBColorSpace/displayP3.zh-Hans.md) 的显示器的更宽色域。

##从分量值创建颜色

- **init(hue:saturation:brightness:opacity:)**：从色相、饱和度和亮度值创建恒定颜色。
- **init(_:white:opacity:)**：创建恒定的灰度颜色。
- **Color.RGBColorSpace**：指定如何解释显示色彩值的配置文件。


---
source: https://developer.apple.com/documentation/SwiftUI/Color/init(_:red:green:blue:opacity:)
crawled: 2025-12-01T10:28:41Z
---

# init(_:red:green:blue:opacity:)

**Initializer**

Creates a constant color from red, green, and blue component values.

## Declaration

```swift
init(_ colorSpace: Color.RGBColorSpace = .sRGB, red: Double, green: Double, blue: Double, opacity: Double = 1)
```

## Parameters

- **colorSpace**: The profile that specifies how to interpret the color for display. The default is [sRGB](RGBColorSpace/sRGB.zh-Hans.md).
- **red**: The amount of red in the color.
- **green**: The amount of green in the color.
- **blue**: The amount of blue in the color.
- **opacity**: An optional degree of opacity, given in the range `0` to `1`. A value of `0` means 100% transparency, while a value of `1` means 100% opacity. The default is `1`.

## Discussion

This initializer creates a constant color that doesn’t change based on context. For example, it doesn’t have distinct light and dark appearances, unlike various system-defined colors, or a color that you load from an Asset Catalog with [init(_:bundle:)](init___bundle.zh-Hans.md).

A standard sRGB color space clamps each color component — `red`, `green`, and `blue` — to a range of `0` to `1`, but SwiftUI colors use an extended sRGB color space, so you can use component values outside that range. This makes it possible to create colors using the [sRGB](RGBColorSpace/sRGB.zh-Hans.md) or [sRGBLinear](RGBColorSpace/sRGBLinear.zh-Hans.md) color space that make full use of the wider gamut of a diplay that supports [displayP3](RGBColorSpace/displayP3.zh-Hans.md).

## Creating a color from component values

- **init(hue:saturation:brightness:opacity:)**: Creates a constant color from hue, saturation, and brightness values.
- **init(_:white:opacity:)**: Creates a constant grayscale color.
- **Color.RGBColorSpace**: A profile that specifies how to interpret a color value for display.

