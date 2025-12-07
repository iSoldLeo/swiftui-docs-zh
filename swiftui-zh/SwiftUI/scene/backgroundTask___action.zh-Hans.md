--- 来源：https://developer.apple.com/documentation/SwiftUI/Scene/backgroundTask(_:action:)

抓取时间：2025-12-02T17:43:28Z

---

# backgroundTask(_:action:)

**实例方法**

当系统提供后台任务时，运行指定的操作。

## 声明

```swift
nonisolated func backgroundTask<D, R>(_ task: BackgroundTask<D, R>, action: @escaping (D) async -> R) -> some Scene where D : Sendable, R : Sendable

```

## 参数

- **task**：要关联此操作的任务类型。

- **action**：系统为指定任务类型运行的异步闭包。

## 说明

当系统唤醒您的应用或扩展程序以执行一个或多个后台任务时，它将调用与匹配任务关联的所有操作。异步操作返回后，系统会将您的应用重新置于挂起状态。当系统收到您提供的 Action 闭包的返回值时，即认为任务已完成。如果任务超时未完成，则系统会取消该任务。您可以使用 `doc://com.apple.documentation/documentation/Swift/withTaskCancellationHandler(operation:onCancel:)` 来观察任务是否已接近完成。

```swift
/// An example of a Weather Application.
struct WeatherApp: App {
    var body: some Scene {
        WindowGroup {
            Text("Responds to App Refresh")
        }
        .backgroundTask(.appRefresh("WEATHER_DATA")) {
            await updateWeatherData()
        }
    }
    func updateWeatherData() async {
        // fetches new weather data and updates app state
    }
}
```

## 处理后台任务

- **BackgroundTask**：您的应用或扩展程序可以处理的后台任务类型。

- **SnapshotData**：快照后台任务的相关数据。

- **SnapshotResponse**：您的应用对快照后台任务的响应。


---
source: https://developer.apple.com/documentation/SwiftUI/Scene/backgroundTask(_:action:)
crawled: 2025-12-02T17:43:28Z
---

# backgroundTask(_:action:)

**Instance Method**

Runs the specified action when the system provides a background task.

## Declaration

```swift
nonisolated func backgroundTask<D, R>(_ task: BackgroundTask<D, R>, action: @escaping (D) async -> R) -> some Scene where D : Sendable, R : Sendable

```

## Parameters

- **task**: The type of task with which to associate the provided action.
- **action**: An async closure that the system runs for the specified task type.

## Discussion

When the system wakes your app or extension for one or more background tasks, it will call any actions associated with matching tasks. When your async actions return, the system put your app back into a suspended state. The system considers the task completed when the action closure that you provide returns. If the action closure has not returned when the task runs out of time to complete, the system cancels the task. Use doc://com.apple.documentation/documentation/Swift/withTaskCancellationHandler(operation:onCancel:) to observe whether the task is low on runtime.

```swift
/// An example of a Weather Application.
struct WeatherApp: App {
    var body: some Scene {
        WindowGroup {
            Text("Responds to App Refresh")
        }
        .backgroundTask(.appRefresh("WEATHER_DATA")) {
            await updateWeatherData()
        }
    }
    func updateWeatherData() async {
        // fetches new weather data and updates app state
    }
}
```

## Handling background tasks

- **BackgroundTask**: The kinds of background tasks that your app or extension can handle.
- **SnapshotData**: The associated data of a snapshot background task.
- **SnapshotResponse**: Your application’s response to a snapshot background task.

