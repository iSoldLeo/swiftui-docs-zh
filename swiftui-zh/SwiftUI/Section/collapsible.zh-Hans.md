---
来源： https://developer.apple.com/documentation/SwiftUI/Section/collapsible(_:)
抓取时间： 2025-12-02T21:50:32Z
---

# collapsible(_:)

**实例方法**

设置用户是否可以折叠部分。

## 声明

```swift
func collapsible(_ collapsible: Bool) -> some View

```

## 讨论

此修饰符仅适用于 [List](../List.zh-Hans.md) 视图中具有 [sidebar](../ListStyle/sidebar.zh-Hans.md) 样式的部分。

## 过时的符号

- **init(header:content:)**：创建带有页眉和所提供章节内容的章节。
- **init(footer:content:)**：创建带有页脚和所提供章节内容的章节。
- **init(header:footer:content:)**：创建带有页眉、页脚和所提供部分内容的部分。


---
source: https://developer.apple.com/documentation/SwiftUI/Section/collapsible(_:)
crawled: 2025-12-02T21:50:32Z
---

# collapsible(_:)

**Instance Method**

Sets whether a section can be collapsed by the user.

## Declaration

```swift
func collapsible(_ collapsible: Bool) -> some View

```

## Discussion

This modifier only applies to sections in [List](../List.zh-Hans.md) views that have the [sidebar](../ListStyle/sidebar.zh-Hans.md) style.

## Deprecated symbols

- **init(header:content:)**: Creates a section with a header and the provided section content.
- **init(footer:content:)**: Creates a section with a footer and the provided section content.
- **init(header:footer:content:)**: Creates a section with a header, footer, and the provided section content.

