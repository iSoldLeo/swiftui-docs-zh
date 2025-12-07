--- 来源：https://developer.apple.com/documentation/SwiftUI/DismissAction/callAsFunction()

抓取时间：2025-12-01T10:21:03Z

---

# callAsFunction()

**实例方法**

如果视图当前处于显示状态，则将其关闭。

## 声明

```swift
@MainActor @preconcurrency func callAsFunction()
```

## 讨论

请勿直接调用此方法。当您调用从 [Environment](../Environment.zh-Hans.md) 获取的 [DismissAction](../DismissAction.zh-Hans.md) 结构时，SwiftUI 会自动为您调用它：

```swift
private struct SheetContents: View {
    @Environment(\.dismiss) private var dismiss

    var body: some View {
        Button("Done") {
            dismiss() // Implicitly calls dismiss.callAsFunction()
        }
    }
}
```

有关 Swift 如何使用 `callAsFunction()` 方法简化调用点语法的详细信息，请参阅《Swift 程序设计语言》中的 [https://docs.swift.org/swift-book/ReferenceManual/Declarations.html#ID622]。


---
source: https://developer.apple.com/documentation/SwiftUI/DismissAction/callAsFunction()
crawled: 2025-12-01T10:21:03Z
---

# callAsFunction()

**Instance Method**

Dismisses the view if it is currently presented.

## Declaration

```swift
@MainActor @preconcurrency func callAsFunction()
```

## Discussion

Don’t call this method directly. SwiftUI calls it for you when you call the [DismissAction](../DismissAction.zh-Hans.md) structure that you get from the [Environment](../Environment.zh-Hans.md):

```swift
private struct SheetContents: View {
    @Environment(\.dismiss) private var dismiss

    var body: some View {
        Button("Done") {
            dismiss() // Implicitly calls dismiss.callAsFunction()
        }
    }
}
```

For information about how Swift uses the `callAsFunction()` method to simplify call site syntax, see [https://docs.swift.org/swift-book/ReferenceManual/Declarations.html#ID622] in *The Swift Programming Language*.

