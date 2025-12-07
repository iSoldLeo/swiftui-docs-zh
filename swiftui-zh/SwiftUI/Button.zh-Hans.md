--- 来源：https://developer.apple.com/documentation/SwiftUI/Button

抓取时间：2025-12-02T16:23:16Z

---

# 按钮

**Structure**

一个用于触发操作的控件。

## 声明

```swift
struct Button<Label> where Label : View
```

## 概述

创建按钮需要提供一个操作和一个标签。操作可以是方法或闭包属性，用于在用户点击或轻触按钮时执行特定操作。标签是一个视图，用于描述按钮的操作——例如，显示文本、图标或两者兼有。

按钮的标签可以是任何类型的视图，例如，纯文本标签可以使用 [Text](Text.zh-Hans.md) 视图：

```swift
Button(action: signIn) {
    Text("Sign In")
}
```

或者，带有标题和图标的按钮可以使用 [Label](Label.zh-Hans.md) 视图：

```swift
Button(action: signIn) {
    Label("Sign In", systemImage: "arrow.up")
}
```

对于这些常见情况，您还可以使用便捷初始化器，其第一个参数为标题字符串或 [LocalizedStringKey](LocalizedStringKey.zh-Hans.md)，第二个参数可选地为系统映像名称或 `ImageResource`，而不是使用尾随闭包：

```swift
Button("Sign In", systemImage: "arrow.up", action: signIn)
```

当同时提供标题和图标时，建议使用这些便捷初始化器或 [Label](Label.zh-Hans.md) 视图。这样，按钮可以动态调整其外观，以便在工具栏和菜单等容器中正确渲染其标题和图标。例如，在 iOS 系统中，按钮默认在工具栏中仅显示图标，但在菜单中则会同时显示标题和图标。这样定义标签也有助于提升辅助功能——例如，将 [labelStyle(_:)](View/labelStyle.zh-Hans.md) 修饰符与 [iconOnly](LabelStyle/iconOnly.zh-Hans.md) 样式结合使用，按钮将仅显示图标，但在 VoiceOver 等辅助功能模式下仍会使用标题来描述按钮：

```swift
Button("Sign In", systemImage: "arrow.up", action: signIn)
    .labelStyle(.iconOnly)
```

避免使用仅包含图像或纯视觉组件而没有辅助功能标签的标签。

用户激活按钮的方式因平台而异：

- 在 iOS 和 watchOS 系统中，用户轻点按钮。

- 在 macOS 系统中，用户点击按钮。

- 在 tvOS 系统中，用户在将焦点放在按钮上时，按下 Siri Remote 等外部遥控器上的“选择”按钮。

按钮的外观取决于多种因素，例如按钮的放置位置、是否为其分配角色以及其样式。

### 向容器添加按钮

对于任何用于触发操作的用户界面元素，都可以使用按钮。按钮会自动调整其视觉样式，以匹配不同容器和上下文中的预期样式。例如，要创建一个用户选择后触发操作的单元格（[List](List.zh-Hans.md)），请向列表内容添加一个按钮：

```swift
List {
    // Cells that show all the current folders.
    ForEach(folders) { folder in
        Text(folder.title)
    }

    // A cell that, when selected, adds a new folder.
    Button(action: addItem) {
        Label("Add Folder", systemImage: "folder.badge.plus")
    }
}
```

类似地，要创建一个触发操作的上下文菜单项，请向修饰符（[contextMenu(_:)](View/contextMenu.zh-Hans.md)）的内容闭包添加一个按钮：

```swift
.contextMenu {
    Button("Cut", action: cut)
    Button("Copy", action: copy)
    Button("Paste", action: paste)
}
```

这种模式也适用于 SwiftUI 中大多数其他具有可自定义交互式内容的容器视图，例如（[Form](Form.zh-Hans.md)）实例。

### 分配角色

您可以选择为按钮初始化一个 [ButtonRole](ButtonRole.zh-Hans.md) 角色，以描述按钮的用途。例如，您可以创建一个 [destructive](ButtonRole/destructive.zh-Hans.md) 按钮用于删除操作：

```swift
 Button("Delete", role: .destructive, action: delete)
```

系统会根据按钮的角色，在各种情况下为其设置合适的样式。例如，上下文菜单中的删除按钮会显示为红色前景色：

如果您没有为按钮指定角色，系统将应用相应的默认外观。

### 按钮样式

您可以使用标准按钮样式（例如 [bordered](PrimitiveButtonStyle/bordered.zh-Hans.md)）自定义按钮的外观，并使用 [buttonStyle(_:)](View/buttonStyle.zh-Hans.md) 修饰符应用该样式：

```swift
HStack {
    Button("Sign In", action: signIn)
    Button("Register", action: register)
}
.buttonStyle(.bordered)
```

如果您将样式应用于容器视图（如上例所示），则容器中的所有按钮都将使用该样式：

您还可以创建自定义样式。要添加具有标准交互行为的自定义外观，请创建符合 [ButtonStyle](ButtonStyle.zh-Hans.md) 协议的样式。要同时自定义外观和交互行为，请创建符合 [PrimitiveButtonStyle](PrimitiveButtonStyle.zh-Hans.md) 协议的样式。自定义样式还可以读取按钮的角色并使用它来调整按钮的外观。

## 创建按钮

- **init(action:label:)**：创建一个显示自定义标签的按钮。

- **init(_:action:)**：创建一个按钮，其标签由本地化字符串键生成。

- **init(_:image:action:)**：创建一个按钮，其标签由本地化字符串键和图像资源生成。

- **init(_:systemImage:action:)**：创建一个按钮，其标签由本地化字符串键和系统图像名称生成。

## 创建具有角色的按钮

- **init(role:action:label:)**：创建一个具有指定角色的按钮，该按钮显示自定义标签。

- **init(_:role:action:)**：创建一个具有指定角色的按钮，其标签由本地化字符串键生成。

- **init(_:image:role:action:)**：创建一个具有指定角色的按钮，其标签由本地化字符串键和图像资源生成。

- **init(_:systemImage:role:action:)**：创建一个具有指定角色的按钮，该按钮的标签由本地化字符串键和系统图像生成。

## 根据配置创建按钮

- **init(_:)**：根据具有自定义外观和自定义交互行为的样式配置创建按钮。

## 创建用于执行应用意图的按钮

- **init(_:intent:)**：创建一个执行 `AppIntent` 操作的按钮，该按钮的标签由本地化字符串键生成。

- **init(intent:label:)**：创建一个执行 `AppIntent` 操作的按钮。

- **init(_:role:intent:)**：创建一个具有指定角色的按钮，该按钮执行 `AppIntent` 操作，该按钮的标签由字符串生成。

- **init(role:intent:label:)**：创建一个具有指定角色的按钮，该按钮执行 `AppIntent` 操作。

- **init(_:image:role:intent:)**：创建一个具有指定角色的按钮，该按钮的标签由字符串和图像资源生成。

- **init(_:systemImage:role:intent:)**：创建一个具有指定角色的按钮，该按钮的标签由字符串和系统图像生成。

## 初始化器

- **init(role:action:)**：创建一个显示默认标签的按钮。

## 创建按钮

- **buttonStyle(_:)**：将此视图中按钮的样式设置为具有自定义外观和标准交互行为的按钮样式。

- **buttonBorderShape(_:)**：设置此视图中按钮的边框形状。

- **buttonRepeatBehavior(_:)**：设置此视图中的按钮在长时间交互后是否应重复触发其操作。

- **buttonRepeatBehavior**：设置与此关联环境中的按钮在长时间交互后是否应重复触发其操作。

- **ButtonBorderShape**：用于绘制按钮边框的形状。

- **ButtonRole**：描述按钮用途的值。

- **ButtonRepeatBehavior**：控制按钮操作重复性的选项。

- **ButtonSizing**：`Button` 和其他类似按钮的控件的大小调整行为。

## 符合

- 视图


---
source: https://developer.apple.com/documentation/SwiftUI/Button
crawled: 2025-12-02T16:23:16Z
---

# Button

**Structure**

A control that initiates an action.

## Declaration

```swift
struct Button<Label> where Label : View
```

## Overview

You create a button by providing an action and a label. The action is either a method or closure property that does something when a user clicks or taps the button. The label is a view that describes the button’s action — for example, by showing text, an icon, or both.

The label of a button can be any kind of view, such as a [Text](Text.zh-Hans.md) view for text-only labels:

```swift
Button(action: signIn) {
    Text("Sign In")
}
```

Or a [Label](Label.zh-Hans.md) view, for buttons with both a title and an icon:

```swift
Button(action: signIn) {
    Label("Sign In", systemImage: "arrow.up")
}
```

For those common cases, you can also use the convenience initializers that take a title string or [LocalizedStringKey](LocalizedStringKey.zh-Hans.md) as their first parameter, and optionally a system image name or `ImageResource` as their second parameter, instead of a trailing closure:

```swift
Button("Sign In", systemImage: "arrow.up", action: signIn)
```

Prefer to use these convenience initializers, or a [Label](Label.zh-Hans.md) view, when providing both a title and an icon. This allows the button to dynamically adapt its appearance to render its title and icon correctly in containers such as toolbars and menus. For example, on iOS, buttons only display their icons by default when placed in toolbars, but show both a leading title and trailing icon in menus. Defining labels this way also helps with accessibility — for example, applying the [labelStyle(_:)](View/labelStyle.zh-Hans.md) modifier with an [iconOnly](LabelStyle/iconOnly.zh-Hans.md) style to the button will cause it to only visually display its icon, but still use its title to describe the button in accessibility modes like VoiceOver:

```swift
Button("Sign In", systemImage: "arrow.up", action: signIn)
    .labelStyle(.iconOnly)
```

Avoid labels that only use images or exclusively visual components without an accessibility label.

How the user activates the button varies by platform:

- In iOS and watchOS, the user taps the button.
- In macOS, the user clicks the button.
- In tvOS, the user presses “select” on an external remote, like the Siri Remote, while focusing on the button.

The appearance of the button depends on factors like where you place it, whether you assign it a role, and how you style it.

### Adding buttons to containers

Use buttons for any user interface element that initiates an action. Buttons automatically adapt their visual style to match the expected style within these different containers and contexts. For example, to create a [List](List.zh-Hans.md) cell that initiates an action when selected by the user, add a button to the list’s content:

```swift
List {
    // Cells that show all the current folders.
    ForEach(folders) { folder in
        Text(folder.title)
    }

    // A cell that, when selected, adds a new folder.
    Button(action: addItem) {
        Label("Add Folder", systemImage: "folder.badge.plus")
    }
}
```



Similarly, to create a context menu item that initiates an action, add a button to the [contextMenu(_:)](View/contextMenu.zh-Hans.md) modifier’s content closure:

```swift
.contextMenu {
    Button("Cut", action: cut)
    Button("Copy", action: copy)
    Button("Paste", action: paste)
}
```



This pattern extends to most other container views in SwiftUI that have customizable, interactive content, like [Form](Form.zh-Hans.md) instances.

### Assigning a role

You can optionally initialize a button with a [ButtonRole](ButtonRole.zh-Hans.md) that characterizes the button’s purpose. For example, you can create a [destructive](ButtonRole/destructive.zh-Hans.md) button for a deletion action:

```swift
 Button("Delete", role: .destructive, action: delete)
```

The system uses the button’s role to style the button appropriately in every context. For example, a destructive button in a contextual menu appears with a red foreground color:



If you don’t specify a role for a button, the system applies an appropriate default appearance.

### Styling buttons

You can customize a button’s appearance using one of the standard button styles, like [bordered](PrimitiveButtonStyle/bordered.zh-Hans.md), and apply the style with the [buttonStyle(_:)](View/buttonStyle.zh-Hans.md) modifier:

```swift
HStack {
    Button("Sign In", action: signIn)
    Button("Register", action: register)
}
.buttonStyle(.bordered)
```

If you apply the style to a container view, as in the example above, all the buttons in the container use the style:



You can also create custom styles. To add a custom appearance with standard interaction behavior, create a style that conforms to the [ButtonStyle](ButtonStyle.zh-Hans.md) protocol. To customize both appearance and interaction behavior, create a style that conforms to the [PrimitiveButtonStyle](PrimitiveButtonStyle.zh-Hans.md) protocol. Custom styles can also read the button’s role and use it to adjust the button’s appearance.

## Creating a button

- **init(action:label:)**: Creates a button that displays a custom label.
- **init(_:action:)**: Creates a button that generates its label from a localized string key.
- **init(_:image:action:)**: Creates a button that generates its label from a localized string key and image resource.
- **init(_:systemImage:action:)**: Creates a button that generates its label from a localized string key and system image name.

## Creating a button with a role

- **init(role:action:label:)**: Creates a button with a specified role that displays a custom label.
- **init(_:role:action:)**: Creates a button with a specified role that generates its label from a localized string key.
- **init(_:image:role:action:)**: Creates a button with a specified role that generates its label from a localized string key and an image resource.
- **init(_:systemImage:role:action:)**: Creates a button with a specified role that generates its label from a localized string key and a system image.

## Creating a button from a configuration

- **init(_:)**: Creates a button based on a configuration for a style with a custom appearance and custom interaction behavior.

## Creating a button to perform an App Intent

- **init(_:intent:)**: Creates a button that performs an `AppIntent` and generates its label from a localized string key.
- **init(intent:label:)**: Creates a button that performs an `AppIntent`.
- **init(_:role:intent:)**: Creates a button with a specified role that performs an `AppIntent` and generates its label from a string.
- **init(role:intent:label:)**: Creates a button with a specified role that performs an `AppIntent`.
- **init(_:image:role:intent:)**: Creates a button with a specified role that generates its label from a string and an image resource.
- **init(_:systemImage:role:intent:)**: Creates a button with a specified role that generates its label from a string and a system image.

## Initializers

- **init(role:action:)**: Creates a button that displays a default label.

## Creating buttons

- **buttonStyle(_:)**: Sets the style for buttons within this view to a button style with a custom appearance and standard interaction behavior.
- **buttonBorderShape(_:)**: Sets the border shape for buttons in this view.
- **buttonRepeatBehavior(_:)**: Sets whether buttons in this view should repeatedly trigger their actions on prolonged interactions.
- **buttonRepeatBehavior**: Whether buttons with this associated environment should repeatedly trigger their actions on prolonged interactions.
- **ButtonBorderShape**: A shape used to draw a button’s border.
- **ButtonRole**: A value that describes the purpose of a button.
- **ButtonRepeatBehavior**: The options for controlling the repeatability of button actions.
- **ButtonSizing**: The sizing behavior of `Button`s and other button-like controls.

## Conforms To

- View

