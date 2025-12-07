---
来源：https://developer.apple.com/documentation/SwiftUI/Section/init(content:footer:)
抓取时间： 2025-12-02T21:50:27Z
---

# init(content:footer:)

**Initializer**

创建一个带有页脚和所提供部分内容的部分。

## 声明

```swift
init(@ViewBuilder content: () -> Content, @ViewBuilder footer: () -> Footer)
```

## 参数

- **content**：节的内容。
- **footer**：用作章节页脚的视图。

## 添加页眉和页脚

- **init(content:header:)**：创建带有页眉和所提供的章节内容的章节。
- **init(content:header:footer:)**：创建带有页眉、页脚和所提供部分内容的部分。


---
source: https://developer.apple.com/documentation/SwiftUI/Section/init(content:footer:)
crawled: 2025-12-02T21:50:27Z
---

# init(content:footer:)

**Initializer**

Creates a section with a footer and the provided section content.

## Declaration

```swift
init(@ViewBuilder content: () -> Content, @ViewBuilder footer: () -> Footer)
```

## Parameters

- **content**: The section’s content.
- **footer**: A view to use as the section’s footer.

## Adding headers and footers

- **init(content:header:)**: Creates a section with a header and the provided section content.
- **init(content:header:footer:)**: Creates a section with a header, footer, and the provided section content.

