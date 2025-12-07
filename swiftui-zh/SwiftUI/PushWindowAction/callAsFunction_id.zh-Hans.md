--- 来源：https://developer.apple.com/documentation/SwiftUI/PushWindowAction/callAsFunction(id:)

抓取时间：2025-12-01T10:20:58Z

---

# callAsFunction(id:)

**实例方法**

推送一个与指定标识符关联的窗口。

## 声明

```swift
@MainActor func callAsFunction(id: String)
```

## 参数

- **id**：要呈现的场景的标识符。

## 说明

请勿直接调用此方法。当您使用标识符调用 [pushWindow](../EnvironmentValues/pushWindow.zh-Hans.md) 操作时，SwiftUI 会调用它：

```swift
pushWindow(id: "viewer")
```

有关 Swift 如何使用 `callAsFunction()` 方法简化调用点语法的详细信息，请参阅《Swift 程序设计语言》中的 [https://docs.swift.org/swift-book/ReferenceManual/Declarations.html#ID622]。


---
source: https://developer.apple.com/documentation/SwiftUI/PushWindowAction/callAsFunction(id:)
crawled: 2025-12-01T10:20:58Z
---

# callAsFunction(id:)

**Instance Method**

Pushes a window that is associated with the specified identifier.

## Declaration

```swift
@MainActor func callAsFunction(id: String)
```

## Parameters

- **id**: The identifier of the scene to present.

## Discussion

Don’t call this method directly. SwiftUI calls it when you call the [pushWindow](../EnvironmentValues/pushWindow.zh-Hans.md) action with an identifier:

```swift
pushWindow(id: "viewer")
```

For information about how Swift uses the `callAsFunction()` method to simplify call site syntax, see [https://docs.swift.org/swift-book/ReferenceManual/Declarations.html#ID622] in *The Swift Programming Language*.

