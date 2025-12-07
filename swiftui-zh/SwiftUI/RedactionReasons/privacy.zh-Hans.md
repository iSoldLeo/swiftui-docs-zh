--- 来源：https://developer.apple.com/documentation/SwiftUI/RedactionReasons/privacy
抓取时间：2025-12-03T06:08:46Z

---

# 隐私

**类型属性**

显示的数据应进行模糊处理以保护隐私信息。

## 声明

```swift
static let privacy: RedactionReasons
```

## 讨论

标记为 `privacySensitive` 的视图将使用标准样式自动进行编辑。要应用自定义处理，可以从环境中读取编辑原因。

```swift
struct BankingContentView: View {
    @Environment(\.redactionReasons) var redactionReasons

    var body: some View {
        if redactionReasons.contains(.privacy) {
            FullAppCover()
        } else {
            AppContent()
        }
    }
}
```

## 获取编辑原因

- **invalidated**：显示的数据应显示为已失效并等待更新。

- **placeholder**：显示的数据应显示为通用占位符。


---
source: https://developer.apple.com/documentation/SwiftUI/RedactionReasons/privacy
crawled: 2025-12-03T06:08:46Z
---

# privacy

**Type Property**

Displayed data should be obscured to protect private information.

## Declaration

```swift
static let privacy: RedactionReasons
```

## Discussion

Views marked with `privacySensitive` will be automatically redacted using a standard styling. To apply a custom treatment the redaction reason can be read out of the environment.

```swift
struct BankingContentView: View {
    @Environment(\.redactionReasons) var redactionReasons

    var body: some View {
        if redactionReasons.contains(.privacy) {
            FullAppCover()
        } else {
            AppContent()
        }
    }
}
```

## Getting redaction reasons

- **invalidated**: Displayed data should appear as invalidated and pending a new update.
- **placeholder**: Displayed data should appear as generic placeholders.

