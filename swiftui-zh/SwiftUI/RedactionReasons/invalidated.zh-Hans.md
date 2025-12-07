--- 来源：https://developer.apple.com/documentation/SwiftUI/RedactionReasons/invalidated

抓取时间：2025-12-03T06:08:44Z

---

# invalidated

**类型属性**

显示的数据应显示为已失效，等待更新。

## 声明

```swift
static let invalidated: RedactionReasons
```

## 讨论

标记为 `invalidatableContent` 的视图将自动使用标准样式进行编辑，以表明内容已失效，新内容即将可用。

## 获取编辑原因

- **placeholder**：显示的数据应显示为通用占位符。

- **privacy**：显示的数据应被模糊处理以保护隐私信息。


---
source: https://developer.apple.com/documentation/SwiftUI/RedactionReasons/invalidated
crawled: 2025-12-03T06:08:44Z
---

# invalidated

**Type Property**

Displayed data should appear as invalidated and pending a new update.

## Declaration

```swift
static let invalidated: RedactionReasons
```

## Discussion

Views marked with `invalidatableContent` will be automatically redacted with a standard styling indicating the content is invalidated and new content will be available soon.

## Getting redaction reasons

- **placeholder**: Displayed data should appear as generic placeholders.
- **privacy**: Displayed data should be obscured to protect private information.

