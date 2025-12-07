---
来源：https://developer.apple.com/documentation/SwiftUI/HelpLink/init(anchor:book:)
抓取时间：2025-12-01T10:31:28Z
---

# init(anchor:book:)

**Initializer**

使用指定的锚点和书籍构建新的帮助链接。

## 声明

```swift
init(anchor: NSHelpManager.AnchorName, book: NSHelpManager.BookName)
```

## 参数

- **anchor**：帮助手册中要打开的锚点。
- **book**：要打开的特定书籍名称。

## 创建帮助链接

- **init(action:)**：用指定的操作创建一个新的帮助链接。
- **init(destination:)**：构造一个新的帮助链接，打开指定的目标 URL。
- **init(anchor:)**：在主应用程序捆绑包的图书中使用指定的锚点构建新的帮助链接。


---
source: https://developer.apple.com/documentation/SwiftUI/HelpLink/init(anchor:book:)
crawled: 2025-12-01T10:31:28Z
---

# init(anchor:book:)

**Initializer**

Constructs a new help link with the specified anchor and book.

## Declaration

```swift
init(anchor: NSHelpManager.AnchorName, book: NSHelpManager.BookName)
```

## Parameters

- **anchor**: The anchor within the help book to open to.
- **book**: The specific book name to open.

## Creating a help link

- **init(action:)**: Constructs a new help link with the specified action.
- **init(destination:)**: Constructs a new help link that opens the specified destination URL.
- **init(anchor:)**: Constructs a new help link with the specified anchor in the main app bundle’s book.

