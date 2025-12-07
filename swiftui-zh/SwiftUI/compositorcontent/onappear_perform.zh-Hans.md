--- 来源：https://developer.apple.com/documentation/swiftui/compositorcontent/onappear(perform:)

抓取时间：2025-12-03T06:32:31Z

---

# onAppear(perform:)

**实例方法**

添加一个在内容显示之前执行的操作。

## 声明

```swift
nonisolated func onAppear(perform action: (() -> Void)? = nil) -> some CompositorContent

```

## 参数

- **action**：要执行的操作。如果 `action` 为 `nil`，则调用无效。

## 返回值

一个 CompositorContent，它会在显示之前触发 `action`。

## 讨论

SwiftUI 调用此方法的具体时机取决于您应用此方法的具体内容类型，但 `action` 闭包会在第一帧渲染出现之前完成。


---
source: https://developer.apple.com/documentation/swiftui/compositorcontent/onappear(perform:)
crawled: 2025-12-03T06:32:31Z
---

# onAppear(perform:)

**Instance Method**

Adds an action to perform before this content appears.

## Declaration

```swift
nonisolated func onAppear(perform action: (() -> Void)? = nil) -> some CompositorContent

```

## Parameters

- **action**: The action to perform. If `action` is `nil`, the call has no effect.

## Return Value

A CompositorContent that triggers `action` before it appears.

## Discussion

The exact moment that SwiftUI calls this method depends on the specific content type that you apply it to, but the `action` closure completes before the first rendered frame appears.

