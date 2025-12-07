---
来源：https://developer.apple.com/documentation/SwiftUI/AttributedTextSelection/init(insertionPoint:typingAttributes:)
抓取时间：2025-12-03T06:17:42Z
---

# init(insertionPoint:typingAttributes:)

**Initializer**

将选区初始化为单个插入点。

## 声明

```swift
init(insertionPoint: AttributedString.Index, typingAttributes: AttributeContainer? = nil)
```

## 参数

- **insertionPoint**：字符串的索引，charet 应放置在该处。
- **typingAttributes**：下一个键入字符的属性，或 `nil`（如果应从文本属性中推断）。


---
source: https://developer.apple.com/documentation/SwiftUI/AttributedTextSelection/init(insertionPoint:typingAttributes:)
crawled: 2025-12-03T06:17:42Z
---

# init(insertionPoint:typingAttributes:)

**Initializer**

Initialize a selection to a single insertion point.

## Declaration

```swift
init(insertionPoint: AttributedString.Index, typingAttributes: AttributeContainer? = nil)
```

## Parameters

- **insertionPoint**: The index of the string where the charet should be positioned.
- **typingAttributes**: The attributes for the next character that is typed, or `nil` if they should be inferred from the attributes on the text.

