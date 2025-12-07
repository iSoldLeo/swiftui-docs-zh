---
来源：https://developer.apple.com/documentation/SwiftUI/Section/init(isExpanded:content:header:)
抓取时间： 2025-12-01T02:41:23Z
---

# init(isExpanded:content:header:)

**Initializer**

创建一个包含页眉、提供的章节内容和代表章节扩展状态的绑定的章节。

## 声明

```swift
init(isExpanded: Binding<Bool>, @ViewBuilder content: () -> Content, @ViewBuilder header: () -> Parent)
```

## 参数

- **isExpanded**：与布尔值的绑定，该布尔值决定部分的展开状态（展开或折叠）。
- **content**：节的内容。
- **header**：用作章节标题的视图。

## 控制可折叠性

- **init(_:isExpanded:content:)**：用提供的章节内容创建一个章节。


---
source: https://developer.apple.com/documentation/SwiftUI/Section/init(isExpanded:content:header:)
crawled: 2025-12-01T02:41:23Z
---

# init(isExpanded:content:header:)

**Initializer**

Creates a section with a header, the provided section content, and a binding representing the section’s expansion state.

## Declaration

```swift
init(isExpanded: Binding<Bool>, @ViewBuilder content: () -> Content, @ViewBuilder header: () -> Parent)
```

## Parameters

- **isExpanded**: A binding to a Boolean value that determines the section’s expansion state (expanded or collapsed).
- **content**: The section’s content.
- **header**: A view to use as the section’s header.

## Controlling collapsibility

- **init(_:isExpanded:content:)**: Creates a section with the provided section content.

