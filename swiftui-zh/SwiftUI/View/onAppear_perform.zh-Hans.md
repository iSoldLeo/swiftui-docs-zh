--- 来源：https://developer.apple.com/documentation/SwiftUI/View/onAppear(perform:)

抓取时间：2025-12-02T16:02:37Z

---

# onAppear(perform:)

**实例方法**

添加一个在视图显示之前执行的操作。

## 声明

```swift
nonisolated func onAppear(perform action: (() -> Void)? = nil) -> some View

```

## 参数

- **action**：要执行的操作。如果 `action` 为 `nil`，则调用无效。

## 返回值

一个在显示之前触发 `action` 的视图。

## 讨论

SwiftUI 调用此方法的具体时机取决于您应用此方法的视图类型，但 `action` 闭包会在第一个渲染帧出现之前完成。

## 响应视图生命周期更新

- **onDisappear(perform:)**：添加一个在此视图消失后要执行的操作。

- **task(priority:_:)**：添加一个在此视图出现之前要执行的异步任务。

- **task(id:priority:_:)**：添加一个在此视图出现之前或指定值更改时要执行的任务。


---
source: https://developer.apple.com/documentation/SwiftUI/View/onAppear(perform:)
crawled: 2025-12-02T16:02:37Z
---

# onAppear(perform:)

**Instance Method**

Adds an action to perform before this view appears.

## Declaration

```swift
nonisolated func onAppear(perform action: (() -> Void)? = nil) -> some View

```

## Parameters

- **action**: The action to perform. If `action` is `nil`, the call has no effect.

## Return Value

A view that triggers `action` before it appears.

## Discussion

The exact moment that SwiftUI calls this method depends on the specific view type that you apply it to, but the `action` closure completes before the first rendered frame appears.

## Responding to view life cycle updates

- **onDisappear(perform:)**: Adds an action to perform after this view disappears.
- **task(priority:_:)**: Adds an asynchronous task to perform before this view appears.
- **task(id:priority:_:)**: Adds a task to perform before this view appears or when a specified value changes.

