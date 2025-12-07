---
来源： https://developer.apple.com/documentation/SwiftUI/AttributedTextSelection/Indices/insertionPoint(_:)
抓取时间： 2025-12-04T13:17:11Z
---

# AttributedTextSelection.Indices.insertionPoint(_:)

**Case**

单个插入点的索引。

## 声明

```swift
case insertionPoint(AttributedString.Index)
```

## 讨论

在归属字符串的`startIndex`处的插入点等同于第一个字符前的一个空格。使用`endIndex`的插入点是有效的。它等同于位于归属字符串最后一个字符之后的一个空格。


---
source: https://developer.apple.com/documentation/SwiftUI/AttributedTextSelection/Indices/insertionPoint(_:)
crawled: 2025-12-04T13:17:11Z
---

# AttributedTextSelection.Indices.insertionPoint(_:)

**Case**

The index of a single insertion point.

## Declaration

```swift
case insertionPoint(AttributedString.Index)
```

## Discussion

The an insertion point at the `startIndex` of an attributed string is equivalent to a caret preceding the first character. An insertion point using `endIndex` is valid. It is equivalent to a caret located after the last character in the attributed string.

