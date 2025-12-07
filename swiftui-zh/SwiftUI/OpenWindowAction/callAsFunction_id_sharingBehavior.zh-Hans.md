---
来源：https://developer.apple.com/documentation/SwiftUI/OpenWindowAction/callAsFunction(id:sharingBehavior:)
抓取时间：2025-12-01T10:20:56Z
---

# callAsFunction(id:sharingBehavior:)

**实例方法**

使用指定的共享 sharingBehavior 打开与指定标识符相关联的窗口。

## 声明

```swift
@MainActor func callAsFunction(id: String, sharingBehavior: OpenWindowAction.SharingBehavior) async throws
```

## 参数

- **id**：要呈现的场景的标识符。
- **sharingBehavior**：打开窗口的共享行为。

## 讨论

如果 sharingBehavior（共享行为）为请求或要求，则在有可用的 sharingSession 且使用您应用程序的人确认共享提议的情况下，窗口将被共享。如果请求共享行为且未共享窗口，则窗口会正常打开。如果要求共享行为，但窗口未共享，则窗口不会打开，并会出现错误。无论共享行为如何，如果窗口无法打开，都会抛出一个错误。

不要直接调用此方法。SwiftUI 会在您使用标识符调用[openWindow](../EnvironmentValues/openWindow.zh-Hans.md) 操作时调用该方法：

```swift
try await openWindow(id: "message", sharingBehavior: .requested)
```

有关 Swift 如何使用`callAsFunction()` 方法简化调用站点语法的信息，请参阅 *The Swift Programming Language* 中的 [https://docs.swift.org/swift-book/ReferenceManual/Declarations.html#ID622]。


---
source: https://developer.apple.com/documentation/SwiftUI/OpenWindowAction/callAsFunction(id:sharingBehavior:)
crawled: 2025-12-01T10:20:56Z
---

# callAsFunction(id:sharingBehavior:)

**Instance Method**

Opens a window that’s associated with the specified identifier, using the specified sharing sharingBehavior..

## Declaration

```swift
@MainActor func callAsFunction(id: String, sharingBehavior: OpenWindowAction.SharingBehavior) async throws
```

## Parameters

- **id**: The identifier of the scene to present.
- **sharingBehavior**: The sharing behavior for the opened window.

## Discussion

If sharingBehavior is requested or required, the window is shared if there is an available sharingSession and the person using your app confirms the offer to share. If sharingBehavior is requested and the window is not shared, it is opened normally. If sharingBehavior is required and the window is not shared, it is not opened, and an error is thrown. Regardless of sharingBehavior, an error is thrown if the window fails to open.

Don’t call this method directly. SwiftUI calls it when you call the [openWindow](../EnvironmentValues/openWindow.zh-Hans.md) action with an identifier:

```swift
try await openWindow(id: "message", sharingBehavior: .requested)
```

For information about how Swift uses the `callAsFunction()` method to simplify call site syntax, see [https://docs.swift.org/swift-book/ReferenceManual/Declarations.html#ID622] in *The Swift Programming Language*.

