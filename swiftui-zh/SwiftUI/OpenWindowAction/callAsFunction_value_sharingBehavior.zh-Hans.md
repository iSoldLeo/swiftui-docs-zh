---
来源：https://developer.apple.com/documentation/SwiftUI/OpenWindowAction/callAsFunction(value:sharingBehavior:)
抓取时间：2025-12-03T05:31:54Z
---

# callAsFunction(value:sharingBehavior:)

**实例方法**

使用指定的共享行为（sharingBehavior）打开由窗口组定义的窗口，该窗口显示指定值的类型。

## 声明

```swift
@MainActor func callAsFunction<D>(value: D, sharingBehavior: OpenWindowAction.SharingBehavior) async throws where D : Decodable, D : Encodable, D : Hashable
```

## 讨论

如果请求或要求共享行为（sharingBehavior），则如果存在可用的共享会话（sharingSession），且使用您应用程序的人确认了共享提议，则窗口将被共享。如果请求共享行为，且未共享窗口，则窗口会正常打开。如果要求共享行为，但窗口未共享，则窗口不会打开，并会出现错误。无论共享行为如何，如果窗口无法打开，都会抛出一个错误。

不要直接调用此方法。SwiftUI 会在您调用带有值的[openWindow](../EnvironmentValues/openWindow.zh-Hans.md) 操作时调用该方法：

```swift
try await openWindow(value: message.id,
sharingBehavior: .requested)
```

有关 Swift 如何使用`callAsFunction()` 方法简化调用站点语法的信息，请参阅 *The Swift Programming Language* 中的 [https://docs.swift.org/swift-book/ReferenceManual/Declarations.html#ID622]。

- 参数

- 值：要呈现的值。
- sharingBehavior：已打开窗口的共享行为。


---
source: https://developer.apple.com/documentation/SwiftUI/OpenWindowAction/callAsFunction(value:sharingBehavior:)
crawled: 2025-12-03T05:31:54Z
---

# callAsFunction(value:sharingBehavior:)

**Instance Method**

Opens a window defined by a window group that presents the type of the specified value, using the specified sharingBehavior.

## Declaration

```swift
@MainActor func callAsFunction<D>(value: D, sharingBehavior: OpenWindowAction.SharingBehavior) async throws where D : Decodable, D : Encodable, D : Hashable
```

## Discussion

If sharingBehavior is requested or required, the window is shared if there is an available sharingSession and the person using your app confirms the offer to share. If sharingBehavior is requested and the window is not shared, it is opened normally. If sharingBehavior is required and the window is not shared, it is not opened, and an error is thrown. Regardless of sharingBehavior, an error is thrown if the window fails to open.

Don’t call this method directly. SwiftUI calls it when you call the [openWindow](../EnvironmentValues/openWindow.zh-Hans.md) action with a value:

```swift
try await openWindow(value: message.id,
sharingBehavior: .requested)
```

For information about how Swift uses the `callAsFunction()` method to simplify call site syntax, see [https://docs.swift.org/swift-book/ReferenceManual/Declarations.html#ID622] in *The Swift Programming Language*.

- Parameters

- value: The value to present.
- sharingBehavior: the sharing behavior for the opened window.

