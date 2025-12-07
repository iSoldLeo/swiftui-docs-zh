---
来源：https://developer.apple.com/documentation/SwiftUI/Section/init(内容：页眉：页脚：)
抓取时间： 2025-12-02T21:50:28Z
---

# init(content:header:footer:)

**Initializer**

创建一个包含页眉、页脚和提供的部分内容的部分。

## 声明

```swift
init(@ViewBuilder content: () -> Content, @ViewBuilder header: () -> Parent, @ViewBuilder footer: () -> Footer)
```

## 参数

- **content**：节的内容。
- **header**：用作章节标题的视图。
- **footer**：用作章节页脚的视图。

## 添加页眉和页脚

- **init(content:header:)**：创建带有页眉和所提供的章节内容的章节。
- **init(content:footer:)**：创建带有页脚和所提供章节内容的章节。


---
source: https://developer.apple.com/documentation/SwiftUI/Section/init(content:header:footer:)
crawled: 2025-12-02T21:50:28Z
---

# init(content:header:footer:)

**Initializer**

Creates a section with a header, footer, and the provided section content.

## Declaration

```swift
init(@ViewBuilder content: () -> Content, @ViewBuilder header: () -> Parent, @ViewBuilder footer: () -> Footer)
```

## Parameters

- **content**: The section’s content.
- **header**: A view to use as the section’s header.
- **footer**: A view to use as the section’s footer.

## Adding headers and footers

- **init(content:header:)**: Creates a section with a header and the provided section content.
- **init(content:footer:)**: Creates a section with a footer and the provided section content.

