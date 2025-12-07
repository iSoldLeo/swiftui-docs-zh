--- 来源：https://developer.apple.com/documentation/SwiftUI/Configure-Your-Apps-Navigation-Titles

抓取时间：2025-12-03T05:33:52Z

---

# 配置应用导航标题

**Article**

使用导航标题来显示界面的当前导航状态。

## 概述

在 iOS 和 watchOS 上，当导航到导航堆栈中的某个视图时，导航栏会显示该视图的标题。在 iPadOS 上，主要目标导航标题会反映为应用切换器中的窗口标题。同样，在 macOS 上，系统会将主要目标标题用作标题栏、窗口菜单和调度中心中的窗口标题。

最简单的方法是，您可以直接为导航标题修饰符提供一个字符串或本地化字符串键。

```swift
ContentView()
    .navigationTitle("My Title")
```

您可以使用其他导航相关的修饰符进一步自定义应用程序工具栏的标题。例如，您可以使用导航文档修饰符将 [doc://com.apple.documentation/documentation/Foundation/URL] 或符合 [doc://com.apple.documentation/documentation/CoreTransferable/Transferable] 的自定义类型关联到您的视图。

```swift
ContentView()
    .navigationTitle("My Title")
    .navigationDocument(myURL)
```

在 iOS 和 iPadOS 中，此修饰符将创建一个标题，点击应用程序导航栏中的导航标题即可显示菜单。菜单包含与 URL 相关的信息以及用于共享的可拖动图标。

在 macOS 中，此修饰符将创建一个代理图标，用于操作支持该文档的文件。

提供可传输类型时，通常应提供 [SharePreview](SharePreview.zh-Hans.md)，该修饰符提供用于在菜单标题中渲染预览的相应内容。

```swift
ContentView()
    .navigationTitle("My Title")
    .navigationDocument(
        myDocument, 
        preview: SharePreview(
            "My Preview Title", image: myDocument.image))
```

### 重命名

您可以为导航标题修饰符提供文本绑定，SwiftUI 会自动配置工具栏，以便在 iOS 或 macOS 上编辑导航标题。SwiftUI 会自动将导航标题与提供给文本字段的字符串绑定值同步。

您可以为导航标题提供字符串绑定，以配置标题的文本字段。SwiftUI 会自动将重命名操作添加到标题菜单中，与来自应用命令的操作并列显示。

```swift
ContentView()
    .navigationTitle($contentTitle)
```

在 iOS 中，当在导航标题中使用文本字段时，SwiftUI 会在工具栏标题中创建一个按钮。触发此按钮后，导航标题会更新为显示一个内联文本字段，该字段会根据用户输入的内容更新您提供的绑定值。

## 导航标题

- **navigationTitle(_:)**：使用字符串绑定配置视图的导航标题。

- **navigationSubtitle(_:)**：配置视图的副标题，以便于导航。


---
source: https://developer.apple.com/documentation/SwiftUI/Configure-Your-Apps-Navigation-Titles
crawled: 2025-12-03T05:33:52Z
---

# Configure your apps navigation titles

**Article**

Use a navigation title to display the current navigation state of an interface.

## Overview

On iOS and watchOS, when a view is navigated to inside of a navigation stack, the navigation bar displays that view’s title. On iPadOS, the primary destination’s navigation title is reflected as the window’s title in the App Switcher. Similarly on macOS, the system uses the primary destination’s title as the window title in the titlebar, Windows menu and Mission Control.

In its simplest form, you can provide a string or a localized string key to a navigation title modifier directly.

```swift
ContentView()
    .navigationTitle("My Title")
```

The title of your apps toolbar can be further customized using additional navigation related modifiers. For example, you can associate a [doc://com.apple.documentation/documentation/Foundation/URL] or your own type conforming to [doc://com.apple.documentation/documentation/CoreTransferable/Transferable] to your view using the navigation document modifier.

```swift
ContentView()
    .navigationTitle("My Title")
    .navigationDocument(myURL)
```

In iOS and iPadOS, this will construct a title that can present a menu by tapping the navigation title in the app’s navigation bar. The menu contains content providing information related to the URL and a draggable icon for sharing.

In macOS, this item will construct a proxy icon for manipulating the file backing the document.

When providing a transferable type, you should typically provide a [SharePreview](SharePreview.zh-Hans.md) which provides the appropriate content for rendering the preview in the header of the menu.

```swift
ContentView()
    .navigationTitle("My Title")
    .navigationDocument(
        myDocument, 
        preview: SharePreview(
            "My Preview Title", image: myDocument.image))
```

### Renaming

You can provide a text binding to the navigation title modifier and SwiftUI will automatically configure the toolbar to allow editing of the navigation title on iOS or macOS. SwiftUI automatically syncs the navigation title with the value of the string binding provided to the text field.

You can provide a string binding to the navigation title to configure the title’s text field. SwiftUI will automatically place a rename action in the title menu alongside the actions originating from your app’s commands.

```swift
ContentView()
    .navigationTitle($contentTitle)
```

In iOS, when using a text field in a navigation title, SwiftUI creates a button in the toolbar title. When triggered, this button updates the navigation title to display an inline text field that will update the binding you provide as the user types.

## Navigation titles

- **navigationTitle(_:)**: Configures the view’s title for purposes of navigation, using a string binding.
- **navigationSubtitle(_:)**: Configures the view’s subtitle for purposes of navigation.

