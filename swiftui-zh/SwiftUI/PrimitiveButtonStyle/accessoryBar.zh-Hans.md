---
来源： https://developer.apple.com/documentation/SwiftUI/PrimitiveButtonStyle/accessoryBar
抓取时间： 2025-12-02T21:50:19Z
---

# 配件栏

**类型属性**

一种按钮样式，通常用于附件工具栏（有时称为 "范围栏"），用于缩小搜索或其他操作焦点的按钮。

### 声明

```swift
@MainActor @preconcurrency static var accessoryBar: AccessoryBarButtonStyle { get }
```

## 讨论

这是用 `ToolbarItemPlacement.init(id:_)` 创建的附件工具栏中视图和可搜索作用域的默认按钮样式。

该样式也会影响`Toggle`、`Picker`和`Menu`的按钮样式。

```swift
HStack(alignment: .firstTextBaseline) {
    Button("Button") {}

    Toggle("Toggle", isOn: $isToggleOn)
        .toggleStyle(.button)

    Picker("Picker", selection: $selection) {
        Text("Option 1").tag(0)
        Text("Option 2").tag(1)
    }

    Picker("Inline Picker", selection: $selection) {
        Text("Option 1").tag(0)
        Text("Option 2").tag(1)
    }
    .pickerStyle(.inline)

    Menu("Menu") {
        Button("Item") {}
    }
}
.buttonStyle(.accessoryBar)
```

## 获取内置按钮样式

- **automatic**：基于按钮上下文的默认按钮样式。
- **accessoryBarAction**：用于附件工具栏中额外操作的按钮样式。
- **bordered**：根据按钮上下文应用标准边框样式的按钮样式。
- **borderedProminent**：根据按钮上下文应用标准边框突出样式的按钮样式。
- **borderless**：不应用边框的按钮样式。
- **card**：不填充内容的按钮样式，当按钮有焦点时会应用液态玻璃效果。
- **glass**：根据按钮上下文应用 Liquid Glass 效果的按钮样式。
- **glassProminent**：一种按钮样式，可根据按钮的上下文应用突出的 Liquid Glass 效果。
- **glass(_:)**：根据按钮上下文应用可配置 Liquid Glass 效果的按钮样式。
- **link**：用于模拟链接的按钮样式。
- **plain**：一种按钮样式，在空闲时不会样式化或装饰其内容，但可以应用视觉效果来指示按钮的按下、聚焦或启用状态。


---
source: https://developer.apple.com/documentation/SwiftUI/PrimitiveButtonStyle/accessoryBar
crawled: 2025-12-02T21:50:19Z
---

# accessoryBar

**Type Property**

A button style that is typically used in the context of an accessory toolbar (sometimes refererred to as a “scope bar”), for buttons that narrow the focus of a search or other operation.

## Declaration

```swift
@MainActor @preconcurrency static var accessoryBar: AccessoryBarButtonStyle { get }
```

## Discussion

This is the default button style for views in accessory toolbars, created with `ToolbarItemPlacement.init(id:_)`, and for searchable scopes.

This style will also affect button style `Toggle`s, as well as button style `Picker`s and `Menu`s.

```swift
HStack(alignment: .firstTextBaseline) {
    Button("Button") {}

    Toggle("Toggle", isOn: $isToggleOn)
        .toggleStyle(.button)

    Picker("Picker", selection: $selection) {
        Text("Option 1").tag(0)
        Text("Option 2").tag(1)
    }

    Picker("Inline Picker", selection: $selection) {
        Text("Option 1").tag(0)
        Text("Option 2").tag(1)
    }
    .pickerStyle(.inline)

    Menu("Menu") {
        Button("Item") {}
    }
}
.buttonStyle(.accessoryBar)
```

## Getting built-in button styles

- **automatic**: The default button style, based on the button’s context.
- **accessoryBarAction**: A button style that you use for extra actions in an accessory toolbar.
- **bordered**: A button style that applies the standard border style based on the button’s context.
- **borderedProminent**: A button style that applies the standard bordered prominent style based on the button’s context.
- **borderless**: A button style that doesn’t apply a border.
- **card**: A button style that doesn’t pad the content, and applies a Liquid Glass effect when the button has focus.
- **glass**: A button style that applies a Liquid Glass effect based on the button’s context.
- **glassProminent**: A button style that applies a prominent Liquid Glass effect based on the button’s context.
- **glass(_:)**: A button style that applies a configurable Liquid Glass effect based on the button’s context.
- **link**: A button style for buttons that emulate links.
- **plain**: A button style that doesn’t style or decorate its content while idle, but may apply a visual effect to indicate the pressed, focused, or enabled state of the button.

