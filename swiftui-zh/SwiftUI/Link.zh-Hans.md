--- 来源：https://developer.apple.com/documentation/SwiftUI/Link

抓取时间：2025-12-02T17:27:27Z

---

# 链接

**Structure**

用于导航到 URL 的控件。

## 声明

```swift
@MainActor @preconcurrency struct Link<Label> where Label : View
```

## 概述

通过提供目标 URL 和标题来创建链接。标题告诉用户链接的用途，可以是字符串、生成本地化字符串的标题键，或用作标签的视图。以下示例创建指向 `example.com` 的链接，并将标题字符串显示为链接样式的视图：

```swift
Link("View Our Terms of Service",
      destination: URL(string: "https://www.example.com/TOS.html")!)
```

当用户点击 `Link` 时，默认行为取决于 URL 的内容。例如，SwiftUI 会尽可能在关联的应用中打开通用链接，否则会在用户的默认浏览器中打开。或者，您可以通过将 [openURL](EnvironmentValues/openURL.zh-Hans.md) 环境变量设置为自定义的 [OpenURLAction](OpenURLAction.zh-Hans.md) 来覆盖默认行为：

```swift
Link("Visit Our Site", destination: URL(string: "https://www.example.com")!)
    .environment(\.openURL, OpenURLAction { url in
        print("Open \(url)")
        return .handled
    })
```

与其他视图一样，您可以根据链接标签的视图类型，使用标准视图修饰符来设置链接样式。例如，可以使用自定义的 [font(_:)](View/font.zh-Hans.md) 或 [foregroundColor(_:)](View/foregroundColor.zh-Hans.md) 来修改 [Text](Text.zh-Hans.md) 标签，从而自定义链接在应用 UI 中的外观。

## 创建链接

- **init(_:destination:)**：创建一个控件，该控件包含一个 URL 和一个标题键，用于导航到该 URL。

- **init(destination:label:)**：创建一个控件，包含一个 URL 和一个标签，用于导航到指定的 URL。

## 链接到其他内容

- **ShareLink**：一个用于控制共享演示的视图。

- **SharePreview**：一种要在共享预览中显示的类型的表示形式。

- **TextFieldLink**：一个控件，按下时会请求用户输入文本。

- **HelpLink**：一个具有标准外观的按钮，用于打开特定于应用程序的帮助文档。

## 符合以下规范

- 视图


---
source: https://developer.apple.com/documentation/SwiftUI/Link
crawled: 2025-12-02T17:27:27Z
---

# Link

**Structure**

A control for navigating to a URL.

## Declaration

```swift
@MainActor @preconcurrency struct Link<Label> where Label : View
```

## Overview

Create a link by providing a destination URL and a title. The title tells the user the purpose of the link, and can be a string, a title key that produces a localized string, or a view that acts as a label. The example below creates a link to `example.com` and displays the title string as a link-styled view:

```swift
Link("View Our Terms of Service",
      destination: URL(string: "https://www.example.com/TOS.html")!)
```

When a user taps or clicks a `Link`, the default behavior depends on the contents of the URL. For example, SwiftUI opens a Universal Link in the associated app if possible, or in the user’s default web browser if not. Alternatively, you can override the default behavior by setting the [openURL](EnvironmentValues/openURL.zh-Hans.md) environment value with a custom [OpenURLAction](OpenURLAction.zh-Hans.md):

```swift
Link("Visit Our Site", destination: URL(string: "https://www.example.com")!)
    .environment(\.openURL, OpenURLAction { url in
        print("Open \(url)")
        return .handled
    })
```

As with other views, you can style links using standard view modifiers depending on the view type of the link’s label. For example, a [Text](Text.zh-Hans.md) label could be modified with a custom [font(_:)](View/font.zh-Hans.md) or [foregroundColor(_:)](View/foregroundColor.zh-Hans.md) to customize the appearance of the link in your app’s UI.

## Creating a link

- **init(_:destination:)**: Creates a control, consisting of a URL and a title key, used to navigate to a URL.
- **init(destination:label:)**: Creates a control, consisting of a URL and a label, used to navigate to the given URL.

## Linking to other content

- **ShareLink**: A view that controls a sharing presentation.
- **SharePreview**: A representation of a type to display in a share preview.
- **TextFieldLink**: A control that requests text input from the user when pressed.
- **HelpLink**: A button with a standard appearance that opens app-specific help documentation.

## Conforms To

- View

