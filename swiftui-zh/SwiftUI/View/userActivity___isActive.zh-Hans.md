--- 来源：https://developer.apple.com/documentation/SwiftUI/View/userActivity(_:isActive:_:)

抓取时间：2025-11-30T21:28:22Z

---

# userActivity(_:isActive:_:)

**实例方法**

用于发布用户活动类型。

## 声明

```swift
nonisolated func userActivity(_ activityType: String, isActive: Bool = true, _ update: @escaping (NSUserActivity) -> ()) -> some View

```

## 参数

- **activityType**：要发布的活动类型。

- **isActive**：当 `false` 为真时，不发布该活动。默认为 `true`。

- **update**：用于修改传入的活动以进行发布的函数。

## 讨论

您可以使用 `userActivity(_:isActive:_:)` 来启动、停止或修改特定类型用户活动的广播。

活动的作用域仅限于视图所在的场景或窗口。

## 发送和接收用户活动

- **使用 SwiftUI 恢复应用状态**：通过保留用户当前的活动，为用户提供应用的连续性。

- **userActivity(_:element:_:)**：广播用户活动类型。

- **onContinueUserActivity(_:perform:)**：注册一个处理程序，以便在应用接收到用户活动时调用。


---
source: https://developer.apple.com/documentation/SwiftUI/View/userActivity(_:isActive:_:)
crawled: 2025-11-30T21:28:22Z
---

# userActivity(_:isActive:_:)

**Instance Method**

Advertises a user activity type.

## Declaration

```swift
nonisolated func userActivity(_ activityType: String, isActive: Bool = true, _ update: @escaping (NSUserActivity) -> ()) -> some View

```

## Parameters

- **activityType**: The type of activity to advertise.
- **isActive**: When `false`, avoids advertising the activity. Defaults to `true`.
- **update**: A function that modifies the passed-in activity for advertisement.

## Discussion

You can use `userActivity(_:isActive:_:)` to start, stop, or modify the advertisement of a specific type of user activity.

The scope of the activity applies only to the scene or window the view is in.

## Sending and receiving user activities

- **Restoring your app’s state with SwiftUI**: Provide app continuity for users by preserving their current activities.
- **userActivity(_:element:_:)**: Advertises a user activity type.
- **onContinueUserActivity(_:perform:)**: Registers a handler to invoke in response to a user activity that your app receives.

