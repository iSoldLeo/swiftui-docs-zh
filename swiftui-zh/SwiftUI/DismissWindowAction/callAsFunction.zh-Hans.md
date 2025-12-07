---
来源： https://developer.apple.com/documentation/SwiftUI/DismissWindowAction/callAsFunction()
抓取时间： 2025-12-03T05:31:58Z
---

# callAsFunction()

**实例方法**

解除当前窗口。

## 声明

```swift
@MainActor @preconcurrency func callAsFunction()
```

## 讨论

不要直接调用此方法。SwiftUI 会在您调用 [dismissWindow](../EnvironmentValues/dismissWindow.zh-Hans.md) 操作时调用它：

```swift
dismissWindow()
```

有关 Swift 如何使用`callAsFunction()` 方法简化调用站点语法的信息，请参阅 *The Swift Programming Language* 中的 [https://docs.swift.org/swift-book/documentation/the-swift-programming-language/declarations#Methods-with-Special-Names]。

## 调用操作

- **callAsFunction(id:)**：解除与指定标识符相关联的窗口。
- **callAsFunction(id:value:)**：关闭窗口组定义的窗口，该窗口显示指定的值类型，并与指定的标识符相关联。
- **callAsFunction(value:)**：解散窗口组定义的窗口，该窗口显示指定的值类型。


---
source: https://developer.apple.com/documentation/SwiftUI/DismissWindowAction/callAsFunction()
crawled: 2025-12-03T05:31:58Z
---

# callAsFunction()

**Instance Method**

Dismisses the current window.

## Declaration

```swift
@MainActor @preconcurrency func callAsFunction()
```

## Discussion

Don’t call this method directly. SwiftUI calls it when you call the [dismissWindow](../EnvironmentValues/dismissWindow.zh-Hans.md) action:

```swift
dismissWindow()
```

For information about how Swift uses the `callAsFunction()` method to simplify call site syntax, see [https://docs.swift.org/swift-book/documentation/the-swift-programming-language/declarations#Methods-with-Special-Names] in *The Swift Programming Language*.

## Calling the action

- **callAsFunction(id:)**: Dismisses the window that’s associated with the specified identifier.
- **callAsFunction(id:value:)**: Dismisses the window defined by the window group that is presenting the specified value type and that’s associated with the specified identifier.
- **callAsFunction(value:)**: Dismisses the window defined by the window group that is presenting the specified value type.

