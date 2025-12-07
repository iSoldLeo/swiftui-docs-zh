--- 来源：https://developer.apple.com/documentation/SwiftUI/ShapeStyle/windowBackground
抓取时间：2025-12-03T06:25:23Z

---

# windowBackground

**类型属性**

适用于应与其包含窗口背景相匹配的元素的样式。

## 声明

```swift
static var windowBackground: WindowBackgroundShapeStyle { get }
```

## 讨论

在 macOS 上，此样式与默认样式 `ShapeStyle.background` 的外观有所不同。它与窗口的默认背景相匹配：在浅色外观中为壁纸色调的浅灰色，在深色外观中为壁纸色调的深灰色。

在 visionOS 上，只能使用 `glassBackgroundEffect` 创建默认的玻璃窗口背景。

有关如何使用形状样式的信息，请参阅 [ShapeStyle](../ShapeStyle.zh-Hans.md)。

## 语义样式

- **foreground**：当前上下文中的前景色样式。

- **background**：当前上下文中的背景色样式。

- **selection**：用于根据平台常规颜色和行为以视觉方式指示选中状态的样式。

- **separator**：适用于前景色分隔线或边框线的样式。

- **tint**：反映当前色调颜色的样式。

- **placeholder**：适用于占位符文本的样式。

- **link**：适用于链接的样式。

- **fill**：用于填充形状的叠加填充样式。


---
source: https://developer.apple.com/documentation/SwiftUI/ShapeStyle/windowBackground
crawled: 2025-12-03T06:25:23Z
---

# windowBackground

**Type Property**

A style appropriate for elements that should match the background of their containing window.

## Declaration

```swift
static var windowBackground: WindowBackgroundShapeStyle { get }
```

## Discussion

On macOS, this has a unique appearance compared to the default `ShapeStyle.background`. It matches the default background of a window: a wallpaper-tinted light gray in the light appearance and a wallpaper-tinted dark gray in the dark appearance.

On visionOS, the default glass window background can only be created using `glassBackgroundEffect`.

For information about how to use shape styles, see [ShapeStyle](../ShapeStyle.zh-Hans.md).

## Semantic styles

- **foreground**: The foreground style in the current context.
- **background**: The background style in the current context.
- **selection**: A style used to visually indicate selection following platform conventional colors and behaviors.
- **separator**: A style appropriate for foreground separator or border lines.
- **tint**: A style that reflects the current tint color.
- **placeholder**: A style appropriate for placeholder text.
- **link**: A style appropriate for links.
- **fill**: An overlay fill style for filling shapes.

