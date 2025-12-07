--- 来源：https://developer.apple.com/documentation/swiftui/movecommanddirection

抓取时间：2025-12-04T13:38:31Z

---

# MoveCommandDirection

**Enumeration**

指定方向键的移动方向。

## 声明

```swift
enum MoveCommandDirection
```

## 获取移动命令方向

- **MoveCommandDirection.up**

- **MoveCommandDirection.down**

- **MoveCommandDirection.left**

- **MoveCommandDirection.right**

## 响应命令

- **onMoveCommand(perform:)**：添加一个响应移动命令的操作，例如用户按下 Mac 键盘上的方向键，或在控制 Apple TV 时轻点 Siri Remote 的边缘。

- **onDeleteCommand(perform:)**：添加一个响应系统删除命令的操作，或在视图获得焦点时按下 ⌫（退格键）或 ⌦（向前删除键）。

- **pageCommand(value:in:step:)**：响应 Page Up 或 Page Down 命令，使值在指定范围内逐级递增。

- **onExitCommand(perform:)**：设置一个操作，该操作在视图获得焦点时，因接收到退出命令而触发。

- **onPlayPauseCommand(perform:)**：添加一个操作，以响应系统的播放/暂停命令。

- **onCommand(_:perform:)**：添加一个操作，以响应给定的选择器。

## 符合以下规范

- Copyable

- Equatable

- Hashable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/swiftui/movecommanddirection
crawled: 2025-12-04T13:38:31Z
---

# MoveCommandDirection

**Enumeration**

Specifies the direction of an arrow key movement.

## Declaration

```swift
enum MoveCommandDirection
```

## Getting move command directions

- **MoveCommandDirection.up**
- **MoveCommandDirection.down**
- **MoveCommandDirection.left**
- **MoveCommandDirection.right**

## Responding to commands

- **onMoveCommand(perform:)**: Adds an action to perform in response to a move command, like when the user presses an arrow key on a Mac keyboard, or taps the edge of the Siri Remote when controlling an Apple TV.
- **onDeleteCommand(perform:)**: Adds an action to perform in response to the system’s Delete command, or pressing either the ⌫ (backspace) or ⌦ (forward delete) keys while the view has focus.
- **pageCommand(value:in:step:)**: Steps a value through a range in response to page up or page down commands.
- **onExitCommand(perform:)**: Sets up an action that triggers in response to receiving the exit command while the view has focus.
- **onPlayPauseCommand(perform:)**: Adds an action to perform in response to the system’s Play/Pause command.
- **onCommand(_:perform:)**: Adds an action to perform in response to the given selector.

## Conforms To

- Copyable
- Equatable
- Hashable
- Sendable
- SendableMetatype

