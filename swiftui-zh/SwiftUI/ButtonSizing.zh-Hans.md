--- 来源：https://developer.apple.com/documentation/SwiftUI/ButtonSizing

抓取时间：2025-12-02T17:36:02Z

---

# ButtonSizing

**Structure**

按钮和其他类似按钮的控件的缩放行为。

## 声明

```swift
struct ButtonSizing
```

## 类型属性

- **automatic**：根据按钮的上下文位置和平台，设置默认的按钮缩放行为。

- **fitted**：沿按钮的主轴调整按钮大小，使其适应内部内容，必要时进行压缩。

- **flexible**：沿按钮的主轴灵活调整按钮大小，通过扩展或压缩超出其理想大小来填充可用空间。

## 创建按钮

- **Button**：用于启动操作的控件。

- **buttonStyle(_:)**：将此视图中按钮的样式设置为具有自定义外观和标准交互行为的按钮样式。

- **buttonBorderShape(_:)**：设置此视图中按钮的边框形状。

- **buttonRepeatBehavior(_:)**：设置此视图中的按钮在长时间交互后是否应重复触发其操作。

- **buttonRepeatBehavior**：设置具有此关联环境的按钮在长时间交互后是否应重复触发其操作。

- **ButtonBorderShape**：用于绘制按钮边框的形状。

- **ButtonRole**：描述按钮用途的值。

- **ButtonRepeatBehavior**：用于控制按钮操作重复性的选项。

## 符合以下标准

- Equatable

- Hashable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/ButtonSizing
crawled: 2025-12-02T17:36:02Z
---

# ButtonSizing

**Structure**

The sizing behavior of `Button`s and other button-like controls.

## Declaration

```swift
struct ButtonSizing
```

## Type Properties

- **automatic**: The default button sizing behavior appropriate for the button’s contextual placement and platform.
- **fitted**: Sizes a button along its primary axis to fit its inner content, compressing if necessary.
- **flexible**: Sizes a button flexibly along its primary axis, filling its available space by expanding or compressing beyond its ideal size.

## Creating buttons

- **Button**: A control that initiates an action.
- **buttonStyle(_:)**: Sets the style for buttons within this view to a button style with a custom appearance and standard interaction behavior.
- **buttonBorderShape(_:)**: Sets the border shape for buttons in this view.
- **buttonRepeatBehavior(_:)**: Sets whether buttons in this view should repeatedly trigger their actions on prolonged interactions.
- **buttonRepeatBehavior**: Whether buttons with this associated environment should repeatedly trigger their actions on prolonged interactions.
- **ButtonBorderShape**: A shape used to draw a button’s border.
- **ButtonRole**: A value that describes the purpose of a button.
- **ButtonRepeatBehavior**: The options for controlling the repeatability of button actions.

## Conforms To

- Equatable
- Hashable
- Sendable
- SendableMetatype

