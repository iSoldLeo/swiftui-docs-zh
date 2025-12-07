--- 来源：https://developer.apple.com/documentation/SwiftUI/View/task(priority:_:)

抓取时间：2025-11-30T19:48:38Z

---

# task(priority:_:)

**实例方法**

添加一个异步任务，在视图显示之前执行。

## 声明

```swift
nonisolated func task(priority: TaskPriority = .userInitiated, _ action: @escaping () async -> Void) -> some View

```

## 参数

- **priority**：创建异步任务时使用的任务优先级。默认优先级为 [doc://com.apple.documentation/documentation/Swift/TaskPriority/userInitiated]。

- **action**：SwiftUI 在视图显示之前作为异步任务调用的闭包。SwiftUI 会在视图消失后、操作完成之前自动取消该任务。

## 返回值

一个在视图显示之前异步运行指定操作的视图。

## 讨论

使用此修饰符可以执行一个生命周期与被修改视图生命周期相同的异步任务。如果任务在 SwiftUI 移除视图或视图更改标识之前未完成，SwiftUI 将取消该任务。

在任务中使用 `await` 关键字可以等待异步调用完成，或者等待 [doc://com.apple.documentation/documentation/Swift/AsyncSequence] 实例的值。例如，您可以修改 [Text](../Text.zh-Hans.md) 视图以启动一个从远程资源加载内容的任务：

```swift
let url = URL(string: "https://example.com")!
@State private var message = "Loading..."

var body: some View {
    Text(message)
        .task {
            do {
                var receivedLines = [String]()
                for try await line in url.lines {
                    receivedLines.append(line)
                    message = "Received \(receivedLines.count) lines"
                }
            } catch {
                message = "Failed to load"
            }
        }
}
```

此示例使用 [doc://com.apple.documentation/documentation/Foundation/URL/lines] 方法将存储在指定 [doc://com.apple.documentation/documentation/Foundation/URL] 中的内容作为异步字符串序列获取。当每到达一行新文本时，`for`-`await`-`in` 循环体会将该行文本存储在一个字符串数组中，并更新文本视图的内容以报告最新的行数。

## 响应视图生命周期更新

- **onAppear(perform:)**：添加一个在此视图显示之前要执行的操作。

- **onDisappear(perform:)**：添加一个在此视图消失之后要执行的操作。

- **task(id:priority:_:)**：添加一个在此视图显示之前或指定值更改时要执行的任务。


---
source: https://developer.apple.com/documentation/SwiftUI/View/task(priority:_:)
crawled: 2025-11-30T19:48:38Z
---

# task(priority:_:)

**Instance Method**

Adds an asynchronous task to perform before this view appears.

## Declaration

```swift
nonisolated func task(priority: TaskPriority = .userInitiated, _ action: @escaping () async -> Void) -> some View

```

## Parameters

- **priority**: The task priority to use when creating the asynchronous task. The default priority is [doc://com.apple.documentation/documentation/Swift/TaskPriority/userInitiated].
- **action**: A closure that SwiftUI calls as an asynchronous task before the view appears. SwiftUI will automatically cancel the task at some point after the view disappears before the action completes.

## Return Value

A view that runs the specified action asynchronously before the view appears.

## Discussion

Use this modifier to perform an asynchronous task with a lifetime that matches that of the modified view. If the task doesn’t finish before SwiftUI removes the view or the view changes identity, SwiftUI cancels the task.

Use the `await` keyword inside the task to wait for an asynchronous call to complete, or to wait on the values of an [doc://com.apple.documentation/documentation/Swift/AsyncSequence] instance. For example, you can modify a [Text](../Text.zh-Hans.md) view to start a task that loads content from a remote resource:

```swift
let url = URL(string: "https://example.com")!
@State private var message = "Loading..."

var body: some View {
    Text(message)
        .task {
            do {
                var receivedLines = [String]()
                for try await line in url.lines {
                    receivedLines.append(line)
                    message = "Received \(receivedLines.count) lines"
                }
            } catch {
                message = "Failed to load"
            }
        }
}
```

This example uses the [doc://com.apple.documentation/documentation/Foundation/URL/lines] method to get the content stored at the specified [doc://com.apple.documentation/documentation/Foundation/URL] as an asynchronous sequence of strings. When each new line arrives, the body of the `for`-`await`-`in` loop stores the line in an array of strings and updates the content of the text view to report the latest line count.

## Responding to view life cycle updates

- **onAppear(perform:)**: Adds an action to perform before this view appears.
- **onDisappear(perform:)**: Adds an action to perform after this view disappears.
- **task(id:priority:_:)**: Adds a task to perform before this view appears or when a specified value changes.

