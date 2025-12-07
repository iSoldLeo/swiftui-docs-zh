---
来源： https://developer.apple.com/documentation/SwiftUI/TextSelectionAffinity/downstream
抓取时间： 2025-12-03T06:17:39Z
---

# TextSelectionAffinity.downstream

**Case**

下游选择亲和性。在这种情况下，光标与紧随其后的字符相关联。

## 声明

```swift
case downstream
```

## 讨论

在我们的示例`hello|مرحبا`中，由于下游亲和力，光标将与 "مرحبا "的第一个字符相关联。如果您输入的是阿拉伯语，由于阿拉伯语是从右到左书写的，因此这些字符会添加到 "مرحبا "中的 "م "之前。


---
source: https://developer.apple.com/documentation/SwiftUI/TextSelectionAffinity/downstream
crawled: 2025-12-03T06:17:39Z
---

# TextSelectionAffinity.downstream

**Case**

An downstream selection affinity. In this case, the cursor is associated with the character immediately after it.

## Declaration

```swift
case downstream
```

## Discussion

In the context of our example `hello|مرحبا`, with a downstream affinity, the cursor would be associated with the first character of “مرحبا”. If you were to type in Arabic, the characters would be added before the “م” in “مرحبا”, since Arabic is written right-to-left.

