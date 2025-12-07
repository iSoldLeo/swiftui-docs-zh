---
来源：https://developer.apple.com/documentation/SwiftUI/Color/Resolved/init(colorSpace:red:green:blue:opacity:)
抓取时间：2025-12-04T13:15:35Z


# init(colorSpace:red:green:blue:opacity:)

**Initializer**

用红、绿、蓝分量值创建解析颜色。

## 声明

```swift
init(colorSpace: Color.RGBColorSpace = .sRGB, red: Float, green: Float, blue: Float, opacity: Float = 1)
```

## 参数

- **colorSpace**：指定如何解释显示颜色的配置文件。默认值为 [sRGB](../RGBColorSpace/sRGB.zh-Hans.md)。
- **red**：颜色中红色的含量。
- **green**：颜色中绿色的含量。
- **blue**：颜色中蓝色的含量。
- **opacity**：可选的不透明度，范围从 `0` 到 `1`。`0` 表示 100% 透明度，而 `1` 表示 100% 不透明度。默认值为 `1`。

## 讨论

标准 sRGB 色彩空间将每个颜色分量（`red`、`green` 和`blue`）箝制在`0` 到 `1` 的范围内、但 SwiftUI 颜色使用的是扩展的 sRGB 色彩空间，因此您可以使用该范围之外的分量值。这样就可以使用 [sRGB](../RGBColorSpace/sRGB.zh-Hans.md) 或 [sRGBLinear](../RGBColorSpace/sRGBLinear.zh-Hans.md) 色彩空间创建色彩，充分利用支持 [displayP3](../RGBColorSpace/displayP3.zh-Hans.md) 的显示器的更宽色域。


---
source: https://developer.apple.com/documentation/SwiftUI/Color/Resolved/init(colorSpace:red:green:blue:opacity:)
crawled: 2025-12-04T13:15:35Z
---

# init(colorSpace:red:green:blue:opacity:)

**Initializer**

Creates a resolved color from red, green, and blue component values.

## Declaration

```swift
init(colorSpace: Color.RGBColorSpace = .sRGB, red: Float, green: Float, blue: Float, opacity: Float = 1)
```

## Parameters

- **colorSpace**: The profile that specifies how to interpret the color for display. The default is [sRGB](../RGBColorSpace/sRGB.zh-Hans.md).
- **red**: The amount of red in the color.
- **green**: The amount of green in the color.
- **blue**: The amount of blue in the color.
- **opacity**: An optional degree of opacity, given in the range `0` to `1`. A value of `0` means 100% transparency, while a value of `1` means 100% opacity. The default is `1`.

## Discussion

A standard sRGB color space clamps each color component — `red`, `green`, and `blue` — to a range of `0` to `1`, but SwiftUI colors use an extended sRGB color space, so you can use component values outside that range. This makes it possible to create colors using the [sRGB](../RGBColorSpace/sRGB.zh-Hans.md) or [sRGBLinear](../RGBColorSpace/sRGBLinear.zh-Hans.md) color space that make full use of the wider gamut of a diplay that supports [displayP3](../RGBColorSpace/displayP3.zh-Hans.md).

