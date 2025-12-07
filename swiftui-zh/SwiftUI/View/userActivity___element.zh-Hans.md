--- 来源：https://developer.apple.com/documentation/SwiftUI/View/userActivity(_:element:_:)

抓取时间：2025-11-30T21:28:22Z

---

# userActivity(_:element:_:)

**实例方法**

发布用户活动类型。

## 声明

```swift
nonisolated func userActivity<P>(_ activityType: String, element: P?, _ update: @escaping (P, NSUserActivity) -> ()) -> some View

```

## 参数

- **activityType**：要发布的活动类型。

- **element**：如果元素为 `nil`，则不会将处理程序与该活动关联（如果没有处理程序，则不会发布任何活动）。该方法将非 `nil` 元素传递给处理程序，以便所有处理程序无需都使用 `guard element = element else { return }` 实现提前退出。

- **update**：一个用于修改传入的 Activity 以进行广播的函数。

## 讨论

Activity 的作用域仅适用于视图所在的场景或窗口。

## 发送和接收用户 Activity

- **使用 SwiftUI 恢复应用状态**：通过保留用户当前的 Activity 来确保应用的连续性。

- **userActivity(_:isActive:_:)**：广播用户 Activity 类型。

- **onContinueUserActivity(_:perform:)**：注册一个处理程序，以便在应用接收到用户 Activity 时调用。


---
source: https://developer.apple.com/documentation/SwiftUI/View/userActivity(_:element:_:)
crawled: 2025-11-30T21:28:22Z
---

# userActivity(_:element:_:)

**Instance Method**

Advertises a user activity type.

## Declaration

```swift
nonisolated func userActivity<P>(_ activityType: String, element: P?, _ update: @escaping (P, NSUserActivity) -> ()) -> some View

```

## Parameters

- **activityType**: The type of activity to advertise.
- **element**: If the element is `nil`, the handler will not be associated with the activity (and if there are no handlers, no activity is advertised). The method passes the non-`nil` element to the handler as a convenience so the handlers don’t all need to implement an early exit with `guard element = element else { return }`.
- **update**: A function that modifies the passed-in activity for advertisement.

## Discussion

The scope of the activity applies only to the scene or window the view is in.

## Sending and receiving user activities

- **Restoring your app’s state with SwiftUI**: Provide app continuity for users by preserving their current activities.
- **userActivity(_:isActive:_:)**: Advertises a user activity type.
- **onContinueUserActivity(_:perform:)**: Registers a handler to invoke in response to a user activity that your app receives.

