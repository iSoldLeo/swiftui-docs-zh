--- 来源：https://developer.apple.com/documentation/SwiftUI/View/buttonStyle(_:)

抓取时间：2025-12-02T17:33:01Z

---

# buttonStyle(_:)

**实例方法**

将此视图中按钮的样式设置为具有自定义外观和标准交互行为的按钮样式。

## 声明

```swift
nonisolated func buttonStyle<S>(_ style: S) -> some View where S : ButtonStyle

```

## 说明

使用此修饰符可为视图中的所有按钮实例设置特定样式：

```swift
HStack {
    Button("Sign In", action: signIn)
    Button("Register", action: register)
}
.buttonStyle(.bordered)
```

您还可以使用此修饰符为通过组合获得按钮样式的控件设置样式，例如以下示例中的 [Menu](../Menu.zh-Hans.md) 和 [Toggle](../Toggle.zh-Hans.md) 视图：

```swift
VStack {
    Menu("Terms and Conditions") {
        Button("Open in Preview", action: openInPreview)
        Button("Save as PDF", action: saveAsPDF)
    }
    Toggle("Remember Password", isOn: $isToggleOn)
    Toggle("Flag", isOn: $flagged)
    Button("Sign In", action: signIn)
}
.menuStyle(.button)
.toggleStyle(.button)
.buttonStyle(.bordered)
```

[menuStyle(_:)](menuStyle.zh-Hans.md) 修饰符使“条款和条件”菜单呈现为按钮。类似地，[toggleStyle(_:)](toggleStyle.zh-Hans.md) 修饰符使两个切换按钮呈现为按钮。然后，按钮样式修饰符不仅使显式的“登录”按钮 [Button](../Button.zh-Hans.md) 呈现为带边框的按钮样式，而且使具有按钮样式的菜单和切换按钮也呈现为带边框的按钮样式。

## 创建按钮

- **Button**：用于启动操作的控件。

- **buttonBorderShape(_:)**：设置此视图中按钮的边框形状。

- **buttonRepeatBehavior(_:)**：设置此视图中的按钮在长时间交互后是否应重复触发其操作。

- **buttonRepeatBehavior**：设置与此关联环境中的按钮在长时间交互后是否应重复触发其操作。

- **ButtonBorderShape**：用于绘制按钮边框的形状。

- **ButtonRole**：描述按钮用途的值。

- **ButtonRepeatBehavior**：用于控制按钮操作重复性的选项。

- **ButtonSizing**：`Button` 和其他类似按钮的控件的缩放行为。


---
source: https://developer.apple.com/documentation/SwiftUI/View/buttonStyle(_:)
crawled: 2025-12-02T17:33:01Z
---

# buttonStyle(_:)

**Instance Method**

Sets the style for buttons within this view to a button style with a custom appearance and standard interaction behavior.

## Declaration

```swift
nonisolated func buttonStyle<S>(_ style: S) -> some View where S : ButtonStyle

```

## Discussion

Use this modifier to set a specific style for all button instances within a view:

```swift
HStack {
    Button("Sign In", action: signIn)
    Button("Register", action: register)
}
.buttonStyle(.bordered)
```

You can also use this modifier to set the style for controls that acquire a button style through composition, like the [Menu](../Menu.zh-Hans.md) and [Toggle](../Toggle.zh-Hans.md) views in the following example:

```swift
VStack {
    Menu("Terms and Conditions") {
        Button("Open in Preview", action: openInPreview)
        Button("Save as PDF", action: saveAsPDF)
    }
    Toggle("Remember Password", isOn: $isToggleOn)
    Toggle("Flag", isOn: $flagged)
    Button("Sign In", action: signIn)
}
.menuStyle(.button)
.toggleStyle(.button)
.buttonStyle(.bordered)
```

The [menuStyle(_:)](menuStyle.zh-Hans.md) modifier causes the Terms and Conditions menu to render as a button. Similarly, the [toggleStyle(_:)](toggleStyle.zh-Hans.md) modifier causes the two toggles to render as buttons. The button style modifier then causes not only the explicit Sign In [Button](../Button.zh-Hans.md), but also the menu and toggles with button styling, to render with the bordered button style.

## Creating buttons

- **Button**: A control that initiates an action.
- **buttonBorderShape(_:)**: Sets the border shape for buttons in this view.
- **buttonRepeatBehavior(_:)**: Sets whether buttons in this view should repeatedly trigger their actions on prolonged interactions.
- **buttonRepeatBehavior**: Whether buttons with this associated environment should repeatedly trigger their actions on prolonged interactions.
- **ButtonBorderShape**: A shape used to draw a button’s border.
- **ButtonRole**: A value that describes the purpose of a button.
- **ButtonRepeatBehavior**: The options for controlling the repeatability of button actions.
- **ButtonSizing**: The sizing behavior of `Button`s and other button-like controls.

