--- 来源：https://developer.apple.com/documentation/SwiftUI/View/redacted(reason:)

抓取时间：2025-12-02T17:32:54Z

---

# redacted(reason:)

**实例方法**

为该视图层级添加应用编辑的原因。

## 声明

```swift
nonisolated func redacted(reason: RedactionReasons) -> some View

```

## 说明

添加编辑是一个累加过程：任何提供的编辑都会添加到父视图提供的原因中。

## 编辑私密内容

- **为“始终显示”状态设计您的应用**：自定义 watchOS 应用的用户界面，使其能够持续显示。

- **privacySensitive(_:)**：将视图标记为包含敏感的私密用户数据。

- **unredacted()**：移除为该视图层级应用编辑的任何原因。

- **redactionReasons**：当前应用于视图层级的编辑原因。

- **isSceneCaptured**：当前捕获状态。

- **RedactionReasons**：对屏幕上显示的数据进行编辑的原因。


---
source: https://developer.apple.com/documentation/SwiftUI/View/redacted(reason:)
crawled: 2025-12-02T17:32:54Z
---

# redacted(reason:)

**Instance Method**

Adds a reason to apply a redaction to this view hierarchy.

## Declaration

```swift
nonisolated func redacted(reason: RedactionReasons) -> some View

```

## Discussion

Adding a redaction is an additive process: any redaction provided will be added to the reasons provided by the parent.

## Redacting private content

- **Designing your app for the Always On state**: Customize your watchOS app’s user interface for continuous display.
- **privacySensitive(_:)**: Marks the view as containing sensitive, private user data.
- **unredacted()**: Removes any reason to apply a redaction to this view hierarchy.
- **redactionReasons**: The current redaction reasons applied to the view hierarchy.
- **isSceneCaptured**: The current capture state.
- **RedactionReasons**: The reasons to apply a redaction to data displayed on screen.

