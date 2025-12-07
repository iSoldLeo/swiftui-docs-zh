---
来源: https://developer.apple.com/documentation/SwiftUI/Color/init(_:white:opacity:)
抓取时间： 2025-12-03T05:39:31Z
---

# init(_:white:opacity:)

**Initializer**

创建恒定的灰度颜色。

## 声明

```swift
init(_ colorSpace: Color.RGBColorSpace = .sRGB, white: Double, opacity: Double = 1)
```

## 参数

- **colorSpace**：指定如何解释显示颜色的配置文件。默认值为 [sRGB](RGBColorSpace/sRGB.zh-Hans.md)。
- **white**：表示颜色白度的数值，数值越大越接近 100% 白色，数值越小越接近 100% 黑色。
- **opacity**：可选的不透明度，取值范围为 `0` 至 `1`。`0` 表示 100% 透明度，而 `1` 表示 100% 不透明度。默认值为 `1`。

### 讨论

该初始化程序会创建一个常量颜色，不会根据上下文而改变。例如，它不像各种系统定义的颜色或使用 [init(_:bundle:)](init___bundle.zh-Hans.md) 从资产目录载入的颜色那样，有明显的明暗显示。

标准 sRGB 色彩空间将`white`分量限制在`0`到`1`的范围内，但 SwiftUI 颜色使用的是扩展 sRGB 色彩空间，因此可以使用该范围以外的分量值。这样就可以使用 [sRGB](RGBColorSpace/sRGB.zh-Hans.md) 或 [sRGBLinear](RGBColorSpace/sRGBLinear.zh-Hans.md) 色彩空间创建色彩，充分利用支持 [displayP3](RGBColorSpace/displayP3.zh-Hans.md) 的显示器的更宽色域。

##从分量值创建颜色

- **init(hue:saturation:brightness:opacity:)**：从色相、饱和度和亮度值创建恒定颜色。
- **init(_:red:green:blue:opacity:)**：根据红、绿、蓝分量值创建恒定颜色。
- **Color.RGBColorSpace**：指定如何解释显示色彩值的配置文件。


---
source: https://developer.apple.com/documentation/SwiftUI/Color/init(_:white:opacity:)
crawled: 2025-12-03T05:39:31Z
---

# init(_:white:opacity:)

**Initializer**

Creates a constant grayscale color.

## Declaration

```swift
init(_ colorSpace: Color.RGBColorSpace = .sRGB, white: Double, opacity: Double = 1)
```

## Parameters

- **colorSpace**: The profile that specifies how to interpret the color for display. The default is [sRGB](RGBColorSpace/sRGB.zh-Hans.md).
- **white**: A value that indicates how white the color is, with higher values closer to 100% white, and lower values closer to 100% black.
- **opacity**: An optional degree of opacity, given in the range `0` to `1`. A value of `0` means 100% transparency, while a value of `1` means 100% opacity. The default is `1`.

## Discussion

This initializer creates a constant color that doesn’t change based on context. For example, it doesn’t have distinct light and dark appearances, unlike various system-defined colors, or a color that you load from an Asset Catalog with [init(_:bundle:)](init___bundle.zh-Hans.md).

A standard sRGB color space clamps the `white` component to a range of `0` to `1`, but SwiftUI colors use an extended sRGB color space, so you can use component values outside that range. This makes it possible to create colors using the [sRGB](RGBColorSpace/sRGB.zh-Hans.md) or [sRGBLinear](RGBColorSpace/sRGBLinear.zh-Hans.md) color space that make full use of the wider gamut of a diplay that supports [displayP3](RGBColorSpace/displayP3.zh-Hans.md).

## Creating a color from component values

- **init(hue:saturation:brightness:opacity:)**: Creates a constant color from hue, saturation, and brightness values.
- **init(_:red:green:blue:opacity:)**: Creates a constant color from red, green, and blue component values.
- **Color.RGBColorSpace**: A profile that specifies how to interpret a color value for display.

