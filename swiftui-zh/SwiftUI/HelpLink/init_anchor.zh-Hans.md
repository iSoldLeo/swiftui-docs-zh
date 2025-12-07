---
来源：https://developer.apple.com/documentation/SwiftUI/HelpLink/init(锚点:)
抓取时间：2025-12-03T05:42:16Z
---

# init(anchor:)

**Initializer**

使用主应用程序捆绑包中的指定锚点构建新的帮助链接。

## 声明

```swift
init(anchor: NSHelpManager.AnchorName)
```

## 参数

- **anchor**：要打开的帮助手册中的锚点。

## 讨论

主应用程序捆绑手册的名称由其 Info.plist 文件中的`CFBundleHelpBookName`键定义。

## 创建帮助链接

- **init(action:)**：使用指定的操作构建新的帮助链接。
- **init(destination:)**：构造一个新的帮助链接，打开指定的目标 URL。
- **init(anchor:book:)**：使用指定的锚点和书籍构建新的帮助链接。


---
source: https://developer.apple.com/documentation/SwiftUI/HelpLink/init(anchor:)
crawled: 2025-12-03T05:42:16Z
---

# init(anchor:)

**Initializer**

Constructs a new help link with the specified anchor in the main app bundle’s book.

## Declaration

```swift
init(anchor: NSHelpManager.AnchorName)
```

## Parameters

- **anchor**: The anchor within the help book to open to.

## Discussion

The main app bundle book name is defined by the `CFBundleHelpBookName` key in its Info.plist file.

## Creating a help link

- **init(action:)**: Constructs a new help link with the specified action.
- **init(destination:)**: Constructs a new help link that opens the specified destination URL.
- **init(anchor:book:)**: Constructs a new help link with the specified anchor and book.

