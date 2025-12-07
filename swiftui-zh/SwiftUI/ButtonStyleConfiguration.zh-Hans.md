---
来源： https://developer.apple.com/documentation/SwiftUI/ButtonStyleConfiguration
抓取时间： 2025-12-02T17:33:02Z
---

# ButtonStyleConfiguration

**Structure**

按钮的属性。

## 声明

```swift
struct ButtonStyleConfiguration
```

## 配置按钮标签

- **label**：描述按下按钮后效果的视图。
- **ButtonStyleConfiguration.Label**：按钮的分型标签。

## 配置按钮的交互状态

- **isPressed**：布尔值，表示用户当前是否正在按下按钮。

## 定义按钮的用途

- **role**：描述按钮用途的可选语义角色。

## 设计按钮样式

- **buttonStyle(_:)**：将此视图中按钮的样式设置为具有自定义外观和标准交互行为的按钮样式。
- **ButtonStyle**：将标准交互行为和自定义外观应用于视图层次结构中所有按钮的类型。
- **PrimitiveButtonStyle**：对视图层次结构中的所有按钮应用自定义交互行为和自定义外观的类型。
- **PrimitiveButtonStyleConfiguration**：按钮的属性。
- **signInWithAppleButtonStyle(_:)**：按钮的属性：设置用于显示控件的样式（参见 `SignInWithAppleButton.Style`）。


---
source: https://developer.apple.com/documentation/SwiftUI/ButtonStyleConfiguration
crawled: 2025-12-02T17:33:02Z
---

# ButtonStyleConfiguration

**Structure**

The properties of a button.

## Declaration

```swift
struct ButtonStyleConfiguration
```

## Configuring a button’s label

- **label**: A view that describes the effect of pressing the button.
- **ButtonStyleConfiguration.Label**: A type-erased label of a button.

## Configuring a button’s interaction state

- **isPressed**: A Boolean that indicates whether the user is currently pressing the button.

## Defining the button’s purpose

- **role**: An optional semantic role that describes the button’s purpose.

## Styling buttons

- **buttonStyle(_:)**: Sets the style for buttons within this view to a button style with a custom appearance and standard interaction behavior.
- **ButtonStyle**: A type that applies standard interaction behavior and a custom appearance to all buttons within a view hierarchy.
- **PrimitiveButtonStyle**: A type that applies custom interaction behavior and a custom appearance to all buttons within a view hierarchy.
- **PrimitiveButtonStyleConfiguration**: The properties of a button.
- **signInWithAppleButtonStyle(_:)**: Sets the style used for displaying the control (see `SignInWithAppleButton.Style`).

