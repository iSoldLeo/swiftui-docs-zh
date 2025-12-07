---
来源： https://developer.apple.com/documentation/SwiftUI/WindowBackgroundShapeStyle
抓取时间： 2025-12-03T06:25:31Z
---

# WindowBackgroundShapeStyle

**Structure**

适合与包含窗口的背景相匹配的元素的样式。

## 声明

```swift
struct WindowBackgroundShapeStyle
```

## 创建样式

- **init()**：创建新的窗口背景形状样式实例。

## 支持类型

- **AngularGradient**：角度渐变。
- **EllipticalGradient**：绘制椭圆的径向渐变。
- **LinearGradient**：线性梯度。
- **RadialGradient**：径向梯度。
- **Material**：背景材质类型。
- **ImagePaint**：形状样式，通过重复图像的某个区域来填充形状。
- **HierarchicalShapeStyle**：映射到编号内容样式之一的形状样式。
- **HierarchicalShapeStyleModifier**：可应用于分层形状的样式。
- **ForegroundStyle**：当前上下文中的前景样式。
- **BackgroundStyle**：当前上下文中的前景样式：当前上下文中的背景样式。
- **SelectionShapeStyle**：当前上下文中的背景样式：用于按照平台常规颜色和行为直观表示选择的样式。
- **SeparatorShapeStyle**：适合前景分隔线或边界线的样式。
- **TintShapeStyle**：反映当前色调颜色的样式。
- **FillShapeStyle**：显示其中一种叠加填充的形状样式。
- **LinkShapeStyle**：适合链接的样式。

## 符合

- 可发送
- 可发送元类型
- 形状样式


---
source: https://developer.apple.com/documentation/SwiftUI/WindowBackgroundShapeStyle
crawled: 2025-12-03T06:25:31Z
---

# WindowBackgroundShapeStyle

**Structure**

A style appropriate for elements that should match the background of their containing window.

## Declaration

```swift
struct WindowBackgroundShapeStyle
```

## Creating the style

- **init()**: Creates a new window background shape style instance.

## Supporting types

- **AngularGradient**: An angular gradient.
- **EllipticalGradient**: A radial gradient that draws an ellipse.
- **LinearGradient**: A linear gradient.
- **RadialGradient**: A radial gradient.
- **Material**: A background material type.
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

## Conforms To

- Sendable
- SendableMetatype
- ShapeStyle

