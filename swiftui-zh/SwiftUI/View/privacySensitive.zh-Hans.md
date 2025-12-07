--- 来源：https://developer.apple.com/documentation/SwiftUI/View/privacySensitive(_:)

抓取时间：2025-11-30T21:18:01Z

---

# privacySensitive(_:)

**实例方法**

将视图标记为包含敏感的、私密的用户数据。

## 声明

```swift
nonisolated func privacySensitive(_ sensitive: Bool = true) -> some View

```

## 讨论

当您应用 [privacy](../RedactionReasons/privacy.zh-Hans.md) 编辑原因时，SwiftUI 会编辑使用此修饰符标记的视图。

```swift
struct BankAccountView: View {
    var body: some View {
        VStack {
            Text("Account #")

            Text(accountNumber)
                .font(.headline)
                .privacySensitive() // Hide only the account number.
        }
    }
}
```

## 编辑私密内容

- **为“始终显示”状态设计您的应用**：自定义 watchOS 应用的用户界面，使其能够持续显示。

- **redacted(reason:)**：添加一个原因，以便对此视图层级应用编辑。

- **unredacted()**：移除对该视图层级应用任何编辑的原因。

- **redactionReasons**：当前应用于视图层级的编辑原因。

- **isSceneCaptured**：当前捕获状态。

- **RedactionReasons**：对屏幕上显示的数据应用编辑的原因。


---
source: https://developer.apple.com/documentation/SwiftUI/View/privacySensitive(_:)
crawled: 2025-11-30T21:18:01Z
---

# privacySensitive(_:)

**Instance Method**

Marks the view as containing sensitive, private user data.

## Declaration

```swift
nonisolated func privacySensitive(_ sensitive: Bool = true) -> some View

```

## Discussion

SwiftUI redacts views marked with this modifier when you apply the [privacy](../RedactionReasons/privacy.zh-Hans.md) redaction reason.

```swift
struct BankAccountView: View {
    var body: some View {
        VStack {
            Text("Account #")

            Text(accountNumber)
                .font(.headline)
                .privacySensitive() // Hide only the account number.
        }
    }
}
```

## Redacting private content

- **Designing your app for the Always On state**: Customize your watchOS app’s user interface for continuous display.
- **redacted(reason:)**: Adds a reason to apply a redaction to this view hierarchy.
- **unredacted()**: Removes any reason to apply a redaction to this view hierarchy.
- **redactionReasons**: The current redaction reasons applied to the view hierarchy.
- **isSceneCaptured**: The current capture state.
- **RedactionReasons**: The reasons to apply a redaction to data displayed on screen.

