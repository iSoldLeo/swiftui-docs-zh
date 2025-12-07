---
来源：https://developer.apple.com/documentation/SwiftUI/Section/init(content:header:)
抓取时间： 2025-12-02T16:23:39Z
---

# init(content:header:)

**Initializer**

创建带有页眉和所提供的章节内容的章节。

## 声明

```swift
init(@ViewBuilder content: () -> Content, @ViewBuilder header: () -> Parent)
```

## 参数

- **content**：节的内容。
- **header**：用作章节标题的视图。

## 添加页眉和页脚

- **init(content:footer:)**：创建带有页脚和所提供章节内容的章节。
- **init(content:header:footer:)**：创建带有页眉、页脚和所提供部分内容的部分。


---
source: https://developer.apple.com/documentation/SwiftUI/Section/init(content:header:)
crawled: 2025-12-02T16:23:39Z
---

# init(content:header:)

**Initializer**

Creates a section with a header and the provided section content.

## Declaration

```swift
init(@ViewBuilder content: () -> Content, @ViewBuilder header: () -> Parent)
```

## Parameters

- **content**: The section’s content.
- **header**: A view to use as the section’s header.

## Adding headers and footers

- **init(content:footer:)**: Creates a section with a footer and the provided section content.
- **init(content:header:footer:)**: Creates a section with a header, footer, and the provided section content.

