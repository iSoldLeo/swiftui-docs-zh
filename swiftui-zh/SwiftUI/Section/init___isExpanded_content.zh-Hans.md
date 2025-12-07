---
来源：https://developer.apple.com/documentation/SwiftUI/Section/init(_:isExpanded:content:)
抓取时间： 2025-12-01T02:41:23Z
---

# init(_:isExpanded:content:)

**Initializer**

使用提供的分节内容创建分节。

## 声明

```swift
init(_ titleKey: LocalizedStringKey, isExpanded: Binding<Bool>, @ViewBuilder content: () -> Content)
```

## 参数

- **titleKey**：小节本地化标题的键值，用于描述小节的内容。
- **isExpanded**：与布尔值的绑定，该布尔值决定章节的展开状态（展开或折叠）。
- **content**：节的内容。

## 控制可折叠性

- **init(isExpanded:content:header:)**：创建一个包含标题、提供的章节内容和代表章节展开状态的绑定的章节。


---
source: https://developer.apple.com/documentation/SwiftUI/Section/init(_:isExpanded:content:)
crawled: 2025-12-01T02:41:23Z
---

# init(_:isExpanded:content:)

**Initializer**

Creates a section with the provided section content.

## Declaration

```swift
init(_ titleKey: LocalizedStringKey, isExpanded: Binding<Bool>, @ViewBuilder content: () -> Content)
```

## Parameters

- **titleKey**: The key for the section’s localized title, which describes the contents of the section.
- **isExpanded**: A binding to a Boolean value that determines the section’s expansion state (expanded or collapsed).
- **content**: The section’s content.

## Controlling collapsibility

- **init(isExpanded:content:header:)**: Creates a section with a header, the provided section content, and a binding representing the section’s expansion state.

