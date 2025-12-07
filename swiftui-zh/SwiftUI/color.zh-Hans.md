--- 来源：https://developer.apple.com/documentation/swiftui/color

抓取时间：2025-12-04T11:33:58Z

---

# 颜色

**Structure**

一种能够适应特定上下文的颜色表示。

## 声明

```swift
@frozen struct Color
```

## 概述

您可以通过以下几种方式创建颜色：

- 从资源目录加载颜色：

```swift
let aqua = Color("aqua") // Looks in your app's main bundle by default.
```

- 指定颜色分量值，例如红色、绿色和蓝色；色调、饱和度和亮度；或白色级别：

```swift
let skyBlue = Color(red: 0.4627, green: 0.8392, blue: 1.0)
let lemonYellow = Color(hue: 0.1639, saturation: 1, brightness: 1)
let steelGray = Color(white: 0.4745)
```

- 从另一个颜色创建颜色实例，例如 [doc://com.apple.documentation/documentation/UIKit/UIColor] 或 [doc://com.apple.documentation/documentation/AppKit/NSColor]：

```swift
#if os(iOS)
let linkColor = Color(uiColor: .link)
#elseif os(macOS)
let linkColor = Color(nsColor: .linkColor)
#endif
```

- 使用预定义调色板中的一种颜色，例如 [black](ShapeStyle/black.zh-Hans.md)、[green](ShapeStyle/green.zh-Hans.md) 和 [purple](ShapeStyle/purple.zh-Hans.md)。

某些视图修饰符可以接受颜色作为参数。例如，[foregroundStyle(_:)](View/foregroundStyle.zh-Hans.md) 使用您提供的颜色来设置视图元素（例如文本）的前景色，或者 [doc://com.apple.documentation/design/Human-Interface-Guidelines/sf-symbols]：

```swift
Image(systemName: "leaf.fill")
    .foregroundStyle(Color.green)
```

由于 SwiftUI 将颜色视为 [View](View.zh-Hans.md) 实例，因此您也可以直接将它们添加到视图层次结构中。例如，您可以使用上面定义的颜色在太阳图像下方叠加一个矩形：

```swift
ZStack {
    skyBlue
    Image(systemName: "sun.max.fill")
        .foregroundStyle(lemonYellow)
}
.frame(width: 200, height: 100)
```

用作视图的颜色会扩展以填充其所分配的所有空间，如上例中由外层元素 [ZStack](ZStack.zh-Hans.md) 的框架定义：

SwiftUI 仅在特定环境中使用颜色之前将其解析为具体值。这使得系统定义的颜色或从资源目录加载的颜色能够根据上下文呈现。例如，一种颜色可以有不同的浅色和深色变体，系统会在渲染时从中选择。

## 创建颜色

- **init(_:bundle:)**：根据您指定的名称从颜色集中创建颜色。

- **init(_:)**：使用已解析颜色指定的值创建常量颜色。

- **resolve(in:)**：根据当前的 `context` 值，将此颜色解析为已解析的颜色。

## 根据分量值创建颜色

- **init(hue:saturation:brightness:opacity:)**：根据色调、饱和度和亮度值创建常量颜色。

- **init(_:white:opacity:)**：创建常量灰度颜色。

- **init(_:red:green:blue:opacity:)**：根据红色、绿色和蓝色分量值创建常量颜色。

- **Color.RGBColorSpace**：指定如何解释颜色值以进行显示的配置文件。

## 根据其他颜色创建颜色

- **init(uiColor:)**：根据 UIKit 颜色创建颜色。

- **init(nsColor:)**：根据 AppKit 颜色创建颜色。

- **init(cgColor:)**：根据 Core Graphics 颜色创建颜色。

## 获取标准颜色

- **black**：适用于 UI 元素的黑色。

- **blue**：适用于 UI 元素的上下文相关蓝色。

- **brown**：适用于 UI 元素的上下文相关棕色。

- **clear**：适用于 UI 元素的透明色。

- **cyan**：适用于 UI 元素的上下文相关青色。

- **gray**：适用于 UI 元素的上下文相关灰色。

- **green**：适用于 UI 元素的上下文相关绿色。

- **indigo**：适用于用户界面元素的上下文相关靛蓝色。

- **mint**：适用于用户界面元素的上下文相关薄荷绿。

- **orange**：适用于用户界面元素的上下文相关橙色。

- **pink**：适用于用户界面元素的上下文相关粉色。

- **purple**：适用于用户界面元素的上下文相关紫色。

- **red**：适用于用户界面元素的上下文相关红色。

- **teal**：适用于用户界面元素的上下文相关青色。

- **white**：适用于用户界面元素的白色。

- **yellow**：一种上下文相关的黄色，适用于用户界面元素。

## 获取语义颜色

- **accentColor**：一种反映系统或应用程序强调色的颜色。

- **primary**：用于主要内容的颜色。

- **secondary**：用于辅助内容的颜色。

## 修改颜色

- **opacity(_:)**：将颜色的不透明度乘以指定的数值。

- **gradient**：返回颜色 `self` 的标准渐变。

- **mix(with:by:in:)**：返回一个与 `rhs` 混合后的版本，混合比例由 `fraction` 指定。

- **exposureAdjust(_:)**：返回一个应用了曝光调整的新颜色。

- **headroom(_:)**：创建一个具有指定 HDR 内容动态范围的新颜色。

## 处理高动态范围 (HDR) 颜色

- **resolveHDR(in:)**：根据一组环境值，将此颜色评估为具有内容动态范围的解析颜色。

- **Color.ResolvedHDR**：一个具体的颜色值，包含 HDR 动态范围信息。

## 描述颜色

- **description**：颜色的文本表示。

## 比较颜色

- **==(_:_:)**：指示两种颜色是否相等。

- **hash(into:)**：将颜色的基本组成部分代入给定的哈希函数进行哈希处理。

## 已弃用的符号

- **cgColor**：颜色的 Core Graphics 表示（如果可用）。

## 默认实现

- **ShapeStyle 实现**

- **Transferable 实现**

## 设置颜色

- **tint(_:)**：设置此视图中的色调颜色。

## 符合以下协议

- Copyable

- CustomStringConvertible

- Equatable

- Hashable

- Sendable

- SendableMetatype

- ShapeStyle

- Transferable

- View


---
source: https://developer.apple.com/documentation/swiftui/color
crawled: 2025-12-04T11:33:58Z
---

# Color

**Structure**

A representation of a color that adapts to a given context.

## Declaration

```swift
@frozen struct Color
```

## Overview

You can create a color in one of several ways:

- Load a color from an Asset Catalog:

```swift
let aqua = Color("aqua") // Looks in your app's main bundle by default.
```
- Specify component values, like red, green, and blue; hue, saturation, and brightness; or white level:

```swift
let skyBlue = Color(red: 0.4627, green: 0.8392, blue: 1.0)
let lemonYellow = Color(hue: 0.1639, saturation: 1, brightness: 1)
let steelGray = Color(white: 0.4745)
```
- Create a color instance from another color, like a [doc://com.apple.documentation/documentation/UIKit/UIColor] or an [doc://com.apple.documentation/documentation/AppKit/NSColor]:

```swift
#if os(iOS)
let linkColor = Color(uiColor: .link)
#elseif os(macOS)
let linkColor = Color(nsColor: .linkColor)
#endif
```
- Use one of a palette of predefined colors, like [black](ShapeStyle/black.zh-Hans.md), [green](ShapeStyle/green.zh-Hans.md), and [purple](ShapeStyle/purple.zh-Hans.md).

Some view modifiers can take a color as an argument. For example, [foregroundStyle(_:)](View/foregroundStyle.zh-Hans.md) uses the color you provide to set the foreground color for view elements, like text or [doc://com.apple.documentation/design/Human-Interface-Guidelines/sf-symbols]:

```swift
Image(systemName: "leaf.fill")
    .foregroundStyle(Color.green)
```



Because SwiftUI treats colors as [View](View.zh-Hans.md) instances, you can also directly add them to a view hierarchy. For example, you can layer a rectangle beneath a sun image using colors defined above:

```swift
ZStack {
    skyBlue
    Image(systemName: "sun.max.fill")
        .foregroundStyle(lemonYellow)
}
.frame(width: 200, height: 100)
```

A color used as a view expands to fill all the space it’s given, as defined by the frame of the enclosing [ZStack](ZStack.zh-Hans.md) in the above example:



SwiftUI only resolves a color to a concrete value just before using it in a given environment. This enables a context-dependent appearance for system defined colors, or those that you load from an Asset Catalog. For example, a color can have distinct light and dark variants that the system chooses from at render time.

## Creating a color

- **init(_:bundle:)**: Creates a color from a color set that you indicate by name.
- **init(_:)**: Creates a constant color with the values specified by the resolved color.
- **resolve(in:)**: Evaluates this color to a resolved color given the current `context`.

## Creating a color from component values

- **init(hue:saturation:brightness:opacity:)**: Creates a constant color from hue, saturation, and brightness values.
- **init(_:white:opacity:)**: Creates a constant grayscale color.
- **init(_:red:green:blue:opacity:)**: Creates a constant color from red, green, and blue component values.
- **Color.RGBColorSpace**: A profile that specifies how to interpret a color value for display.

## Creating a color from another color

- **init(uiColor:)**: Creates a color from a UIKit color.
- **init(nsColor:)**: Creates a color from an AppKit color.
- **init(cgColor:)**: Creates a color from a Core Graphics color.

## Getting standard colors

- **black**: A black color suitable for use in UI elements.
- **blue**: A context-dependent blue color suitable for use in UI elements.
- **brown**: A context-dependent brown color suitable for use in UI elements.
- **clear**: A clear color suitable for use in UI elements.
- **cyan**: A context-dependent cyan color suitable for use in UI elements.
- **gray**: A context-dependent gray color suitable for use in UI elements.
- **green**: A context-dependent green color suitable for use in UI elements.
- **indigo**: A context-dependent indigo color suitable for use in UI elements.
- **mint**: A context-dependent mint color suitable for use in UI elements.
- **orange**: A context-dependent orange color suitable for use in UI elements.
- **pink**: A context-dependent pink color suitable for use in UI elements.
- **purple**: A context-dependent purple color suitable for use in UI elements.
- **red**: A context-dependent red color suitable for use in UI elements.
- **teal**: A context-dependent teal color suitable for use in UI elements.
- **white**: A white color suitable for use in UI elements.
- **yellow**: A context-dependent yellow color suitable for use in UI elements.

## Getting semantic colors

- **accentColor**: A color that reflects the accent color of the system or app.
- **primary**: The color to use for primary content.
- **secondary**: The color to use for secondary content.

## Modifying a color

- **opacity(_:)**: Multiplies the opacity of the color by the given amount.
- **gradient**: Returns the standard gradient for the color `self`.
- **mix(with:by:in:)**: Returns a version of self mixed with `rhs` by the amount specified by `fraction`.
- **exposureAdjust(_:)**: Returns a new color with an exposure adjustment applied.
- **headroom(_:)**: Creates a new color with specified HDR content headroom.

## Working with high dynamic range (HDR) colors

- **resolveHDR(in:)**: Evaluates this color to a resolved color with content headroom, given a set of environment values.
- **Color.ResolvedHDR**: A concrete color value, including HDR headroom information.

## Describing a color

- **description**: A textual representation of the color.

## Comparing colors

- **==(_:_:)**: Indicates whether two colors are equal.
- **hash(into:)**: Hashes the essential components of the color by feeding them into the given hash function.

## Deprecated symbols

- **cgColor**: A Core Graphics representation of the color, if available.

## Default Implementations

- **ShapeStyle Implementations**
- **Transferable Implementations**

## Setting a color

- **tint(_:)**: Sets the tint color within this view.

## Conforms To

- Copyable
- CustomStringConvertible
- Equatable
- Hashable
- Sendable
- SendableMetatype
- ShapeStyle
- Transferable
- View

