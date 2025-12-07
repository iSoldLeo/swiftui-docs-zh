---
来源： https://developer.apple.com/documentation/SwiftUI/Color/RGBColorSpace
抓取时间： 2025-12-03T05:39:33Z
---

# Color.RGBColorSpace

**Enumeration**

指定如何解释显示颜色值的配置文件。

## 声明

```swift
enum RGBColorSpace
```

## 获取色彩空间

- **Color.RGBColorSpace.sRGB**：扩展的红、绿、蓝 (sRGB) 色彩空间。
- **Color.RGBColorSpace.sRGBLinear**：具有线性传递函数的扩展 sRGB 色彩空间。
- **Color.RGBColorSpace.displayP3**：显示 P3 色彩空间。

## 从分量值创建颜色

- **init(hue:saturation:brightness:opacity:)**：从色相、饱和度和亮度值创建恒定颜色。
- **init(_:white:opacity:)**：创建恒定的灰度颜色。
- **init(_:red:green:blue:opacity:)**：用红、绿、蓝分量值创建恒定颜色。

## 符合

- 可复制
- 等价
- 可散列
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/Color/RGBColorSpace
crawled: 2025-12-03T05:39:33Z
---

# Color.RGBColorSpace

**Enumeration**

A profile that specifies how to interpret a color value for display.

## Declaration

```swift
enum RGBColorSpace
```

## Getting color spaces

- **Color.RGBColorSpace.sRGB**: The extended red, green, blue (sRGB) color space.
- **Color.RGBColorSpace.sRGBLinear**: The extended sRGB color space with a linear transfer function.
- **Color.RGBColorSpace.displayP3**: The Display P3 color space.

## Creating a color from component values

- **init(hue:saturation:brightness:opacity:)**: Creates a constant color from hue, saturation, and brightness values.
- **init(_:white:opacity:)**: Creates a constant grayscale color.
- **init(_:red:green:blue:opacity:)**: Creates a constant color from red, green, and blue component values.

## Conforms To

- Copyable
- Equatable
- Hashable
- Sendable
- SendableMetatype

