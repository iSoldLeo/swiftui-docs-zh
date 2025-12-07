--- 来源：https://developer.apple.com/documentation/SwiftUI/ShapeStyle/foreground

抓取时间：2025-12-03T06:25:17Z

---

# 前景样式

**类型属性**

当前上下文中的前景样式。

## 声明

```swift
static var foreground: ForegroundStyle { get }
```

## 说明

访问此值可获取 SwiftUI 在当前上下文中用于前景元素（例如文本、符号和形状）的样式。使用 [foregroundStyle(_:)](../View/foregroundStyle.zh-Hans.md) 修饰符可为给定视图及其子视图设置新的前景样式。

有关如何使用形状样式的信息，请参阅 [ShapeStyle](../ShapeStyle.zh-Hans.md)。

## 语义样式

- **background**：当前上下文中的背景样式。

- **selection**：一种用于根据平台常规颜色和行为以视觉方式指示选中状态的样式。

- **separator**：一种适用于前景分隔线或边框线的样式。

- **tint**：一种反映当前色调颜色的样式。

- **placeholder**：一种适用于占位符文本的样式。

- **link**：一种适用于链接的样式。

- **fill**：一种用于填充形状的叠加填充样式。

- **windowBackground**：一种适用于应与其包含窗口背景相匹配的元素的样式。


---
source: https://developer.apple.com/documentation/SwiftUI/ShapeStyle/foreground
crawled: 2025-12-03T06:25:17Z
---

# foreground

**Type Property**

The foreground style in the current context.

## Declaration

```swift
static var foreground: ForegroundStyle { get }
```

## Discussion

Access this value to get the style SwiftUI uses for foreground elements, like text, symbols, and shapes, in the current context. Use the [foregroundStyle(_:)](../View/foregroundStyle.zh-Hans.md) modifier to set a new foreground style for a given view and its child views.

For information about how to use shape styles, see [ShapeStyle](../ShapeStyle.zh-Hans.md).

## Semantic styles

- **background**: The background style in the current context.
- **selection**: A style used to visually indicate selection following platform conventional colors and behaviors.
- **separator**: A style appropriate for foreground separator or border lines.
- **tint**: A style that reflects the current tint color.
- **placeholder**: A style appropriate for placeholder text.
- **link**: A style appropriate for links.
- **fill**: An overlay fill style for filling shapes.
- **windowBackground**: A style appropriate for elements that should match the background of their containing window.

