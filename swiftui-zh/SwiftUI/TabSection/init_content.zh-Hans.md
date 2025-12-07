---
来源： https://developer.apple.com/documentation/SwiftUI/TabSection/init(内容：)
抓取时间： 2025-12-02T20:59:48Z
---

# init(content:)

**Initializer**

使用提供的章节内容创建章节。

## 声明

```swift
init(@TabContentBuilder<SelectionValue> content: () -> Content) where Header == EmptyView, Footer == EmptyView
```

## 参数

- **content**：节的内容。

## 创建标签部分

- **init(_:content:)**：用提供的内容创建一个部分。
- **init(content:header:)**：用标题和提供的节内容创建节。


---
source: https://developer.apple.com/documentation/SwiftUI/TabSection/init(content:)
crawled: 2025-12-02T20:59:48Z
---

# init(content:)

**Initializer**

Creates a section with the provided section content.

## Declaration

```swift
init(@TabContentBuilder<SelectionValue> content: () -> Content) where Header == EmptyView, Footer == EmptyView
```

## Parameters

- **content**: The section’s content.

## Creating a tab section

- **init(_:content:)**: Creates a section with the provided content.
- **init(content:header:)**: Creates a section with a header and the provided section content.

