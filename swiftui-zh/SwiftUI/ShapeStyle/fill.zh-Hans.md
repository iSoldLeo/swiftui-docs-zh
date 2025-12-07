--- 来源：https://developer.apple.com/documentation/SwiftUI/ShapeStyle/fill
抓取时间：2025-12-03T06:25:22Z

---

# fill

**类型属性**

用于填充形状的覆盖填充样式。

## 声明

```swift
static var fill: FillShapeStyle { get }
```

## 讨论

此形状样式适用于位于现有背景色之上的元素。它包含透明度，允许背景色透过填充显示出来。

使用此样式的主要版本填充细长或小型形状，例如 iOS 上的滑块轨道。使用此样式的次要版本填充中等大小的形状，例如 iOS 上的开关背景。使用此样式的第三版本填充大型形状，例如 iOS 上的输入框、搜索栏或按钮。使用此样式的第四版本填充包含复杂内容的大型区域，例如 iOS 上的展开表格单元格。

## 语义样式

- **foreground**：当前上下文中的前景色样式。

- **background**：当前上下文中的背景色样式。

- **selection**：用于根据平台约定的颜色和行为，以视觉方式指示选中状态的样式。

- **separator**：适用于前景色分隔符或边框线的样式。

- **tint**：反映当前色调颜色的样式。

- **placeholder**：适用于占位符文本的样式。

- **link**：适用于链接的样式。

- **windowBackground**：适用于应与其包含窗口背景相匹配的元素的样式。


---
source: https://developer.apple.com/documentation/SwiftUI/ShapeStyle/fill
crawled: 2025-12-03T06:25:22Z
---

# fill

**Type Property**

An overlay fill style for filling shapes.

## Declaration

```swift
static var fill: FillShapeStyle { get }
```

## Discussion

This shape style is appropriate for items situated on top of an existing background color. It incorporates transparency to allow the background color to show through.

Use the primary version of this style to fill thin or small shapes, such as the track of a slider on iOS. Use the secondary version of this style to fill medium-size shapes, such as the background of a switch on iOS. Use the tertiary version of this style to fill large shapes, such as input fields, search bars, or buttons on iOS. Use the quaternary version of this style to fill large areas that contain complex content, such as an expanded table cell on iOS.

## Semantic styles

- **foreground**: The foreground style in the current context.
- **background**: The background style in the current context.
- **selection**: A style used to visually indicate selection following platform conventional colors and behaviors.
- **separator**: A style appropriate for foreground separator or border lines.
- **tint**: A style that reflects the current tint color.
- **placeholder**: A style appropriate for placeholder text.
- **link**: A style appropriate for links.
- **windowBackground**: A style appropriate for elements that should match the background of their containing window.

