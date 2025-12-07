---
来源：https://developer.apple.com/documentation/SwiftUI/OpenWindowAction/callAsFunction(value:)
抓取时间： 2025-12-01T10:20:50Z
---

# callAsFunction(value:)

**实例方法**

打开一个由窗口组定义的窗口，该窗口显示指定值的类型。

## 声明

```swift
@MainActor @preconcurrency func callAsFunction<D>(value: D) where D : Decodable, D : Encodable, D : Hashable
```

## 参数

- **value**：要显示的值。

## 讨论

不要直接调用此方法。SwiftUI 会在您调用带有值的[openWindow](../EnvironmentValues/openWindow.zh-Hans.md) 操作时调用该方法：

```swift
openWindow(value: message.id)
```

有关 Swift 如何使用`callAsFunction()` 方法简化调用站点语法的信息，请参阅 *The Swift Programming Language* 中的 [https://docs.swift.org/swift-book/ReferenceManual/Declarations.html#ID622]。

## 调用操作

- **callAsFunction(id:)**：打开与指定标识符相关联的窗口。
- **callAsFunction(id:value:)**：打开窗口组定义的窗口，该窗口显示指定的值类型，并与指定的标识符相关联。


---
source: https://developer.apple.com/documentation/SwiftUI/OpenWindowAction/callAsFunction(value:)
crawled: 2025-12-01T10:20:50Z
---

# callAsFunction(value:)

**Instance Method**

Opens a window defined by a window group that presents the type of the specified value.

## Declaration

```swift
@MainActor @preconcurrency func callAsFunction<D>(value: D) where D : Decodable, D : Encodable, D : Hashable
```

## Parameters

- **value**: The value to present.

## Discussion

Don’t call this method directly. SwiftUI calls it when you call the [openWindow](../EnvironmentValues/openWindow.zh-Hans.md) action with a value:

```swift
openWindow(value: message.id)
```

For information about how Swift uses the `callAsFunction()` method to simplify call site syntax, see [https://docs.swift.org/swift-book/ReferenceManual/Declarations.html#ID622] in *The Swift Programming Language*.

## Calling the action

- **callAsFunction(id:)**: Opens a window that’s associated with the specified identifier.
- **callAsFunction(id:value:)**: Opens a window defined by the window group that presents the specified value type and that’s associated with the specified identifier.

