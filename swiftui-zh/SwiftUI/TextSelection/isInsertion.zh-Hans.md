---
来源： https://developer.apple.com/documentation/SwiftUI/TextSelection/isInsertion
抓取时间： 2025-12-03T06:17:37Z
---

# isInsertion

**实例属性**

如果选中点是插入点，则返回 `true`。

## 声明

```swift
var isInsertion: Bool { get }
```

## 讨论

插入点实际上代表了一个不包含字符的范围，表示字符串中的一个位置。该位置指的是文本中将插入新字符的位置。换句话说，它表示开始和结束索引相等的情况。


---
source: https://developer.apple.com/documentation/SwiftUI/TextSelection/isInsertion
crawled: 2025-12-03T06:17:37Z
---

# isInsertion

**Instance Property**

Return `true` if the selection is an insertion point.

## Declaration

```swift
var isInsertion: Bool { get }
```

## Discussion

An insertion point effectively represents a range that contains no characters, indicating a location in the string. This location refers to the point in the text where new characters will be inserted. In other words, it represents cases when the start and end index are equal.

