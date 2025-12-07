--- 来源：https://developer.apple.com/documentation/SwiftUI/TextFieldLink

抓取时间：2025-12-02T17:27:58Z

---

# TextFieldLink

**Structure**

一个控件，按下后会请求用户输入文本。

## 声明

```swift
struct TextFieldLink<Label> where Label : View
```

## 概述

应该使用 `TextFieldLink` 通过按钮界面请求用户输入文本。

## 创建文本字段链接

- **init(_:prompt:onSubmit:)**：创建一个 TextFieldLink，按下后会请求用户输入文本。

- **init(prompt:label:onSubmit:)**：创建一个 TextFieldLink，按下后会请求用户输入文本。

## 链接到其他内容

- **Link**：用于导航到 URL 的控件。

- **ShareLink**：用于控制共享演示的视图。

- **SharePreview**：用于在共享预览中显示的类型表示。

- **HelpLink**：具有标准外观的按钮，用于打开特定于应用程序的帮助文档。

## 符合以下规范

- View


---
source: https://developer.apple.com/documentation/SwiftUI/TextFieldLink
crawled: 2025-12-02T17:27:58Z
---

# TextFieldLink

**Structure**

A control that requests text input from the user when pressed.

## Declaration

```swift
struct TextFieldLink<Label> where Label : View
```

## Overview

A `TextFieldLink` should be used to request text input from the user through a button interface.

## Creating a text field link

- **init(_:prompt:onSubmit:)**: Creates a TextFieldLink which when pressed will request text input from the user.
- **init(prompt:label:onSubmit:)**: Creates a TextFieldLink which when pressed will request text input from the user.

## Linking to other content

- **Link**: A control for navigating to a URL.
- **ShareLink**: A view that controls a sharing presentation.
- **SharePreview**: A representation of a type to display in a share preview.
- **HelpLink**: A button with a standard appearance that opens app-specific help documentation.

## Conforms To

- View

