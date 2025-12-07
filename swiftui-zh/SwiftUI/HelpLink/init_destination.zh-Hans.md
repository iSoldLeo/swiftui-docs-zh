---
来源： https://developer.apple.com/documentation/SwiftUI/HelpLink/init(目的地：)
抓取时间： 2025-12-01T10:31:27Z
---

# init(destination:)

**Initializer**

构造一个新的帮助链接，打开指定的目标 URL。

## 声明

```swift
init(destination: URL)
```

## 参数

- **destination**：点击按钮时要打开的 URL。

## 讨论

如果您希望使用标准的帮助按钮外观来打开一个网站链接，请使用此初始化程序。

您可以用自定义的[OpenURLAction](../OpenURLAction.zh-Hans.md)设置[openURL](../EnvironmentValues/openURL.zh-Hans.md)环境值，从而在点击按钮时覆盖默认行为。

## 创建帮助链接

- **init(action:)**：用指定的操作创建一个新的帮助链接。
- **init(anchor:)**：在主应用程序捆绑包的图书中使用指定的锚点构建新的帮助链接。
- **init(anchor:book:)**：使用指定的锚点和书籍构建新的帮助链接。


---
source: https://developer.apple.com/documentation/SwiftUI/HelpLink/init(destination:)
crawled: 2025-12-01T10:31:27Z
---

# init(destination:)

**Initializer**

Constructs a new help link that opens the specified destination URL.

## Declaration

```swift
init(destination: URL)
```

## Parameters

- **destination**: The URL to open when the button is clicked.

## Discussion

Use this initializer when you want the standard help button appearance that opens a link to a website.

You can override the default behavior when the button is clicked by setting the [openURL](../EnvironmentValues/openURL.zh-Hans.md) environment value with a custom [OpenURLAction](../OpenURLAction.zh-Hans.md).

## Creating a help link

- **init(action:)**: Constructs a new help link with the specified action.
- **init(anchor:)**: Constructs a new help link with the specified anchor in the main app bundle’s book.
- **init(anchor:book:)**: Constructs a new help link with the specified anchor and book.

