---
来源： https://developer.apple.com/documentation/SwiftUI/HierarchicalShapeStyle
抓取时间： 2025-12-03T04:53:49Z
---

# 分级形状样式

**Structure**

映射到编号内容样式之一的形状样式。

### 声明

```swift
@frozen struct HierarchicalShapeStyle
```

## 获取分层形状样式

- **primary**：映射到当前内容样式第一层的形状样式。
- **secondary**：映射到当前内容样式第二层的形状样式。
- **tertiary**：映射到当前内容样式第三层的形状样式。
- **quaternary**：映射到当前内容样式第三层的形状样式：映射到当前内容样式第四层的形状样式。

### 类型属性

- **quinary**：映射到当前内容样式第五层的形状样式。

### 支持类型

- **AngularGradient**：角度渐变。
- **EllipticalGradient**：绘制椭圆的径向渐变。
- **LinearGradient**：线性梯度。
- **RadialGradient**：径向梯度。
- **Material**：背景材质类型。
- **ImagePaint**：形状样式，通过重复图像的某个区域来填充形状。
- **HierarchicalShapeStyleModifier**：可应用于分层形状的样式。
- **ForegroundStyle**：当前上下文中的前景样式。
- **BackgroundStyle**：当前上下文中的前景样式：当前上下文中的背景样式。
- **SelectionShapeStyle**：当前上下文中的背景样式：用于按照平台常规颜色和行为直观表示选择的样式。
- **SeparatorShapeStyle**：适合前景分隔线或边界线的样式。
- **TintShapeStyle**：反映当前色调颜色的样式。
- **FillShapeStyle**：显示其中一种叠加填充的形状样式。
- **LinkShapeStyle**：适合链接的样式。
- **PlaceholderTextShapeStyle**：适合链接的样式：适合占位符文本的样式。

## 符合

- 比特可复制
- 可复制
- 可发送
- 可发送元类型
- 形状样式


---
source: https://developer.apple.com/documentation/SwiftUI/HierarchicalShapeStyle
crawled: 2025-12-03T04:53:49Z
---

# HierarchicalShapeStyle

**Structure**

A shape style that maps to one of the numbered content styles.

## Declaration

```swift
@frozen struct HierarchicalShapeStyle
```

## Getting hierarchical shape styles

- **primary**: A shape style that maps to the first level of the current content style.
- **secondary**: A shape style that maps to the second level of the current content style.
- **tertiary**: A shape style that maps to the third level of the current content style.
- **quaternary**: A shape style that maps to the fourth level of the current content style.

## Type Properties

- **quinary**: A shape style that maps to the fifth level of the current content style.

## Supporting types

- **AngularGradient**: An angular gradient.
- **EllipticalGradient**: A radial gradient that draws an ellipse.
- **LinearGradient**: A linear gradient.
- **RadialGradient**: A radial gradient.
- **Material**: A background material type.
- **ImagePaint**: A shape style that fills a shape by repeating a region of an image.
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

- BitwiseCopyable
- Copyable
- Sendable
- SendableMetatype
- ShapeStyle

