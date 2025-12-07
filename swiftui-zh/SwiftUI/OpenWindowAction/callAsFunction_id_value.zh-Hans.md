---
来源：https://developer.apple.com/documentation/SwiftUI/OpenWindowAction/callAsFunction(id:value:)
抓取时间： 2025-12-03T05:31:45Z
---

# callAsFunction(id:value:)

**实例方法**

打开窗口组定义的窗口，该窗口显示指定的值类型，并与指定的标识符相关联。

## 声明

```swift
@MainActor @preconcurrency func callAsFunction<D>(id: String, value: D) where D : Decodable, D : Encodable, D : Hashable
```

## 参数

- **id**：要呈现的场景的标识符。
- **value**：要显示的值。

## 讨论

不要直接调用此方法。当您使用标识符和值调用[openWindow](../EnvironmentValues/openWindow.zh-Hans.md) 操作时，SwiftUI 会调用该方法：

```swift
openWindow(id: "message", value: message.id)
```

有关 Swift 如何使用`callAsFunction()` 方法简化调用站点语法的信息，请参阅 *The Swift Programming Language* 中的 [https://docs.swift.org/swift-book/ReferenceManual/Declarations.html#ID622]。

## 调用操作

- **callAsFunction(id:)**：打开与指定标识符相关联的窗口。
- **callAsFunction(value:)**：打开由窗口组定义的窗口，该窗口显示指定值的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/OpenWindowAction/callAsFunction(id:value:)
crawled: 2025-12-03T05:31:45Z
---

# callAsFunction(id:value:)

**Instance Method**

Opens a window defined by the window group that presents the specified value type and that’s associated with the specified identifier.

## Declaration

```swift
@MainActor @preconcurrency func callAsFunction<D>(id: String, value: D) where D : Decodable, D : Encodable, D : Hashable
```

## Parameters

- **id**: The identifier of the scene to present.
- **value**: The value to present.

## Discussion

Don’t call this method directly. SwiftUI calls it when you call the [openWindow](../EnvironmentValues/openWindow.zh-Hans.md) action with an identifier and a value:

```swift
openWindow(id: "message", value: message.id)
```

For information about how Swift uses the `callAsFunction()` method to simplify call site syntax, see [https://docs.swift.org/swift-book/ReferenceManual/Declarations.html#ID622] in *The Swift Programming Language*.

## Calling the action

- **callAsFunction(id:)**: Opens a window that’s associated with the specified identifier.
- **callAsFunction(value:)**: Opens a window defined by a window group that presents the type of the specified value.

