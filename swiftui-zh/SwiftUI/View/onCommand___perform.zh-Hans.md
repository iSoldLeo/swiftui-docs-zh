--- 来源：https://developer.apple.com/documentation/SwiftUI/View/onCommand(_:perform:)

抓取时间：2025-12-02T17:42:16Z

---

# onCommand(_:perform:)

**实例方法**

添加一个操作以响应给定的选择器。

## 声明

```swift
nonisolated func onCommand(_ selector: Selector, perform action: (() -> Void)?) -> some View

```

## 参数

- **selector**：要注册的选择器 `action`。

- **action**：要执行的操作。如果 `action` 为 `nil`，则 `command` 保持与此视图的关联，但不会触发。

## 返回值

当 `command` 发生时，会触发 `action` 的视图。

## 说明

要触发此操作，此视图或其包含的某个视图必须处于焦点状态。对于焦点视图*更近*的其他视图上的相同命令，其优先级更高，可能会覆盖此操作。

## 响应命令

- **onMoveCommand(perform:)**：添加一个操作，用于响应移动命令，例如用户按下 Mac 键盘上的方向键，或在控制 Apple TV 时轻点 Siri Remote 的边缘。

- **onDeleteCommand(perform:)**：添加一个操作，用于响应系统的删除命令，或在视图处于焦点状态时按下 ⌫（退格键）或 ⌦（向前删除键）。

- **pageCommand(value:in:step:)**：响应 Page Up 或 Page Down 命令，使值在指定范围内逐级移动。

- **onExitCommand(perform:)**：设置一个操作，该操作在视图获得焦点时，因接收到退出命令而触发。

- **onPlayPauseCommand(perform:)**：添加一个操作，该操作在系统发出播放/暂停命令时执行。

- **MoveCommandDirection**：指定方向键的移动方向。


---
source: https://developer.apple.com/documentation/SwiftUI/View/onCommand(_:perform:)
crawled: 2025-12-02T17:42:16Z
---

# onCommand(_:perform:)

**Instance Method**

Adds an action to perform in response to the given selector.

## Declaration

```swift
nonisolated func onCommand(_ selector: Selector, perform action: (() -> Void)?) -> some View

```

## Parameters

- **selector**: The selector to register for `action`.
- **action**: The action to perform. If `action` is `nil`, `command` keeps its association with this view but doesn’t trigger.

## Return Value

A view that triggers `action` when the `command` occurs.

## Discussion

This view or one of the views it contains must be in focus in order for the action to trigger. Other actions for the same command on views *closer* to the view in focus take priority, potentially overriding this action.

## Responding to commands

- **onMoveCommand(perform:)**: Adds an action to perform in response to a move command, like when the user presses an arrow key on a Mac keyboard, or taps the edge of the Siri Remote when controlling an Apple TV.
- **onDeleteCommand(perform:)**: Adds an action to perform in response to the system’s Delete command, or pressing either the ⌫ (backspace) or ⌦ (forward delete) keys while the view has focus.
- **pageCommand(value:in:step:)**: Steps a value through a range in response to page up or page down commands.
- **onExitCommand(perform:)**: Sets up an action that triggers in response to receiving the exit command while the view has focus.
- **onPlayPauseCommand(perform:)**: Adds an action to perform in response to the system’s Play/Pause command.
- **MoveCommandDirection**: Specifies the direction of an arrow key movement.

