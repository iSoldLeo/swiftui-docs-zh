---
来源：https://developer.apple.com/documentation/SwiftUI/TabSection/init(content:header:)
抓取时间： 2025-12-02T20:59:49Z
---

# init(content:header:)

**Initializer**

创建带有页眉和所提供的章节内容的章节。

## 声明

```swift
init(@TabContentBuilder<SelectionValue> content: () -> Content, @ViewBuilder header: () -> Header) where Header : View, Footer == EmptyView
```

## 参数

- **content**：节的内容。
- **header**：用作章节标题的视图。

## 创建分节标签

- **init(content:)**：用提供的节内容创建一个节。
- **init(_:content:)**：使用提供的内容创建节。


---
source: https://developer.apple.com/documentation/SwiftUI/TabSection/init(content:header:)
crawled: 2025-12-02T20:59:49Z
---

# init(content:header:)

**Initializer**

Creates a section with a header and the provided section content.

## Declaration

```swift
init(@TabContentBuilder<SelectionValue> content: () -> Content, @ViewBuilder header: () -> Header) where Header : View, Footer == EmptyView
```

## Parameters

- **content**: The section’s content.
- **header**: A view to use as the section’s header.

## Creating a tab section

- **init(content:)**: Creates a section with the provided section content.
- **init(_:content:)**: Creates a section with the provided content.

