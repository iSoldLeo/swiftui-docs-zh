--- 来源：https://developer.apple.com/documentation/SwiftUI/TextRenderer/sizeThatFits(proposal:text:)

抓取时间：2025-12-02T20:59:23Z

---

# sizeThatFits(proposal:text:)

**实例方法**

返回 `proposal` 中文本的大小。提供的 `text` 代理值可用于查询底层文本布局的大小调整行为。

## 声明

```swift
func sizeThatFits(proposal: ProposedViewSize, text: TextProxy) -> CGSize
```

## 讨论

此函数的默认实现返回 `text.size(proposal)`。


---
source: https://developer.apple.com/documentation/SwiftUI/TextRenderer/sizeThatFits(proposal:text:)
crawled: 2025-12-02T20:59:23Z
---

# sizeThatFits(proposal:text:)

**Instance Method**

Returns the size of the text in `proposal`. The provided `text` proxy value may be used to query the sizing behavior of the underlying text layout.

## Declaration

```swift
func sizeThatFits(proposal: ProposedViewSize, text: TextProxy) -> CGSize
```

## Discussion

The default implementation of this function returns `text.size(proposal)`.

