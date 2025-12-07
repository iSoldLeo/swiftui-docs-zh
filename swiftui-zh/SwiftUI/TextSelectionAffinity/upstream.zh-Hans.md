---
来源： https://developer.apple.com/documentation/SwiftUI/TextSelectionAffinity/upstream
抓取时间： 2025-12-03T06:17:40Z
---

# TextSelectionAffinity.upstream

**Case**

上游选择亲和性。在这种情况下，光标与紧靠其前的字符相关联。

## 声明

```swift
case upstream
```

## 讨论

在我们的示例`hello|مرحبا` 中，如果使用上游亲和素，光标将与 "hello "中的 "o "相关联。如果您键入的是英文，则会在 "hello "中的 "o "后继续添加字符。


---
source: https://developer.apple.com/documentation/SwiftUI/TextSelectionAffinity/upstream
crawled: 2025-12-03T06:17:40Z
---

# TextSelectionAffinity.upstream

**Case**

An upstream selection affinity. In this case, the cursor is associated with the character immediately before it.

## Declaration

```swift
case upstream
```

## Discussion

In the context of our example  `hello|مرحبا`, with an upstream affinity, the cursor would be associated with the “o” from “hello”. If you were to type in English, the characters would continue to be added after the “o” in “hello”.

