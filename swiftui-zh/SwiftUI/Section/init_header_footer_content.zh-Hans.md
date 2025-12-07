---
来源: https://developer.apple.com/documentation/SwiftUI/Section/init(页眉:页脚:内容:)
抓取时间： 2025-12-01T02:41:26Z
---

# init(header:footer:content:)

**Initializer**

创建一个包含页眉、页脚和提供的章节内容的章节。

## 声明

```swift
init(header: Parent, footer: Footer, @ViewBuilder content: () -> Content)
```

## 参数

- **header**：用作章节标题的视图。
- **footer**：用作章节页脚的视图。
- **content**：节的内容。

## 过时的符号

- **init(header:content:)**：创建带有页眉和所提供章节内容的章节。
- **init(footer:content:)**：创建带有页脚和所提供章节内容的章节。
- **collapsible(_:)**：设置用户是否可以折叠节。


---
source: https://developer.apple.com/documentation/SwiftUI/Section/init(header:footer:content:)
crawled: 2025-12-01T02:41:26Z
---

# init(header:footer:content:)

**Initializer**

Creates a section with a header, footer, and the provided section content.

## Declaration

```swift
init(header: Parent, footer: Footer, @ViewBuilder content: () -> Content)
```

## Parameters

- **header**: A view to use as the section’s header.
- **footer**: A view to use as the section’s footer.
- **content**: The section’s content.

## Deprecated symbols

- **init(header:content:)**: Creates a section with a header and the provided section content.
- **init(footer:content:)**: Creates a section with a footer and the provided section content.
- **collapsible(_:)**: Sets whether a section can be collapsed by the user.

