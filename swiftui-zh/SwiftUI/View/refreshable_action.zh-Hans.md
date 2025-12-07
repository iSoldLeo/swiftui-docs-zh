--- 来源：https://developer.apple.com/documentation/SwiftUI/View/refreshable(action:)

抓取时间：2025-11-30T21:24:53Z

---

# refreshable(action:)

**实例方法**

将此视图标记为可刷新。

## 声明

```swift
nonisolated func refreshable(action: @escaping () async -> Void) -> some View

```

## 参数

- **action**：SwiftUI 在用户请求刷新时执行的异步处理程序。使用此处理程序可以启动对已修改视图中显示的模型数据的更新。在处理程序内部的任何异步调用前使用 `await`。

## 返回值

一个在其环境中添加了新的刷新操作的视图。

## 讨论

将此修饰符应用于视图，可将视图环境中的 [refresh](../EnvironmentValues/refresh.zh-Hans.md) 值设置为使用指定 `action` 作为其处理程序的 [RefreshAction](../RefreshAction.zh-Hans.md) 实例。检测到该实例存在的视图可以更改其外观，以便用户执行处理程序。

例如，在 iOS 和 iPadOS 上将此修饰符应用于 [List](../List.zh-Hans.md) 时，列表将启用标准的下拉刷新手势，以刷新列表内容。当用户向下拖动可滚动区域的顶部时，视图将显示进度指示器并执行指定的处理程序。该指示器在刷新期间保持可见，刷新过程异步运行：

```swift
List(mailbox.conversations) { conversation in
    ConversationCell(conversation)
}
.refreshable {
    await mailbox.fetch()
}
```

您也可以为自己的视图添加刷新功能。有关如何操作的信息，请参阅 [RefreshAction](../RefreshAction.zh-Hans.md)。

## 刷新列表内容

- **refresh**：存储在视图环境中的刷新操作。

- **RefreshAction**：启动刷新操作的操作。


---
source: https://developer.apple.com/documentation/SwiftUI/View/refreshable(action:)
crawled: 2025-11-30T21:24:53Z
---

# refreshable(action:)

**Instance Method**

Marks this view as refreshable.

## Declaration

```swift
nonisolated func refreshable(action: @escaping () async -> Void) -> some View

```

## Parameters

- **action**: An asynchronous handler that SwiftUI executes when the user requests a refresh. Use this handler to initiate an update of model data displayed in the modified view. Use `await` in front of any asynchronous calls inside the handler.

## Return Value

A view with a new refresh action in its environment.

## Discussion

Apply this modifier to a view to set the [refresh](../EnvironmentValues/refresh.zh-Hans.md) value in the view’s environment to a [RefreshAction](../RefreshAction.zh-Hans.md) instance that uses the specified `action` as its handler. Views that detect the presence of the instance can change their appearance to provide a way for the user to execute the handler.

For example, when you apply this modifier on iOS and iPadOS to a [List](../List.zh-Hans.md), the list enables a standard pull-to-refresh gesture that refreshes the list contents. When the user drags the top of the scrollable area downward, the view reveals a progress indicator and executes the specified handler. The indicator remains visible for the duration of the refresh, which runs asynchronously:

```swift
List(mailbox.conversations) { conversation in
    ConversationCell(conversation)
}
.refreshable {
    await mailbox.fetch()
}
```

You can add refresh capability to your own views as well. For information on how to do that, see [RefreshAction](../RefreshAction.zh-Hans.md).

## Refreshing a list’s content

- **refresh**: A refresh action stored in a view’s environment.
- **RefreshAction**: An action that initiates a refresh operation.

