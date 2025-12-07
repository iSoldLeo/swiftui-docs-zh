---
来源： https://developer.apple.com/documentation/SwiftUI/DismissWindowAction/callAsFunction(id:)
抓取时间： 2025-12-01T10:21:01Z
---

# callAsFunction(id:)

**实例方法**

解除与指定标识符相关联的窗口。

## 声明

```swift
@MainActor @preconcurrency func callAsFunction(id: String)
```

## 参数

- **id**：要解散场景的标识符。

## 讨论

当指定的标识符代表一个[WindowGroup](../WindowGroup.zh-Hans.md) 时，该组中所有打开的窗口都将被解散。要取消与`WindowGroup` 场景相关的单个窗口，请使用 `dismissWindow(value:)` 或 `dismissWindow(id:value:)`。

不要直接调用此方法。SwiftUI 会在您使用标识符调用 [dismissWindow](../EnvironmentValues/dismissWindow.zh-Hans.md) 操作时调用该方法：

```swift
dismissWindow(id: "message")
```

有关 Swift 如何使用`callAsFunction()` 方法简化调用站点语法的信息，请参阅 *The Swift Programming Language* 中的 [https://docs.swift.org/swift-book/documentation/the-swift-programming-language/declarations#Methods-with-Special-Names]。

## 调用操作

- **callAsFunction()**：解除当前窗口。
- **callAsFunction(id:value:)**：关闭窗口组定义的窗口，该窗口显示指定的值类型，并与指定的标识符相关联。
- **callAsFunction(value:)**：解散窗口组定义的窗口，该窗口显示指定的值类型。


---
source: https://developer.apple.com/documentation/SwiftUI/DismissWindowAction/callAsFunction(id:)
crawled: 2025-12-01T10:21:01Z
---

# callAsFunction(id:)

**Instance Method**

Dismisses the window that’s associated with the specified identifier.

## Declaration

```swift
@MainActor @preconcurrency func callAsFunction(id: String)
```

## Parameters

- **id**: The identifier of the scene to dismiss.

## Discussion

When the specified identifier represents a [WindowGroup](../WindowGroup.zh-Hans.md), all of the open windows in that group will be dismissed. For dismissing a single window associated to a `WindowGroup` scene, use `dismissWindow(value:)` or `dismissWindow(id:value:)`.

Don’t call this method directly. SwiftUI calls it when you call the [dismissWindow](../EnvironmentValues/dismissWindow.zh-Hans.md) action with an identifier:

```swift
dismissWindow(id: "message")
```

For information about how Swift uses the `callAsFunction()` method to simplify call site syntax, see [https://docs.swift.org/swift-book/documentation/the-swift-programming-language/declarations#Methods-with-Special-Names] in *The Swift Programming Language*.

## Calling the action

- **callAsFunction()**: Dismisses the current window.
- **callAsFunction(id:value:)**: Dismisses the window defined by the window group that is presenting the specified value type and that’s associated with the specified identifier.
- **callAsFunction(value:)**: Dismisses the window defined by the window group that is presenting the specified value type.

