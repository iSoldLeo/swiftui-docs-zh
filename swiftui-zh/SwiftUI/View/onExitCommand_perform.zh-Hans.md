--- 来源：https://developer.apple.com/documentation/SwiftUI/View/onExitCommand(perform:)

抓取时间：2025-12-02T17:42:15Z

---

# onExitCommand(perform:)

**实例方法**

设置一个操作，该操作会在视图获得焦点时，因接收到退出命令而触发。

## 声明

```swift
nonisolated func onExitCommand(perform action: (() -> Void)?) -> some View

```

## 说明

用户可以通过按下 tvOS 上的菜单按钮或 macOS 上的 Esc 键来发出退出命令。

## 响应命令

- **onMoveCommand(perform:)**：添加一个操作，用于响应移动命令，例如当用户按下 Mac 键盘上的方向键，或在控制 Apple TV 时轻点 Siri Remote 的边缘。

- **onDeleteCommand(perform:)**：添加一个操作，用于响应系统的删除命令，或在视图获得焦点时按下 ⌫（退格键）或 ⌦（向前删除键）。

- **pageCommand(value:in:step:)**：响应 Page Up 或 Page Down 命令，使值在指定范围内逐级移动。

- **onPlayPauseCommand(perform:)**：添加一个操作，用于响应系统的播放/暂停命令。

- **onCommand(_:perform:)**：添加一个操作，用于响应给定的选择器。

- **MoveCommandDirection**：指定箭头键的移动方向。


---
source: https://developer.apple.com/documentation/SwiftUI/View/onExitCommand(perform:)
crawled: 2025-12-02T17:42:15Z
---

# onExitCommand(perform:)

**Instance Method**

Sets up an action that triggers in response to receiving the exit command while the view has focus.

## Declaration

```swift
nonisolated func onExitCommand(perform action: (() -> Void)?) -> some View

```

## Discussion

The user generates an exit command by pressing the Menu button on tvOS, or the escape key on macOS.

## Responding to commands

- **onMoveCommand(perform:)**: Adds an action to perform in response to a move command, like when the user presses an arrow key on a Mac keyboard, or taps the edge of the Siri Remote when controlling an Apple TV.
- **onDeleteCommand(perform:)**: Adds an action to perform in response to the system’s Delete command, or pressing either the ⌫ (backspace) or ⌦ (forward delete) keys while the view has focus.
- **pageCommand(value:in:step:)**: Steps a value through a range in response to page up or page down commands.
- **onPlayPauseCommand(perform:)**: Adds an action to perform in response to the system’s Play/Pause command.
- **onCommand(_:perform:)**: Adds an action to perform in response to the given selector.
- **MoveCommandDirection**: Specifies the direction of an arrow key movement.

