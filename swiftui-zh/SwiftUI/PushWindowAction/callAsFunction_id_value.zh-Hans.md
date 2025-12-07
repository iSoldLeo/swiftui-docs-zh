--- 来源：https://developer.apple.com/documentation/SwiftUI/PushWindowAction/callAsFunction(id:value:)

抓取时间：2025-12-03T05:31:56Z

---

# callAsFunction(id:value:)

**实例方法**

推送一个由窗口组定义的窗口，该窗口呈现指定类型的值，并与指定的标识符关联。

## 声明

```swift
@MainActor func callAsFunction<D>(id: String, value: D) where D : Decodable, D : Encodable, D : Hashable
```

## 参数

- **id**：要呈现的场景的标识符。

- **value**：要呈现的值。

## 说明

请勿直接调用此方法。当您使用标识符和值调用 [pushWindow](../EnvironmentValues/pushWindow.zh-Hans.md) 操作时，SwiftUI 会调用它：

```swift
pushWindow(id: "viewer", value: video.id)
```

有关 Swift 如何使用 `callAsFunction()` 方法简化调用点语法的详细信息，请参阅《Swift 程序设计语言》中的 [https://docs.swift.org/swift-book/ReferenceManual/Declarations.html#ID622]。


---
source: https://developer.apple.com/documentation/SwiftUI/PushWindowAction/callAsFunction(id:value:)
crawled: 2025-12-03T05:31:56Z
---

# callAsFunction(id:value:)

**Instance Method**

Pushes a window defined by the window group that presents the specified value type and that is associated with the specified identifier.

## Declaration

```swift
@MainActor func callAsFunction<D>(id: String, value: D) where D : Decodable, D : Encodable, D : Hashable
```

## Parameters

- **id**: The identifier of the scene to present.
- **value**: The value to present.

## Discussion

Don’t call this method directly. SwiftUI calls it when you call the [pushWindow](../EnvironmentValues/pushWindow.zh-Hans.md) action with an identifier and a value:

```swift
pushWindow(id: "viewer", value: video.id)
```

For information about how Swift uses the `callAsFunction()` method to simplify call site syntax, see [https://docs.swift.org/swift-book/ReferenceManual/Declarations.html#ID622] in *The Swift Programming Language*.

