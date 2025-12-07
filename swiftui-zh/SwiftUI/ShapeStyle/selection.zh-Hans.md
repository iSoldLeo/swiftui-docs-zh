---

来源：https://developer.apple.com/documentation/SwiftUI/ShapeStyle/selection
抓取时间：2025-12-03T06:25:18Z

---

# 选择

**类型属性**

一种用于根据平台约定的颜色和行为，以视觉方式指示选中状态的样式。

## 声明

```swift
static var selection: SelectionShapeStyle { get }
```

## 讨论

例如：

```swift
ForEach(items) {
   ItemView(value: item, isSelected: item.id == selectedID)
}

struct ItemView {
    var value: item
    var isSelected: Bool

    var body: some View {
        // construct the actual cell content
            .background(isSelected
                ? AnyShapeStyle(.selection)
                    : AnyShapeStyle(.fill.quaternary),
                in: .rect(cornerRadius: 6))
    }
}
```

在 macOS 和 iPadOS 上，此样式会自动反映窗口的按键状态和焦点状态。只有当窗口处于按键状态且最近的可聚焦元素处于焦点状态时，才会使用高亮显示。在 iPhone 上，此样式始终会填充环境的强调色。

当将其作为其他视图的背景时，它会自动将该视图环境的 `EnvironmentValues.backgroundProminence` 设置为与当前选中状态相匹配。

有关如何使用形状样式的信息，请参阅 [ShapeStyle](../ShapeStyle.zh-Hans.md)。

## 语义样式

- **foreground**：当前上下文中的前景色样式。

- **background**：当前上下文中的背景色样式。

- **separator**：适用于前景色分隔线或边框线的样式。

- **tint**：反映当前色调颜色的样式。

- **placeholder**：适用于占位符文本的样式。

- **link**：适用于链接的样式。

- **fill**：用于填充形状的叠加填充样式。

- **windowBackground**：适用于需要与所在窗口背景颜色相匹配的元素的样式。


---
source: https://developer.apple.com/documentation/SwiftUI/ShapeStyle/selection
crawled: 2025-12-03T06:25:18Z
---

# selection

**Type Property**

A style used to visually indicate selection following platform conventional colors and behaviors.

## Declaration

```swift
static var selection: SelectionShapeStyle { get }
```

## Discussion

For example:

```swift
ForEach(items) {
   ItemView(value: item, isSelected: item.id == selectedID)
}

struct ItemView {
    var value: item
    var isSelected: Bool

    var body: some View {
        // construct the actual cell content
            .background(isSelected
                ? AnyShapeStyle(.selection)
                    : AnyShapeStyle(.fill.quaternary),
                in: .rect(cornerRadius: 6))
    }
}
```

On macOS and iPadOS this automatically reflects window key state and focus state, where the emphasized appearance will be used only when the window is key and the nearest focusable element is actually focused. On iPhone, this will always fill with the environment’s accent color.

When applied as a background of another view, it will automatically set the `EnvironmentValues.backgroundProminence` for the environment of that view to match the current prominence of the selection.

For information about how to use shape styles, see [ShapeStyle](../ShapeStyle.zh-Hans.md).

## Semantic styles

- **foreground**: The foreground style in the current context.
- **background**: The background style in the current context.
- **separator**: A style appropriate for foreground separator or border lines.
- **tint**: A style that reflects the current tint color.
- **placeholder**: A style appropriate for placeholder text.
- **link**: A style appropriate for links.
- **fill**: An overlay fill style for filling shapes.
- **windowBackground**: A style appropriate for elements that should match the background of their containing window.

