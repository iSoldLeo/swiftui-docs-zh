--- 来源：https://developer.apple.com/documentation/SwiftUI/View/onPlayPauseCommand(perform:)

抓取时间：2025-12-02T17:42:15Z

---

# onPlayPauseCommand(perform:)

**实例方法**

添加一个响应系统播放/暂停命令的操作。

## 声明

```swift
nonisolated func onPlayPauseCommand(perform action: (() -> Void)?) -> some View

```

## 响应命令

- **onMoveCommand(perform:)**：添加一个响应移动命令的操作，例如用户按下 Mac 键盘上的方向键，或在控制 Apple TV 时轻点 Siri Remote 的边缘。

- **onDeleteCommand(perform:)**：添加一个操作，用于响应系统的删除命令，或在视图获得焦点时按下 ⌫（退格键）或 ⌦（向前删除键）。

- **pageCommand(value:in:step:)**：响应 Page Up 或 Page Down 命令，使值在指定范围内逐级移动。

- **onExitCommand(perform:)**：设置一个操作，用于在视图获得焦点时，响应收到退出命令而触发。

- **onCommand(_:perform:)**：添加一个操作，用于响应给定的选择器。

- **MoveCommandDirection**：指定箭头键的移动方向。


---
source: https://developer.apple.com/documentation/SwiftUI/View/onPlayPauseCommand(perform:)
crawled: 2025-12-02T17:42:15Z
---

# onPlayPauseCommand(perform:)

**Instance Method**

Adds an action to perform in response to the system’s Play/Pause command.

## Declaration

```swift
nonisolated func onPlayPauseCommand(perform action: (() -> Void)?) -> some View

```

## Responding to commands

- **onMoveCommand(perform:)**: Adds an action to perform in response to a move command, like when the user presses an arrow key on a Mac keyboard, or taps the edge of the Siri Remote when controlling an Apple TV.
- **onDeleteCommand(perform:)**: Adds an action to perform in response to the system’s Delete command, or pressing either the ⌫ (backspace) or ⌦ (forward delete) keys while the view has focus.
- **pageCommand(value:in:step:)**: Steps a value through a range in response to page up or page down commands.
- **onExitCommand(perform:)**: Sets up an action that triggers in response to receiving the exit command while the view has focus.
- **onCommand(_:perform:)**: Adds an action to perform in response to the given selector.
- **MoveCommandDirection**: Specifies the direction of an arrow key movement.

