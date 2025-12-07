---
来源： https://developer.apple.com/documentation/SwiftUI/HelpLink
抓取时间：2025-12-02T17:27:17Z
---

# 帮助链接

**Structure**

具有标准外观的按钮，用于打开特定应用程序的帮助文档。

## 声明

```swift
struct HelpLink
```

## 概览

帮助链接可打开与使用环境相关的文档。通常是打开 Apple 帮助手册中的锚点，但也可以执行任意操作，如打开 URL 或打开窗口。

```swift
HelpLink(anchor: "accountSetupHelp")

HelpLink {
    openURL(onlineHelpURL)
}
```

帮助链接有标准的外观，在视图中的位置也是传统的。在警报或确认对话框的操作中使用时，帮助链接会自动放置在尾部顶角。或者在工作表工具栏中使用时，帮助链接会自动放在下前角。

```swift
struct SheetContentView: View {
    var body: some View {
        Form {
             ...
        }
        .toolbar {
            ToolbarItem(.confirmationAction) {
                Button("Save") { ... }
            }
            ToolbarItem(.cancellationAction) {
                Button("Cancel") { ... }
            }
            ToolbarItem {
                HelpLink(anchor: "sheetHelp")
            }
         }
    }
}
```

## 创建帮助链接

- **init(action:)**：用指定的操作创建一个新的帮助链接。
- **init(destination:)**：构造一个新的帮助链接，打开指定的目标 URL。
- **init(anchor:)**：在主应用程序捆绑包的图书中使用指定锚点构建新的帮助链接。
- **init(anchor:book:)**：使用指定的锚点和书籍构建新的帮助链接。

## 链接到其他内容

- **Link**：用于导航到 URL 的控件。
- **ShareLink**：控制共享演示的视图。
- **SharePreview**：要在共享预览中显示的类型的表示。
- **TextFieldLink**：按下时要求用户输入文本的控件。

## 符合

- 查看


---
source: https://developer.apple.com/documentation/SwiftUI/HelpLink
crawled: 2025-12-02T17:27:17Z
---

# HelpLink

**Structure**

A button with a standard appearance that opens app-specific help documentation.

## Declaration

```swift
struct HelpLink
```

## Overview

A help link opens documentation relevant to the context where they are used. Typically this is by opening to an anchor in an Apple Help book, but can also perform an arbitrary action such as opening a URL or opening a window.

```swift
HelpLink(anchor: "accountSetupHelp")

HelpLink {
    openURL(onlineHelpURL)
}
```

Help links have a standard appearance, as well as conventional placement within a view. When used within an alert or confirmation dialog’s actions, the help link will automatically be placed in the top trailing corner. Or when used in a sheet toolbar, the help link is automatically placed in the lower leading corner.

```swift
struct SheetContentView: View {
    var body: some View {
        Form {
             ...
        }
        .toolbar {
            ToolbarItem(.confirmationAction) {
                Button("Save") { ... }
            }
            ToolbarItem(.cancellationAction) {
                Button("Cancel") { ... }
            }
            ToolbarItem {
                HelpLink(anchor: "sheetHelp")
            }
         }
    }
}
```

## Creating a help link

- **init(action:)**: Constructs a new help link with the specified action.
- **init(destination:)**: Constructs a new help link that opens the specified destination URL.
- **init(anchor:)**: Constructs a new help link with the specified anchor in the main app bundle’s book.
- **init(anchor:book:)**: Constructs a new help link with the specified anchor and book.

## Linking to other content

- **Link**: A control for navigating to a URL.
- **ShareLink**: A view that controls a sharing presentation.
- **SharePreview**: A representation of a type to display in a share preview.
- **TextFieldLink**: A control that requests text input from the user when pressed.

## Conforms To

- View

