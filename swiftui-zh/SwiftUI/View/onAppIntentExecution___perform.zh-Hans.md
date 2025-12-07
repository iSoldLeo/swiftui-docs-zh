--- 来源：https://developer.apple.com/documentation/SwiftUI/View/onAppIntentExecution(_:perform:)

抓取时间：2025-11-30T21:09:56Z

---

# onAppIntentExecution(_:perform:)

**实例方法**

注册一个处理程序，用于响应应用接收到的指定应用意图。

## 声明

```swift
nonisolated func onAppIntentExecution<I>(_ intent: I.Type = I.self, perform action: @escaping @MainActor (I) -> Void) -> some View where I : TargetContentProvidingIntent

```

## 参数

- **intent**：`action` 闭包处理的 App Intent 类型。

- **action**：SwiftUI 在执行指定应用意图时调用的闭包。该闭包以应用意图实例作为输入参数。

## 返回值

一个用于处理指定应用 Intent 的 perform 操作的视图

## 说明

使用此视图修饰符可以接收应用中特定场景的实例。SwiftUI 将传入的用户 Activity 路由到的场景取决于应用的结构、当前激活的场景以及其他配置。更多信息，请参阅 [handlesExternalEvents(matching:)](../scene/handlesExternalEvents_matching.zh-Hans.md)。

如果应用 Intent 实现了 perform() 方法，则会在操作闭包之后调用该方法。如果您的应用 Intent 支持通过 AppIntent.IntentModes API 在后台运行，这将非常有用。


---
source: https://developer.apple.com/documentation/SwiftUI/View/onAppIntentExecution(_:perform:)
crawled: 2025-11-30T21:09:56Z
---

# onAppIntentExecution(_:perform:)

**Instance Method**

Registers a handler to invoke in response to the specified app intent that your app receives.

## Declaration

```swift
nonisolated func onAppIntentExecution<I>(_ intent: I.Type = I.self, perform action: @escaping @MainActor (I) -> Void) -> some View where I : TargetContentProvidingIntent

```

## Parameters

- **intent**: The type of App Intent that the `action` closure handles.
- **action**: A closure that SwiftUI calls when the specified app intent is being performed. The closure takes the app intent instance as an input parameter.

## Return Value

A view that handles the specified app intent’s perform

## Discussion

Use this view modifier to receive instances in a particular scene within your app. The scene that SwiftUI routes the incoming user activity to depends on the structure of your app, what scenes are active, and other configuration. For more information, see [handlesExternalEvents(matching:)](../scene/handlesExternalEvents_matching.zh-Hans.md).

If the app intent implements a perform() method, it will be called after the action closure.  This can be useful if your app intent supports running in the background via the AppIntent.IntentModes API



