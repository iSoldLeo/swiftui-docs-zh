--- 来源：https://developer.apple.com/documentation/SwiftUI/RefreshAction/callAsFunction()

抓取时间：2025-12-03T06:40:09Z

---

# callAsFunction()

**实例方法**

启动刷新操作。

## 声明

```swift
func callAsFunction() async
```

## 讨论

请勿直接调用此方法。当您调用从 [Environment](../Environment.zh-Hans.md) 获取的 [RefreshAction](../RefreshAction.zh-Hans.md) 结构时，SwiftUI 会调用它：

```swift
struct RefreshableView: View {
    @Environment(\.refresh) private var refresh

    var body: some View {
        Button("Refresh") {
            Task {
                await refresh?()  // Implicitly calls refresh.callAsFunction()
            }
        }
        .disabled(refresh == nil)
    }
}
```

有关 Swift 如何使用 `callAsFunction()` 方法简化调用点语法的信息，请参阅《Swift 程序设计语言》中的 [https://docs.swift.org/swift-book/ReferenceManual/Declarations.html#ID622]。有关 Swift 中异步操作的信息，请参阅 [https://docs.swift.org/swift-book/LanguageGuide/Concurrency.html]。


---
source: https://developer.apple.com/documentation/SwiftUI/RefreshAction/callAsFunction()
crawled: 2025-12-03T06:40:09Z
---

# callAsFunction()

**Instance Method**

Initiates a refresh action.

## Declaration

```swift
func callAsFunction() async
```

## Discussion

Don’t call this method directly. SwiftUI calls it when you call the [RefreshAction](../RefreshAction.zh-Hans.md) structure that you get from the [Environment](../Environment.zh-Hans.md):

```swift
struct RefreshableView: View {
    @Environment(\.refresh) private var refresh

    var body: some View {
        Button("Refresh") {
            Task {
                await refresh?()  // Implicitly calls refresh.callAsFunction()
            }
        }
        .disabled(refresh == nil)
    }
}
```

For information about how Swift uses the `callAsFunction()` method to simplify call site syntax, see [https://docs.swift.org/swift-book/ReferenceManual/Declarations.html#ID622] in *The Swift Programming Language*. For information about asynchronous operations in Swift, see [https://docs.swift.org/swift-book/LanguageGuide/Concurrency.html].

