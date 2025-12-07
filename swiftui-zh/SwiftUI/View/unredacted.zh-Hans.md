--- 来源：https://developer.apple.com/documentation/SwiftUI/View/unredacted()

抓取时间：2025-12-02T17:32:55Z

---

# unredacted()

**实例方法**

移除对该视图层级应用任何密文的原因。

## 声明

```swift
nonisolated func unredacted() -> some View

```

## 密文内容

- **为“始终显示”状态设计您的应用**：自定义 watchOS 应用的用户界面，使其能够持续显示。

- **privacySensitive(_:)**：将视图标记为包含敏感的、私密的用户数据。

- **redacted(reason:)**：添加对该视图层级应用密文的原因。

- **redactionReasons**：当前应用于该视图层级的密文原因。

- **isSceneCaptured**：当前捕获状态。

- **RedactionReasons**：对屏幕上显示的数据进行编辑的原因。


---
source: https://developer.apple.com/documentation/SwiftUI/View/unredacted()
crawled: 2025-12-02T17:32:55Z
---

# unredacted()

**Instance Method**

Removes any reason to apply a redaction to this view hierarchy.

## Declaration

```swift
nonisolated func unredacted() -> some View

```

## Redacting private content

- **Designing your app for the Always On state**: Customize your watchOS app’s user interface for continuous display.
- **privacySensitive(_:)**: Marks the view as containing sensitive, private user data.
- **redacted(reason:)**: Adds a reason to apply a redaction to this view hierarchy.
- **redactionReasons**: The current redaction reasons applied to the view hierarchy.
- **isSceneCaptured**: The current capture state.
- **RedactionReasons**: The reasons to apply a redaction to data displayed on screen.

