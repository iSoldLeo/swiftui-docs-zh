--- 来源：https://developer.apple.com/documentation/swiftui/compositorcontent/ondisappear(perform:)

抓取时间：2025-12-03T06:32:38Z

---

# onDisappear(perform:)

**实例方法**

添加一个在内容消失后执行的操作。

## 声明

```swift
nonisolated func onDisappear(perform action: (() -> Void)? = nil) -> some CompositorContent

```

## 参数

- **action**：要执行的操作。如果 `action` 为 `nil`，则调用无效。

## 返回值

一个 CompositorContent，在内容消失后触发 `action`。

## 讨论

SwiftUI 调用此方法的具体时机取决于您应用此方法的具体内容类型，但 `action` 闭包只有在内容从界面消失后才会执行。


---
source: https://developer.apple.com/documentation/swiftui/compositorcontent/ondisappear(perform:)
crawled: 2025-12-03T06:32:38Z
---

# onDisappear(perform:)

**Instance Method**

Adds an action to perform after this content disappears.

## Declaration

```swift
nonisolated func onDisappear(perform action: (() -> Void)? = nil) -> some CompositorContent

```

## Parameters

- **action**: The action to perform. If `action` is `nil`, the call has no effect.

## Return Value

A CompositorContent that triggers `action` after it disappears.

## Discussion

The exact moment that SwiftUI calls this method depends on the specific content type that you apply it to, but the `action` closure doesn’t execute until the content disappears from the interface.

