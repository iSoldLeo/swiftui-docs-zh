--- 来源：https://developer.apple.com/documentation/SwiftUI/View/onDropSessionUpdated(_:)

抓取时间：2025-11-30T21:10:02Z

---

# onDropSessionUpdated(_:)

**实例方法**

指定在由 `dropDestination(_:)` 或其他拖放修饰符激活的正在进行的拖放操作的每次更新时要执行的操作。

## 声明

```swift
nonisolated func onDropSessionUpdated(_ onUpdate: @escaping (DropSession) -> Void) -> some View

```

## 说明

当子视图层次结构中最近的拖放会话变为活动状态时，将调用 `onUpdate` 闭包。


---
source: https://developer.apple.com/documentation/SwiftUI/View/onDropSessionUpdated(_:)
crawled: 2025-11-30T21:10:02Z
---

# onDropSessionUpdated(_:)

**Instance Method**

Specifies an action to perform on each update of an ongoing drop operation activated by `dropDestination(_:)` or other drop modifiers.

## Declaration

```swift
nonisolated func onDropSessionUpdated(_ onUpdate: @escaping (DropSession) -> Void) -> some View

```

## Discussion

The `onUpdate` closure is called when the closest drop session in the child view hierarchy becomes active.

