--- 来源：https://developer.apple.com/documentation/SwiftUI/RedactionReasons/placeholder

抓取时间：2025-12-03T06:08:45Z

---

# placeholder

**类型属性**

显示的数据应显示为通用占位符。

## 声明

```swift
static let placeholder: RedactionReasons
```

## 讨论

文本和图像将自动进行遮罩处理，显示为通用占位符，但会保持其原始大小和形状。使用此功能可以创建占位符 UI，而无需直接向用户公开占位符数据。

## 获取编辑原因

- **invalidated**：显示的数据应显示为已失效，等待更新。

- **privacy**：显示的数据应进行模糊处理，以保护隐私信息。


---
source: https://developer.apple.com/documentation/SwiftUI/RedactionReasons/placeholder
crawled: 2025-12-03T06:08:45Z
---

# placeholder

**Type Property**

Displayed data should appear as generic placeholders.

## Declaration

```swift
static let placeholder: RedactionReasons
```

## Discussion

Text and images will be automatically masked to appear as generic placeholders, though maintaining their original size and shape. Use this to create a placeholder UI without directly exposing placeholder data to users.

## Getting redaction reasons

- **invalidated**: Displayed data should appear as invalidated and pending a new update.
- **privacy**: Displayed data should be obscured to protect private information.

