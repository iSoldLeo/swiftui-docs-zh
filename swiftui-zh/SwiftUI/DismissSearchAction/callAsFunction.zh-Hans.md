---
来源： https://developer.apple.com/documentation/SwiftUI/DismissSearchAction/callAsFunction()
抓取时间： 2025-12-03T06:05:34Z
---

# callAsFunction()

**实例方法**

解除当前搜索操作（如果有）。

## 声明

```swift
@MainActor @preconcurrency func callAsFunction()
```

## 讨论

不要直接调用此方法。当您调用从[Environment](../Environment.zh-Hans.md) 得到的[DismissSearchAction](../DismissSearchAction.zh-Hans.md) 结构时，SwiftUI 会为您调用该方法：

```swift
struct SearchedView: View {
    @Environment(\.dismissSearch) private var dismissSearch

    var body: some View {
        Button("Cancel") {
            dismissSearch() // Implicitly calls dismissSearch.callAsFunction()
        }
    }
}
```

有关 Swift 如何使用`callAsFunction()` 方法简化调用站点语法的信息，请参阅 *The Swift Programming Language* 中的 [https://docs.swift.org/swift-book/ReferenceManual/Declarations.html#ID622]。


---
source: https://developer.apple.com/documentation/SwiftUI/DismissSearchAction/callAsFunction()
crawled: 2025-12-03T06:05:34Z
---

# callAsFunction()

**Instance Method**

Dismisses the current search operation, if any.

## Declaration

```swift
@MainActor @preconcurrency func callAsFunction()
```

## Discussion

Don’t call this method directly. SwiftUI calls it for you when you call the [DismissSearchAction](../DismissSearchAction.zh-Hans.md) structure that you get from the [Environment](../Environment.zh-Hans.md):

```swift
struct SearchedView: View {
    @Environment(\.dismissSearch) private var dismissSearch

    var body: some View {
        Button("Cancel") {
            dismissSearch() // Implicitly calls dismissSearch.callAsFunction()
        }
    }
}
```

For information about how Swift uses the `callAsFunction()` method to simplify call site syntax, see [https://docs.swift.org/swift-book/ReferenceManual/Declarations.html#ID622] in *The Swift Programming Language*.

