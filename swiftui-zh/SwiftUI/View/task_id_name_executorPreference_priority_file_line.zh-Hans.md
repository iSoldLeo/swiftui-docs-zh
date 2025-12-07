--- 来源：https://developer.apple.com/documentation/SwiftUI/View/task(id:name:executorPreference:priority:file:line:_:)

抓取时间：2025-11-30T21:11:10Z

---

# task(id:name:executorPreference:priority:file:line:_:)

**实例方法**

添加一个任务，在视图显示之前或指定值更改时执行。

## 声明

```swift
nonisolated func task<T>(id: T, name: String? = nil, executorPreference taskExecutor: any TaskExecutor, priority: TaskPriority = .userInitiated, file: String = #fileID, line: Int = #line, _ action: sending @escaping @isolated(any) () async -> Void) -> some View where T : Equatable

```

## 参数

- **id**：要观察更改的值。该值必须符合 [doc://com.apple.documentation/documentation/Swift/Equatable] 协议。

- **name**：任务的易读名称。如果此参数为 `nil`，则会生成一个名称。

- **priority**：创建异步任务时使用的任务优先级。默认优先级为 [doc://com.apple.documentation/documentation/Swift/TaskPriority/userInitiated]。

- **file**：默认任务名称中使用的文件名。SwiftUI 默认使用 .task 调用点。

- **line**：默认任务名称中使用的行号。SwiftUI 默认使用 .task 调用点。

- **action**：SwiftUI 在视图显示之前作为异步任务调用的闭包。如果视图消失且操作尚未完成，SwiftUI 可以自动取消该任务。如果 `id` 的值发生变化，SwiftUI 将取消并重新启动该任务。

## 返回值

此方法会在视图显示之前异步运行指定的操作，或者在 `id` 值更改时重新启动任务。

## 说明

此方法的行为与 [task(priority:_:)](task_priority.zh-Hans.md) 类似，但它还会在指定值更改时取消并重新创建任务。为了检测更改，修饰符会测试 `id` 参数的新值是否等于先前的值。为此，该值的类型必须符合 [doc://com.apple.documentation/documentation/Swift/Equatable] 协议。

例如，如果您定义了一个可比较的 `Server` 类型，该类型会在其状态改变时发布自定义通知（例如，从“*已注销*”到“*已登录*”），则可以使用任务修饰符来更新 [Text](../Text.zh-Hans.md) 视图的内容，以反映当前所选服务器的状态：

```swift
Text(status ?? "Signed Out")
    .task(id: server) {
        let sequence = NotificationCenter.default.notifications(
            named: .didUpdateStatus,
            object: server
        ).compactMap {
            $0.userInfo?["status"] as? String
        }
        for await value in sequence {
            status = value
        }
    }
```

此示例使用 [doc://com.apple.documentation/documentation/Foundation/NotificationCenter/notifications(named:object:)] 方法创建由 [doc://com.apple.documentation/documentation/Swift/AsyncSequence] 实例提供的异步通知序列。然后，该示例将通知序列映射到与每个通知中存储的值相对应的字符串序列。

此外，服务器定义了一个自定义的 `didUpdateStatus` 通知：

```swift
extension NSNotification.Name {
    static var didUpdateStatus: NSNotification.Name {
        NSNotification.Name("didUpdateStatus")
    }
}
```

每当服务器状态发生变化时（例如用户登录后），服务器都会发布此自定义类型的通知：

```swift
let notification = Notification(
    name: .didUpdateStatus,
    object: self,
    userInfo: ["status": "Signed In"])
NotificationCenter.default.post(notification)
```

附加到 [Text](../Text.zh-Hans.md) 视图的任务会从通知的用户信息字典中获取并显示状态值。当用户选择其他服务器时，SwiftUI 会取消当前任务并创建一个新任务，该任务随后会等待来自新服务器的通知。


---
source: https://developer.apple.com/documentation/SwiftUI/View/task(id:name:executorPreference:priority:file:line:_:)
crawled: 2025-11-30T21:11:10Z
---

# task(id:name:executorPreference:priority:file:line:_:)

**Instance Method**

Adds a task to perform before this view appears or when a specified value changes.

## Declaration

```swift
nonisolated func task<T>(id: T, name: String? = nil, executorPreference taskExecutor: any TaskExecutor, priority: TaskPriority = .userInitiated, file: String = #fileID, line: Int = #line, _ action: sending @escaping @isolated(any) () async -> Void) -> some View where T : Equatable

```

## Parameters

- **id**: The value to observe for changes. The value must conform to the [doc://com.apple.documentation/documentation/Swift/Equatable] protocol.
- **name**: Human readable name for the task. A name will be generated if this argument is `nil`.
- **priority**: The task priority to use when creating the asynchronous task. The default priority is [doc://com.apple.documentation/documentation/Swift/TaskPriority/userInitiated].
- **file**: File name used in default task name. SwiftUI uses the callsite of .task by default.
- **line**: Line number used in default task name. SwiftUI uses the callsite of .task by default.
- **action**: A closure that SwiftUI calls as an asynchronous task before the view appears. SwiftUI can automatically cancel the task after the view disappears before the action completes. If the `id` value changes, SwiftUI cancels and restarts the task.

## Return Value

A view that runs the specified action asynchronously before the view appears, or restarts the task when the `id` value changes.

## Discussion

This method behaves like [task(priority:_:)](task_priority.zh-Hans.md), except that it also cancels and recreates the task when a specified value changes. To detect a change, the modifier tests whether a new value for the `id` parameter equals the previous value. For this to work, the value’s type must conform to the [doc://com.apple.documentation/documentation/Swift/Equatable] protocol.

For example, if you define an equatable `Server` type that posts custom notifications whenever its state changes — for example, from *signed out* to *signed in* — you can use the task modifier to update the contents of a [Text](../Text.zh-Hans.md) view to reflect the state of the currently selected server:

```swift
Text(status ?? "Signed Out")
    .task(id: server) {
        let sequence = NotificationCenter.default.notifications(
            named: .didUpdateStatus,
            object: server
        ).compactMap {
            $0.userInfo?["status"] as? String
        }
        for await value in sequence {
            status = value
        }
    }
```

This example uses the [doc://com.apple.documentation/documentation/Foundation/NotificationCenter/notifications(named:object:)] method to create an asynchronous sequence of notifications, given by an [doc://com.apple.documentation/documentation/Swift/AsyncSequence] instance. The example then maps the notification sequence to a sequence of strings that correspond to values stored with each notification.

Elsewhere, the server defines a custom `didUpdateStatus` notification:

```swift
extension NSNotification.Name {
    static var didUpdateStatus: NSNotification.Name {
        NSNotification.Name("didUpdateStatus")
    }
}
```

Whenever the server status changes, like after the user signs in, the server posts a notification of this custom type:

```swift
let notification = Notification(
    name: .didUpdateStatus,
    object: self,
    userInfo: ["status": "Signed In"])
NotificationCenter.default.post(notification)
```

The task attached to the [Text](../Text.zh-Hans.md) view gets and displays the status value from the notification’s user information dictionary. When the user chooses a different server, SwiftUI cancels the task and creates a new one, which then waits for notifications from the new server.

