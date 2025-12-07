---
来源：https://developer.apple.com/documentation/SwiftUI/Color/init(色调:饱和度:亮度:不透明度:)
抓取时间：2025-12-01T10:28:39Z
---

# init(hue:saturation:brightness:opacity:)

**Initializer**

用色相、饱和度和亮度值创建常量颜色。

## 声明

```swift
init(hue: Double, saturation: Double, brightness: Double, opacity: Double = 1)
```

## 参数

- **hue**：`0`至`1`范围内的一个值，映射到 0° 至 360° 的角度，表示色轮上的一个色阶。
- **saturation**：在 `0` 到 `1` 范围内的一个值，表示色相对颜色的影响程度。如果`0` 值为 `0`，则消除了色相的影响，呈现灰色。随着数值的增加，色相会变得更加突出。
- **brightness**：在 `0` 到 `1` 范围内的一个值，表示颜色的亮度。如果值为 `0`，则无论其他成分如何，颜色都是黑色。随着分量的增加，颜色也会变亮。
- **opacity**：可选的不透明度，范围为 `0` 至 `1`。`0` 表示 100% 透明度，而 `1` 表示 100% 不透明度。默认值为 `1`。

### 讨论

该初始化程序会创建一个常量颜色，不会根据上下文而改变。例如，它不像各种系统定义的颜色，或使用 [init(_:bundle:)](init___bundle.zh-Hans.md) 从资产目录载入的颜色那样，有明显的明暗显示。

## 从组件值创建颜色

- **init(_:white:opacity:)**：创建恒定的灰度颜色。
- **init(_:red:green:blue:opacity:)**：用红、绿、蓝分量值创建恒定颜色。
- **Color.RGBColorSpace**：指定如何解释显示色彩值的配置文件。


---
source: https://developer.apple.com/documentation/SwiftUI/Color/init(hue:saturation:brightness:opacity:)
crawled: 2025-12-01T10:28:39Z
---

# init(hue:saturation:brightness:opacity:)

**Initializer**

Creates a constant color from hue, saturation, and brightness values.

## Declaration

```swift
init(hue: Double, saturation: Double, brightness: Double, opacity: Double = 1)
```

## Parameters

- **hue**: A value in the range `0` to `1` that maps to an angle from 0° to 360° to represent a shade on the color wheel.
- **saturation**: A value in the range `0` to `1` that indicates how strongly the hue affects the color. A value of `0` removes the effect of the hue, resulting in gray. As the value increases, the hue becomes more prominent.
- **brightness**: A value in the range `0` to `1` that indicates how bright a color is. A value of `0` results in black, regardless of the other components. The color lightens as you increase this component.
- **opacity**: An optional degree of opacity, given in the range `0` to `1`. A value of `0` means 100% transparency, while a value of `1` means 100% opacity. The default is `1`.

## Discussion

This initializer creates a constant color that doesn’t change based on context. For example, it doesn’t have distinct light and dark appearances, unlike various system-defined colors, or a color that you load from an Asset Catalog with [init(_:bundle:)](init___bundle.zh-Hans.md).

## Creating a color from component values

- **init(_:white:opacity:)**: Creates a constant grayscale color.
- **init(_:red:green:blue:opacity:)**: Creates a constant color from red, green, and blue component values.
- **Color.RGBColorSpace**: A profile that specifies how to interpret a color value for display.

