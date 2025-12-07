--- 来源：https://developer.apple.com/documentation/SwiftUI/View/onContinueUserActivity(_:perform:)

抓取时间：2025-11-30T21:28:23Z

---

# onContinueUserActivity(_:perform:)

**实例方法**

注册一个处理程序，用于响应应用接收到的用户活动。

## 声明

```swift
nonisolated func onContinueUserActivity(_ activityType: String, perform action: @escaping (NSUserActivity) -> ()) -> some View

```

## 参数

- **activityType**：`action` 闭包处理的 Activity 类型。请确保此字符串与应用信息属性列表中 [doc://com.apple.documentation/documentation/BundleResources/Information-Property-List/NSUserActivityTypes] 数组中列出的值之一匹配。

- **action**：SwiftUI 会在应用接收到指定类型的用户 Activity 时调用此闭包。该闭包以 Activity 作为输入参数。

## 返回值

一个处理传入用户 Activity 的视图。

## 说明

使用此视图修饰符可在应用的特定场景中接收 [doc://com.apple.documentation/documentation/Foundation/NSUserActivity] 实例。SwiftUI 将传入的用户 Activity 路由到的场景取决于应用的结构、当前激活的场景以及其他配置。更多信息，请参阅 [handlesExternalEvents(matching:)](../scene/handlesExternalEvents_matching.zh-Hans.md)。

传统的 UI 框架使用用户 Activity 将通用链接传递给应用。但是，SwiftUI 直接将通用链接作为 URL 传递给应用。要接收通用链接，请改用 [onOpenURL(perform:)](onOpenURL_perform.zh-Hans.md) 修饰符。

## 发送和接收用户活动

- **使用 SwiftUI 恢复应用状态**：通过保留用户当前活动，为用户提供应用连续性。

- **userActivity(_:element:_:)**：发布用户活动类型。

- **userActivity(_:isActive:_:)**：发布用户活动类型。


---
source: https://developer.apple.com/documentation/SwiftUI/View/onContinueUserActivity(_:perform:)
crawled: 2025-11-30T21:28:23Z
---

# onContinueUserActivity(_:perform:)

**Instance Method**

Registers a handler to invoke in response to a user activity that your app receives.

## Declaration

```swift
nonisolated func onContinueUserActivity(_ activityType: String, perform action: @escaping (NSUserActivity) -> ()) -> some View

```

## Parameters

- **activityType**: The type of activity that the `action` closure handles. Be sure that this string matches one of the values that you list in the [doc://com.apple.documentation/documentation/BundleResources/Information-Property-List/NSUserActivityTypes] array in your app’s Information Property List.
- **action**: A closure that SwiftUI calls when your app receives a user activity of the specified type. The closure takes the activity as an input parameter.

## Return Value

A view that handles incoming user activities.

## Discussion

Use this view modifier to receive [doc://com.apple.documentation/documentation/Foundation/NSUserActivity] instances in a particular scene within your app. The scene that SwiftUI routes the incoming user activity to depends on the structure of your app, what scenes are active, and other configuration. For more information, see [handlesExternalEvents(matching:)](../scene/handlesExternalEvents_matching.zh-Hans.md).

UI frameworks traditionally pass Universal Links to your app using a user activity. However, SwiftUI passes a Universal Link to your app directly as a URL. To receive a Universal Link, use the [onOpenURL(perform:)](onOpenURL_perform.zh-Hans.md) modifier instead.

## Sending and receiving user activities

- **Restoring your app’s state with SwiftUI**: Provide app continuity for users by preserving their current activities.
- **userActivity(_:element:_:)**: Advertises a user activity type.
- **userActivity(_:isActive:_:)**: Advertises a user activity type.

