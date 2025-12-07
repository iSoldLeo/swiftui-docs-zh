--- 来源：https://developer.apple.com/documentation/SwiftUI/PrimitiveButtonStyleConfiguration
抓取时间：2025-12-02T17:33:03Z

---

# PrimitiveButtonStyleConfiguration

**Structure**

按钮的属性。

## 声明

```swift
struct PrimitiveButtonStyleConfiguration
```

## 配置按钮的标签

- **label**：描述调用按钮操作效果的视图。

- **PrimitiveButtonStyleConfiguration.Label**：按钮的无字标签。

## 启动按钮的操作

- **trigger()**：执行按钮的操作。

## 定义按钮用途

- **role**：一个可选的语义角色，用于描述按钮的用途。

## 设置按钮样式

- **buttonStyle(_:)**：将此视图中按钮的样式设置为具有自定义外观和标准交互行为的按钮样式。

- **ButtonStyle**：一种类型，它将标准交互行为和自定义外观应用于视图层次结构中的所有按钮。

- **ButtonStyleConfiguration**：按钮的属性。

- **PrimitiveButtonStyle**：一种类型，它将自定义交互行为和自定义外观应用于视图层次结构中的所有按钮。

- **signInWithAppleButtonStyle(_:)**：设置用于显示控件的样式（参见 `SignInWithAppleButton.Style`）。


---
source: https://developer.apple.com/documentation/SwiftUI/PrimitiveButtonStyleConfiguration
crawled: 2025-12-02T17:33:03Z
---

# PrimitiveButtonStyleConfiguration

**Structure**

The properties of a button.

## Declaration

```swift
struct PrimitiveButtonStyleConfiguration
```

## Configuring a button’s label

- **label**: A view that describes the effect of calling the button’s action.
- **PrimitiveButtonStyleConfiguration.Label**: A type-erased label of a button.

## Initiating a button’s action

- **trigger()**: Performs the button’s action.

## Defining the button’s purpose

- **role**: An optional semantic role describing the button’s purpose.

## Styling buttons

- **buttonStyle(_:)**: Sets the style for buttons within this view to a button style with a custom appearance and standard interaction behavior.
- **ButtonStyle**: A type that applies standard interaction behavior and a custom appearance to all buttons within a view hierarchy.
- **ButtonStyleConfiguration**: The properties of a button.
- **PrimitiveButtonStyle**: A type that applies custom interaction behavior and a custom appearance to all buttons within a view hierarchy.
- **signInWithAppleButtonStyle(_:)**: Sets the style used for displaying the control (see `SignInWithAppleButton.Style`).

