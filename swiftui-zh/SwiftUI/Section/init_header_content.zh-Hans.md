---
来源： https://developer.apple.com/documentation/SwiftUI/Section/init(header:content:)
抓取时间： 2025-12-01T02:41:24Z
---

# init(header:content:)

**Initializer**

用标题和提供的章节内容创建章节。

## 声明

```swift
init(header: Parent, @ViewBuilder content: () -> Content)
```

## 参数

- **header**：用作章节标题的视图。
- **content**：节的内容。

## 过时的符号

- **init(footer:content:)**：创建带有页脚和所提供章节内容的章节。
- **init(header:footer:content:)**：创建带有页眉、页脚和所提供部分内容的部分。
- **collapsible(_:)**：设置用户是否可以折叠栏目。


---
source: https://developer.apple.com/documentation/SwiftUI/Section/init(header:content:)
crawled: 2025-12-01T02:41:24Z
---

# init(header:content:)

**Initializer**

Creates a section with a header and the provided section content.

## Declaration

```swift
init(header: Parent, @ViewBuilder content: () -> Content)
```

## Parameters

- **header**: A view to use as the section’s header.
- **content**: The section’s content.

## Deprecated symbols

- **init(footer:content:)**: Creates a section with a footer and the provided section content.
- **init(header:footer:content:)**: Creates a section with a header, footer, and the provided section content.
- **collapsible(_:)**: Sets whether a section can be collapsed by the user.

