--- 来源：https://developer.apple.com/documentation/SwiftUI/ShapeStyle/tint
抓取时间：2025-12-03T06:25:20Z

---

# tint

**类型属性**

反映当前色调颜色的样式。

## 声明

```swift
static var tint: TintShapeStyle { get }
```

## 讨论

您可以使用 `tint(_:)` 修饰符设置色调颜色。如果没有显式设置色调，则色调将源自应用程序的强调色。

## 语义样式

- **foreground**：当前上下文中的前景色样式。

- **background**：当前上下文中的背景色样式。

- **selection**：一种用于根据平台常规颜色和行为以视觉方式指示选中状态的样式。

- **separator**：一种适用于前景分隔符或边框线的样式。

- **placeholder**：一种适用于占位符文本的样式。

- **link**：一种适用于链接的样式。

- **fill**：一种用于填充形状的覆盖填充样式。

- **windowBackground**：一种适用于应与其包含窗口背景相匹配的元素的样式。


---
source: https://developer.apple.com/documentation/SwiftUI/ShapeStyle/tint
crawled: 2025-12-03T06:25:20Z
---

# tint

**Type Property**

A style that reflects the current tint color.

## Declaration

```swift
static var tint: TintShapeStyle { get }
```

## Discussion

You can set the tint color with the `tint(_:)` modifier. If no explicit tint is set, the tint is derived from the app’s accent color.

## Semantic styles

- **foreground**: The foreground style in the current context.
- **background**: The background style in the current context.
- **selection**: A style used to visually indicate selection following platform conventional colors and behaviors.
- **separator**: A style appropriate for foreground separator or border lines.
- **placeholder**: A style appropriate for placeholder text.
- **link**: A style appropriate for links.
- **fill**: An overlay fill style for filling shapes.
- **windowBackground**: A style appropriate for elements that should match the background of their containing window.

