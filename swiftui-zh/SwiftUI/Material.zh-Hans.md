--- 来源：https://developer.apple.com/documentation/SwiftUI/Material
抓取时间：2025-12-02T17:04:43Z

---

# Material

**Structure**

一种背景材质类型。

## 声明

```swift
struct Material
```

## 概述

您可以通过添加带有 [background(_:ignoresSafeAreaEdges:)](View/background___ignoresSafeAreaEdges.zh-Hans.md) 修饰符的材质，为位于另一个视图后面的视图应用模糊效果：

```swift
ZStack {
    Color.teal
    Label("Flag", systemImage: "flag.fill")
        .padding()
        .background(.regularMaterial)
}
```

在上面的示例中，[ZStack](ZStack.zh-Hans.md) 在颜色 [teal](ShapeStyle/teal.zh-Hans.md) 之上叠加了 [Label](Label.zh-Hans.md)。背景修改器会在标签下方插入常规材质，模糊标签（包括其内边距）覆盖的背景部分：

材质并非视图，但添加材质就像在修改后的视图与其背景之间插入一个半透明图层：

材质提供的模糊效果并非简单的透明度。它使用平台特定的混合模式，产生类似磨砂玻璃的效果。对于复杂的背景（例如图像），这种效果会更加明显：

```swift
ZStack {
    Image("chili_peppers")
        .resizable()
        .aspectRatio(contentMode: .fit)
    Label("Flag", systemImage: "flag.fill")
        .padding()
        .background(.regularMaterial)
}
```

对于物理材质，背景颜色透过的程度取决于材质的厚度。效果也会随着材质的明暗程度而变化：

如果需要材质具有特定形状，可以使用 [background(_:in:fillStyle:)](View/background___in_fillStyle.zh-Hans.md) 修改器。例如，您可以创建带有圆角的材质：

```swift
ZStack {
    Color.teal
    Label("Flag", systemImage: "flag.fill")
        .padding()
        .background(.regularMaterial, in: RoundedRectangle(cornerRadius: 8))
}
```

添加材质后，前景元素会呈现鲜艳度，这是一种根据上下文混合前景和背景色的效果，可以提高对比度。但是，使用 [foregroundStyle(_:)](View/foregroundStyle.zh-Hans.md) 设置自定义前景样式（不包括层级样式，例如 [secondary-swift.type.property](ShapeStyle/secondary-swift_type_property.zh-Hans.md)）会禁用鲜艳度。

## 获取材质类型

- **ultraThin**：半透明材质。

- **thin**：半透明材质。

- **regular**：半透明材质。

- **thick**：不透明材质。

- **ultraThick**：一种几乎不透明的材质。

- **bar**：一种与系统工具栏样式相匹配的材质。

## 实例方法

- **materialActiveAppearance(_:)**：为该材质设置显式激活外观。

## 支持的类型

- **AngularGradient**：一种角度渐变。

- **EllipticalGradient**：一种绘制椭圆的径向渐变。

- **LinearGradient**：一种线性渐变。

- **RadialGradient**：一种径向渐变。

- **ImagePaint**：一种形状样式，通过重复图像区域来填充形状。

- **HierarchicalShapeStyle**：映射到某个编号内容样式的形状样式。

- **HierarchicalShapeStyleModifier**：可应用于层级形状的样式。

- **ForegroundStyle**：当前上下文中的前景色样式。

- **BackgroundStyle**：当前上下文中的背景色样式。

- **SelectionShapeStyle**：用于根据平台常规颜色和行为以视觉方式指示选中状态的样式。

- **SeparatorShapeStyle**：适用于前景色分隔符或边框线的样式。

- **TintShapeStyle**：反映当前色调颜色的样式。

- **FillShapeStyle**：显示某个叠加填充的形状样式。

- **LinkShapeStyle**：适用于链接的样式。

- **PlaceholderTextShapeStyle**：适用于占位符文本的样式。

## 符合以下规范

- Copyable

- Sendable

- SendableMetatype

- ShapeStyle


---
source: https://developer.apple.com/documentation/SwiftUI/Material
crawled: 2025-12-02T17:04:43Z
---

# Material

**Structure**

A background material type.

## Declaration

```swift
struct Material
```

## Overview

You can apply a blur effect to a view that appears behind another view by adding a material with the [background(_:ignoresSafeAreaEdges:)](View/background___ignoresSafeAreaEdges.zh-Hans.md) modifier:

```swift
ZStack {
    Color.teal
    Label("Flag", systemImage: "flag.fill")
        .padding()
        .background(.regularMaterial)
}
```

In the example above, the [ZStack](ZStack.zh-Hans.md) layers a [Label](Label.zh-Hans.md) on top of the color [teal](ShapeStyle/teal.zh-Hans.md). The background modifier inserts the regular material below the label, blurring the part of the background that the label — including its padding — covers:



A material isn’t a view, but adding a material is like inserting a translucent layer between the modified view and its background:



The blurring effect provided by the material isn’t simple opacity. Instead, it uses a platform-specific blending that produces an effect that resembles heavily frosted glass. You can see this more easily with a complex background, like an image:

```swift
ZStack {
    Image("chili_peppers")
        .resizable()
        .aspectRatio(contentMode: .fit)
    Label("Flag", systemImage: "flag.fill")
        .padding()
        .background(.regularMaterial)
}
```



For physical materials, the degree to which the background colors pass through depends on the thickness. The effect also varies with light and dark appearance:



If you need a material to have a particular shape, you can use the [background(_:in:fillStyle:)](View/background___in_fillStyle.zh-Hans.md) modifier. For example, you can create a material with rounded corners:

```swift
ZStack {
    Color.teal
    Label("Flag", systemImage: "flag.fill")
        .padding()
        .background(.regularMaterial, in: RoundedRectangle(cornerRadius: 8))
}
```



When you add a material, foreground elements exhibit vibrancy, a context-specific blend of the foreground and background colors that improves contrast. However using [foregroundStyle(_:)](View/foregroundStyle.zh-Hans.md) to set a custom foreground style — excluding the hierarchical styles, like [secondary-swift.type.property](ShapeStyle/secondary-swift_type_property.zh-Hans.md) — disables vibrancy.



## Getting material types

- **ultraThin**: A mostly translucent material.
- **thin**: A material that’s more translucent than opaque.
- **regular**: A material that’s somewhat translucent.
- **thick**: A material that’s more opaque than translucent.
- **ultraThick**: A mostly opaque material.
- **bar**: A material matching the style of system toolbars.

## Instance Methods

- **materialActiveAppearance(_:)**: Sets an explicit active appearance for this material.

## Supporting types

- **AngularGradient**: An angular gradient.
- **EllipticalGradient**: A radial gradient that draws an ellipse.
- **LinearGradient**: A linear gradient.
- **RadialGradient**: A radial gradient.
- **ImagePaint**: A shape style that fills a shape by repeating a region of an image.
- **HierarchicalShapeStyle**: A shape style that maps to one of the numbered content styles.
- **HierarchicalShapeStyleModifier**: Styles that you can apply to hierarchical shapes.
- **ForegroundStyle**: The foreground style in the current context.
- **BackgroundStyle**: The background style in the current context.
- **SelectionShapeStyle**: A style used to visually indicate selection following platform conventional colors and behaviors.
- **SeparatorShapeStyle**: A style appropriate for foreground separator or border lines.
- **TintShapeStyle**: A style that reflects the current tint color.
- **FillShapeStyle**: A shape style that displays one of the overlay fills.
- **LinkShapeStyle**: A style appropriate for links.
- **PlaceholderTextShapeStyle**: A style appropriate for placeholder text.

## Conforms To

- Copyable
- Sendable
- SendableMetatype
- ShapeStyle

