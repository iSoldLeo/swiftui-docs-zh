--- 来源：https://developer.apple.com/documentation/swiftui/menubutton

抓取时间：2025-12-03T06:23:58Z

---

# 菜单按钮

**Structure**

按下此按钮将显示一个包含选项列表的菜单。

## 声明

```swift
struct MenuButton<Label, Content> where Label : View, Content : View
```

## 创建菜单按钮

- **init(_:content:)**：创建具有指定本地化标题和内容的菜单按钮。

- **init(label:content:)**：创建具有指定标签和内容的菜单按钮。

## 设置菜单按钮样式

- **menuButtonStyle(_:)**：设置此视图中菜单按钮的样式。

- **MenuButtonStyle**：菜单按钮外观和交互的自定义规范。

## 已弃用类型

- **PullDownButton**

- **ContextMenu**：用于存放上下文菜单中菜单项的视图容器。

## 符合以下类型：

- View


---
source: https://developer.apple.com/documentation/swiftui/menubutton
crawled: 2025-12-03T06:23:58Z
---

# MenuButton

**Structure**

A button that displays a menu containing a list of choices when pressed.

## Declaration

```swift
struct MenuButton<Label, Content> where Label : View, Content : View
```

## Creating a menu button

- **init(_:content:)**: Creates a menu button with the specified localized title and content.
- **init(label:content:)**: Creates a menu button with the specified label and content.

## Styling a menu button

- **menuButtonStyle(_:)**: Sets the style for menu buttons within this view.
- **MenuButtonStyle**: A custom specification for the appearance and interaction of a menu button.

## Deprecated types

- **PullDownButton**
- **ContextMenu**: A container for views that you present as menu items in a context menu.

## Conforms To

- View

