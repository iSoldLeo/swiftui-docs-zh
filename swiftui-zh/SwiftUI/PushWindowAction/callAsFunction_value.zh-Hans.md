--- 来源：https://developer.apple.com/documentation/SwiftUI/PushWindowAction/callAsFunction(value:)

抓取时间：2025-12-03T05:31:57Z

---

# callAsFunction(value:)

**实例方法**

推送一个由窗口组定义的窗口，该窗口显示指定值的类型。

## 声明

```swift
@MainActor func callAsFunction<D>(value: D) where D : Decodable, D : Encodable, D : Hashable
```

## 参数

- **value**：要显示的值。

## 说明

请勿直接调用此方法。当您使用以下值调用 [pushWindow](../EnvironmentValues/pushWindow.zh-Hans.md) 操作时，SwiftUI 会调用它：

```swift
pushWindow(value: video.id)
```

有关 Swift 如何使用 `callAsFunction()` 方法简化调用点语法的详细信息，请参阅《Swift 程序设计语言》中的 [https://docs.swift.org/swift-book/ReferenceManual/Declarations.html#ID622]。


---
source: https://developer.apple.com/documentation/SwiftUI/PushWindowAction/callAsFunction(value:)
crawled: 2025-12-03T05:31:57Z
---

# callAsFunction(value:)

**Instance Method**

Pushes a window defined by a window group that presents the type of the specified value.

## Declaration

```swift
@MainActor func callAsFunction<D>(value: D) where D : Decodable, D : Encodable, D : Hashable
```

## Parameters

- **value**: The value to present.

## Discussion

Don’t call this method directly. SwiftUI calls it when you call the [pushWindow](../EnvironmentValues/pushWindow.zh-Hans.md) action with a value:

```swift
pushWindow(value: video.id)
```

For information about how Swift uses the `callAsFunction()` method to simplify call site syntax, see [https://docs.swift.org/swift-book/ReferenceManual/Declarations.html#ID622] in *The Swift Programming Language*.

