---
来源： https://developer.apple.com/documentation/SwiftUI/TabSection/init(_:content:)
抓取时间： 2025-12-01T00:43:48Z
---

# init(_:content:)

**Initializer**

用提供的内容创建一个部分。

## 声明

```swift
init(_ titleKey: LocalizedStringKey, @TabContentBuilder<SelectionValue> content: () -> Content) where Header == Text, Footer == EmptyView
```

## 参数

- **titleKey**：节首的本地化字符串关键字标签。
- **content**：节的内容。

## 创建分节标签

- **init(content:)**：用提供的节内容创建一个节。
- **init(content:header:)**：创建带有页眉和所提供章节内容的章节。


---
source: https://developer.apple.com/documentation/SwiftUI/TabSection/init(_:content:)
crawled: 2025-12-01T00:43:48Z
---

# init(_:content:)

**Initializer**

Creates a section with the provided content.

## Declaration

```swift
init(_ titleKey: LocalizedStringKey, @TabContentBuilder<SelectionValue> content: () -> Content) where Header == Text, Footer == EmptyView
```

## Parameters

- **titleKey**: The localized string key label for the section’s header.
- **content**: The section’s content.

## Creating a tab section

- **init(content:)**: Creates a section with the provided section content.
- **init(content:header:)**: Creates a section with a header and the provided section content.

