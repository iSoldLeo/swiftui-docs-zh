--- 来源：https://developer.apple.com/documentation/SwiftUI/View/onReceive(_:perform:)

抓取时间：2025-11-30T21:17:18Z

---

# onReceive(_:perform:)

**实例方法**

当此视图检测到指定发布者发出的数据时，添加要执行的操作。

## 声明

```swift
nonisolated func onReceive<P>(_ publisher: P, perform action: @escaping (P.Output) -> Void) -> some View where P : Publisher, P.Failure == Never

```

## 参数

- **publisher**：要订阅的发布者。

- **action**：当 `publisher` 发出事件时要执行的操作。发布者发出的事件将作为参数传递给 `action`。

## 返回值

当 `publisher` 发出事件时，触发 `action` 的视图。

## 响应数据更改

- **onChange(of:initial:_:)**：为此视图添加一个修饰符，当特定值更改时触发操作。


---
source: https://developer.apple.com/documentation/SwiftUI/View/onReceive(_:perform:)
crawled: 2025-11-30T21:17:18Z
---

# onReceive(_:perform:)

**Instance Method**

Adds an action to perform when this view detects data emitted by the given publisher.

## Declaration

```swift
nonisolated func onReceive<P>(_ publisher: P, perform action: @escaping (P.Output) -> Void) -> some View where P : Publisher, P.Failure == Never

```

## Parameters

- **publisher**: The publisher to subscribe to.
- **action**: The action to perform when an event is emitted by `publisher`. The event emitted by publisher is passed as a parameter to `action`.

## Return Value

A view that triggers `action` when `publisher` emits an event.

## Responding to data changes

- **onChange(of:initial:_:)**: Adds a modifier for this view that fires an action when a specific value changes.

