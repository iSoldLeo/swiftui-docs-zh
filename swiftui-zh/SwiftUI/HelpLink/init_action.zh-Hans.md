---
来源：https://developer.apple.com/documentation/SwiftUI/HelpLink/init(action:)
抓取时间：2025-12-01T10:31:26Z
---

# init(action:)

**Initializer**

使用指定的操作构建新的帮助链接。

## 声明

```swift
init(action: @escaping () -> Void)
```

## 参数

- **action**：用户单击按钮时要执行的操作。

## 讨论

如果您希望标准帮助按钮的外观与自定义按钮动作一致，而不希望在 Apple 帮助手册中打开文章，请使用此初始化程序。

## 创建帮助链接

- **init(destination:)**：创建一个新的帮助链接，打开指定的目标 URL。
- **init(anchor:)**：在主应用程序捆绑包的图书中使用指定的锚点构建新的帮助链接。
- **init(anchor:book:)**：使用指定的锚点和书籍构建新的帮助链接。


---
source: https://developer.apple.com/documentation/SwiftUI/HelpLink/init(action:)
crawled: 2025-12-01T10:31:26Z
---

# init(action:)

**Initializer**

Constructs a new help link with the specified action.

## Declaration

```swift
init(action: @escaping () -> Void)
```

## Parameters

- **action**: The action to perform when the user clicks the button.

## Discussion

Use this initializer when you want the standard help button appearance with a custom button action that does not open an article in an Apple Help book.

## Creating a help link

- **init(destination:)**: Constructs a new help link that opens the specified destination URL.
- **init(anchor:)**: Constructs a new help link with the specified anchor in the main app bundle’s book.
- **init(anchor:book:)**: Constructs a new help link with the specified anchor and book.

