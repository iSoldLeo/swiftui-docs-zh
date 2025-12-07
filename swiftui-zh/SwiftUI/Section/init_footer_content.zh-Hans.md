---
来源： https://developer.apple.com/documentation/SwiftUI/Section/init(footer:content:)
抓取时间： 2025-12-01T02:41:25Z
---

# init(footer:content:)

**Initializer**

创建一个带有页脚和所提供部分内容的部分。

## 声明

```swift
init(footer: Footer, @ViewBuilder content: () -> Content)
```

## 参数

- **footer**：用作章节页脚的视图。
- **content**：节的内容。

## 过时的符号

- **init(header:content:)**：创建带有页眉和所提供章节内容的章节。
- **init(header:footer:content:)**：创建带有页眉、页脚和所提供部分内容的部分。
- **collapsible(_:)**：设置用户是否可以折叠栏目。


---
source: https://developer.apple.com/documentation/SwiftUI/Section/init(footer:content:)
crawled: 2025-12-01T02:41:25Z
---

# init(footer:content:)

**Initializer**

Creates a section with a footer and the provided section content.

## Declaration

```swift
init(footer: Footer, @ViewBuilder content: () -> Content)
```

## Parameters

- **footer**: A view to use as the section’s footer.
- **content**: The section’s content.

## Deprecated symbols

- **init(header:content:)**: Creates a section with a header and the provided section content.
- **init(header:footer:content:)**: Creates a section with a header, footer, and the provided section content.
- **collapsible(_:)**: Sets whether a section can be collapsed by the user.

