--- 来源：https://developer.apple.com/documentation/swiftui/menu

抓取时间：2025-12-03T06:23:58Z

---

# 菜单

**Structure**

用于显示操作菜单的控件。

## 声明

```swift
struct Menu<Label, Content> where Label : View, Content : View
```

## 概述

以下示例展示了一个包含三个按钮的菜单和一个子菜单，该子菜单本身也包含三个按钮。

```swift
Menu("Actions") {
    Button("Duplicate", action: duplicate)
    Button("Rename", action: rename)
    Button("Delete…", action: delete)
    Menu("Copy") {
        Button("Copy", action: copy)
        Button("Copy Formatted", action: copyFormatted)
        Button("Copy Library Path", action: copyPath)
    }
}
```

您可以像上例所示，使用 [LocalizedStringKey](LocalizedStringKey.zh-Hans.md) 创建菜单标题，或者使用视图构建器创建多个视图，例如图像视图和文本视图：

```swift
Menu {
    Button("Open in Preview", action: openInPreview)
    Button("Save as PDF", action: saveAsPDF)
} label: {
    Label("PDF", systemImage: "doc.fill")
}
```

要支持菜单项的副标题，请使用视图构建器初始化 `Button`，该构建器会创建多个 `Text` 视图，其中第一个文本表示标题，第二个文本表示副标题。同样的方法也适用于其他控件，例如 `Toggle`：

```swift
Menu {
    Button(action: openInPreview) {
        Text("Open in Preview")
        Text("View the document in Preview")
    }
    Button(action: saveAsPDF) {
        Text("Save as PDF")
        Text("Export the document as a PDF file")
    }
} label: {
    Label("PDF", systemImage: "doc.fill")
}
```

### 主要操作

菜单可以创建自定义的主要操作。主要操作将在用户点击或单击控件主体时执行，而菜单的显示将通过辅助手势（例如长按或单击菜单指示器）进行。以下示例创建一个添加书签的菜单，其中包含以菜单形式呈现的高级选项。

```swift
Menu {
    Button(action: addCurrentTabToReadingList) {
        Label("Add to Reading List", systemImage: "eyeglasses")
    }
    Button(action: bookmarkAll) {
        Label("Add Bookmarks for All Tabs", systemImage: "book")
    }
    Button(action: show) {
        Label("Show All Bookmarks", systemImage: "books.vertical")
    }
} label: {
    Label("Add Bookmark", systemImage: "book")
} primaryAction: {
    addBookmark()
}
```

### 菜单样式

使用 [menuStyle(_:)](View/menuStyle.zh-Hans.md) 修饰符更改视图中所有菜单的样式。以下示例演示如何应用自定义样式：

```swift
Menu("Editing") {
    Button("Set In Point", action: setInPoint)
    Button("Set Out Point", action: setOutPoint)
}
.menuStyle(EditingControlsMenuStyle())
```

## 从内容创建菜单

- **init(_:content:)**：创建一个菜单，其标签由本地化字符串键生成。

- **init(content:label:)**：创建一个带有自定义标签的菜单。

- **init(_:image:content:)**：创建一个菜单，其标签由本地化字符串键和图像资源生成。

- **init(_:systemImage:content:)**：创建一个菜单，其标签由本地化字符串键和系统图像生成。

## 创建带有主操作的菜单

- **init(_:content:primaryAction:)**：创建一个带有自定义主操作的菜单，该菜单的标签由本地化字符串键生成。

- **init(content:label:primaryAction:)**：创建一个带有自定义主操作和自定义标签的菜单。

- **init(_:image:content:primaryAction:)**：创建一个带有自定义主操作的菜单，该菜单的标签由本地化字符串键生成。

- **init(_:systemImage:content:primaryAction:)**：创建一个带有自定义主操作的菜单，该菜单的标签由本地化字符串键和系统图像生成。

## 根据配置创建菜单

- **init(_:)**：根据样式配置创建菜单。

## 创建菜单

- **使用自适应控件填充 SwiftUI 菜单**：通过在菜单中填充控件并以直观的方式组织内容来改进您的应用程序。

- **menuStyle(_:)**：设置此视图中菜单的样式。

## 符合以下视图

- 视图


---
source: https://developer.apple.com/documentation/swiftui/menu
crawled: 2025-12-03T06:23:58Z
---

# Menu

**Structure**

A control for presenting a menu of actions.

## Declaration

```swift
struct Menu<Label, Content> where Label : View, Content : View
```

## Overview

The following example presents a menu of three buttons and a submenu, which contains three buttons of its own.

```swift
Menu("Actions") {
    Button("Duplicate", action: duplicate)
    Button("Rename", action: rename)
    Button("Delete…", action: delete)
    Menu("Copy") {
        Button("Copy", action: copy)
        Button("Copy Formatted", action: copyFormatted)
        Button("Copy Library Path", action: copyPath)
    }
}
```

You can create the menu’s title with a [LocalizedStringKey](LocalizedStringKey.zh-Hans.md), as seen in the previous example, or with a view builder that creates multiple views, such as an image and a text view:

```swift
Menu {
    Button("Open in Preview", action: openInPreview)
    Button("Save as PDF", action: saveAsPDF)
} label: {
    Label("PDF", systemImage: "doc.fill")
}
```

To support subtitles on menu items, initialize your `Button` with a view builder that creates multiple `Text` views where the first text represents the title and the second text represents the subtitle. The same approach applies to other controls such as `Toggle`:

```swift
Menu {
    Button(action: openInPreview) {
        Text("Open in Preview")
        Text("View the document in Preview")
    }
    Button(action: saveAsPDF) {
        Text("Save as PDF")
        Text("Export the document as a PDF file")
    }
} label: {
    Label("PDF", systemImage: "doc.fill")
}
```



### Primary action

Menus can be created with a custom primary action. The primary action will be performed when the user taps or clicks on the body of the control, and the menu presentation will happen on a secondary gesture, such as on long press or on click of the menu indicator. The following example creates a menu that adds bookmarks, with advanced options that are presented in a menu.

```swift
Menu {
    Button(action: addCurrentTabToReadingList) {
        Label("Add to Reading List", systemImage: "eyeglasses")
    }
    Button(action: bookmarkAll) {
        Label("Add Bookmarks for All Tabs", systemImage: "book")
    }
    Button(action: show) {
        Label("Show All Bookmarks", systemImage: "books.vertical")
    }
} label: {
    Label("Add Bookmark", systemImage: "book")
} primaryAction: {
    addBookmark()
}
```

### Styling menus

Use the [menuStyle(_:)](View/menuStyle.zh-Hans.md) modifier to change the style of all menus in a view. The following example shows how to apply a custom style:

```swift
Menu("Editing") {
    Button("Set In Point", action: setInPoint)
    Button("Set Out Point", action: setOutPoint)
}
.menuStyle(EditingControlsMenuStyle())
```

## Creating a menu from content

- **init(_:content:)**: Creates a menu that generates its label from a localized string key.
- **init(content:label:)**: Creates a menu with a custom label.
- **init(_:image:content:)**: Creates a menu that generates its label from a localized string key and image resource.
- **init(_:systemImage:content:)**: Creates a menu that generates its label from a localized string key and system image.

## Creating a menu with a primary action

- **init(_:content:primaryAction:)**: Creates a menu with a custom primary action that generates its label from a localized string key.
- **init(content:label:primaryAction:)**: Creates a menu with a custom primary action and custom label.
- **init(_:image:content:primaryAction:)**: Creates a menu with a custom primary action that generates its label from a localized string key.
- **init(_:systemImage:content:primaryAction:)**: Creates a menu with a custom primary action that generates its label from a localized string key and system image.

## Creating a menu from a configuration

- **init(_:)**: Creates a menu based on a style configuration.

## Creating a menu

- **Populating SwiftUI menus with adaptive controls**: Improve your app by populating menus with controls and organizing your content intuitively.
- **menuStyle(_:)**: Sets the style for menus within this view.

## Conforms To

- View

