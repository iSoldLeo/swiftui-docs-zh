---
来源：https://developer.apple.com/documentation/SwiftUI/DismissWindowAction/callAsFunction(id:value:)
抓取时间： 2025-12-01T10:21:02Z
---

# callAsFunction(id:value:)

**实例方法**

撤消窗口组定义的窗口，该窗口显示指定的值类型，并与指定的标识符相关联。

## 声明

```swift
@MainActor @preconcurrency func callAsFunction<D>(id: String, value: D) where D : Decodable, D : Encodable, D : Hashable
```

## 参数

- **id**：要解散场景的标识符。
- **value**：当前显示的值。

## 讨论

不要直接调用此方法。当您使用标识符和值调用[dismissWindow](../EnvironmentValues/dismissWindow.zh-Hans.md) 操作时，SwiftUI 会调用该方法：

```swift
dismissWindow(id: "message", value: message.id)
```

有关 Swift 如何使用`callAsFunction()` 方法简化调用站点语法的信息，请参阅 *The Swift Programming Language* 中的 [https://docs.swift.org/swift-book/documentation/the-swift-programming-language/declarations#Methods-with-Special-Names]。

## 调用操作

- **callAsFunction()**：解除当前窗口。
- **callAsFunction(id:)**：解除与指定标识符关联的窗口。
- **callAsFunction(value:)**：关闭窗口组定义的窗口，该窗口显示指定的值类型。


---
source: https://developer.apple.com/documentation/SwiftUI/DismissWindowAction/callAsFunction(id:value:)
crawled: 2025-12-01T10:21:02Z
---

# callAsFunction(id:value:)

**Instance Method**

Dismisses the window defined by the window group that is presenting the specified value type and that’s associated with the specified identifier.

## Declaration

```swift
@MainActor @preconcurrency func callAsFunction<D>(id: String, value: D) where D : Decodable, D : Encodable, D : Hashable
```

## Parameters

- **id**: The identifier of the scene to dismiss.
- **value**: The value which is currently presented.

## Discussion

Don’t call this method directly. SwiftUI calls it when you call the [dismissWindow](../EnvironmentValues/dismissWindow.zh-Hans.md) action with an identifier and a value:

```swift
dismissWindow(id: "message", value: message.id)
```

For information about how Swift uses the `callAsFunction()` method to simplify call site syntax, see [https://docs.swift.org/swift-book/documentation/the-swift-programming-language/declarations#Methods-with-Special-Names] in *The Swift Programming Language*.

## Calling the action

- **callAsFunction()**: Dismisses the current window.
- **callAsFunction(id:)**: Dismisses the window that’s associated with the specified identifier.
- **callAsFunction(value:)**: Dismisses the window defined by the window group that is presenting the specified value type.

