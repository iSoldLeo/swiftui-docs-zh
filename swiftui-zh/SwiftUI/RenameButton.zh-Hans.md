---

来源：https://developer.apple.com/documentation/SwiftUI/RenameButton
抓取时间：2025-12-02T17:27:43Z

---

# 重命名按钮

**Structure**

一个触发标准重命名操作的按钮。

## 声明

```swift
struct RenameButton<Label> where Label : View
```

## 概述

重命名按钮的操作由上下文决定。使用 [renameAction(_:)](View/renameAction.zh-Hans.md) 修饰符来设置操作。如果未定义操作，系统将禁用该按钮。

```swift
struct RowView: View {
    @State private var text = ""
    @FocusState private var isFocused: Bool

    var body: some View {
        TextField(text: $item.name) {
            Text("Prompt")
        }
        .focused($isFocused)
        .contextMenu {
            RenameButton()
            // ... your own custom actions
        }
        .renameAction { $isFocused = true }
}
```

当用户点击上下文菜单中的重命名按钮时，重命名操作会将 `isFocused` 属性设置为 true，从而使文本字段获得焦点。

您可以将此按钮置于导航标题菜单中，导航标题修饰符会自动配置环境，并执行相应的重命名操作。

```swift
ContentView()
    .navigationTitle($contentTitle) {
        // ... your own custom actions
        RenameButton()
    }
```

## 创建重命名按钮

- **init()**：创建一个重命名按钮。

## 创建特殊用途按钮

- **EditButton**：一个用于切换编辑模式环境值的按钮。

- **PasteButton**：一个系统按钮，用于从剪贴板读取项目并将其传递给闭包。

## 符合以下规范

- View


---
source: https://developer.apple.com/documentation/SwiftUI/RenameButton
crawled: 2025-12-02T17:27:43Z
---

# RenameButton

**Structure**

A button that triggers a standard rename action.

## Declaration

```swift
struct RenameButton<Label> where Label : View
```

## Overview

A rename button receives its action from the environment. Use the [renameAction(_:)](View/renameAction.zh-Hans.md) modifier to set the action. The system disables the button if you don’t define an action.

```swift
struct RowView: View {
    @State private var text = ""
    @FocusState private var isFocused: Bool

    var body: some View {
        TextField(text: $item.name) {
            Text("Prompt")
        }
        .focused($isFocused)
        .contextMenu {
            RenameButton()
            // ... your own custom actions
        }
        .renameAction { $isFocused = true }
}
```

When someone taps the rename button in the context menu, the rename action focuses the text field by setting the `isFocused` property to true.

You can use this button inside of a navigation title menu and the navigation title modifier automatically configures the environment with the appropriate rename action.

```swift
ContentView()
    .navigationTitle($contentTitle) {
        // ... your own custom actions
        RenameButton()
    }
```

## Creating an rename button

- **init()**: Creates a rename button.

## Creating special-purpose buttons

- **EditButton**: A button that toggles the edit mode environment value.
- **PasteButton**: A system button that reads items from the pasteboard and delivers it to a closure.

## Conforms To

- View

