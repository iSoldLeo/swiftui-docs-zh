--- 来源：https://developer.apple.com/documentation/SwiftUI/ShapeStyle/background

抓取时间：2025-12-03T06:25:17Z

---

# background

**类型属性**

当前上下文中的背景样式。

## 声明

```swift
static var background: BackgroundStyle { get }
```

## 讨论

访问此值可获取 SwiftUI 在当前上下文中使用的背景样式。SwiftUI 渲染的具体颜色取决于平台以及用户是否启用了深色模式等因素。

有关如何使用形状样式的信息，请参阅 [ShapeStyle](../ShapeStyle.zh-Hans.md)。

## 语义样式

- **foreground**：当前上下文中的前景样式。

- **selection**：用于根据平台约定的颜色和行为以视觉方式指示选中状态的样式。

- **separator**：适用于前景分隔线或边框线的样式。

- **tint**：反映当前色调颜色的样式。

- **placeholder**：适用于占位符文本的样式。

- **link**：适用于链接的样式。

- **fill**：用于填充形状的叠加填充样式。

- **windowBackground**：适用于应与其包含窗口背景相匹配的元素的样式。


---
source: https://developer.apple.com/documentation/SwiftUI/ShapeStyle/background
crawled: 2025-12-03T06:25:17Z
---

# background

**Type Property**

The background style in the current context.

## Declaration

```swift
static var background: BackgroundStyle { get }
```

## Discussion

Access this value to get the style SwiftUI uses for the background in the current context. The specific color that SwiftUI renders depends on factors like the platform and whether the user has turned on Dark Mode.

For information about how to use shape styles, see [ShapeStyle](../ShapeStyle.zh-Hans.md).

## Semantic styles

- **foreground**: The foreground style in the current context.
- **selection**: A style used to visually indicate selection following platform conventional colors and behaviors.
- **separator**: A style appropriate for foreground separator or border lines.
- **tint**: A style that reflects the current tint color.
- **placeholder**: A style appropriate for placeholder text.
- **link**: A style appropriate for links.
- **fill**: An overlay fill style for filling shapes.
- **windowBackground**: A style appropriate for elements that should match the background of their containing window.

