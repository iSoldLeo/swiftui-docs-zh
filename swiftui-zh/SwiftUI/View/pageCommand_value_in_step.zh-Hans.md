--- 来源：https://developer.apple.com/documentation/SwiftUI/View/pageCommand(value:in:step:)

抓取时间：2025-12-02T17:42:14Z

---

# pageCommand(value:in:step:)

**实例方法**

响应 Page Up 或 Page Down 命令，使值在指定范围内逐级移动。

## 声明

```swift
nonisolated func pageCommand<V>(value: Binding<V>, in bounds: ClosedRange<V>, step: V = 1) -> some View where V : BinaryInteger

```

## 参数

- **value**：用户向上或向下翻页时要修改的值。

- **bounds**：指定值的上下限的闭范围。

- **step**：`value` 的增量或减量。默认为 1。

## 说明

使用此命令，通过绑定值、范围和步长，可以逐步浏览与视图关联的数据模型的各个部分。如果再执行一步会导致值超出范围，则值保持不变。

在 tvOS 上，用户可以通过按下已连接遥控器上的专用按钮来触发“pageUp”和“pageDown”命令。例如，您可以让用户使用频道按钮翻阅电视节目指南：

```swift
struct GuideView: View {
    @State private var pageOffset: Int = 0

    var body: some View {
        GuideContent(at: pageOffset)
            .pageCommand(
                value: $pageOffset,
                in: 0...9,
                step: 1)
    }
}
```

## 响应命令

- **onMoveCommand(perform:)**：添加一个操作，用于响应移动命令，例如当用户按下 Mac 键盘上的方向键，或在控制 Apple TV 时轻点 Siri Remote 的边缘。

- **onDeleteCommand(perform:)**：添加一个操作，用于响应系统的删除命令，或在视图获得焦点时按下 ⌫（退格键）或 ⌦（向前删除键）。

- **onExitCommand(perform:)**：设置一个操作，用于响应在视图获得焦点时接收到退出命令。

- **onPlayPauseCommand(perform:)**：添加一个操作，用于响应系统的播放/暂停命令。

- **onCommand(_:perform:)**：添加一个操作，用于响应给定的选择器。

- **MoveCommandDirection**：指定方向键的移动方向。


---
source: https://developer.apple.com/documentation/SwiftUI/View/pageCommand(value:in:step:)
crawled: 2025-12-02T17:42:14Z
---

# pageCommand(value:in:step:)

**Instance Method**

Steps a value through a range in response to page up or page down commands.

## Declaration

```swift
nonisolated func pageCommand<V>(value: Binding<V>, in bounds: ClosedRange<V>, step: V = 1) -> some View where V : BinaryInteger

```

## Parameters

- **value**: A [Binding](../Binding.zh-Hans.md) to the value to modify when the user pages up or down.
- **bounds**: A closed range that specifies the upper and lower bounds of `value`.
- **step**: The amount by which to increment or decrement `value`. Defaults to 1.

## Discussion

Use this command to step through sections of a data model associated with a view by providing a binding to a value, a range, and step. If taking another step would cause the value to exceed the bounds, then the value remains unchanged.

On tvOS, the user triggers ‘pageUp’ and ‘pageDown’ commands by pressing a dedicated button on a connected remote. For example, you can let a user page through a TV programming guide using the channel buttons:

```swift
struct GuideView: View {
    @State private var pageOffset: Int = 0

    var body: some View {
        GuideContent(at: pageOffset)
            .pageCommand(
                value: $pageOffset,
                in: 0...9,
                step: 1)
    }
}
```

## Responding to commands

- **onMoveCommand(perform:)**: Adds an action to perform in response to a move command, like when the user presses an arrow key on a Mac keyboard, or taps the edge of the Siri Remote when controlling an Apple TV.
- **onDeleteCommand(perform:)**: Adds an action to perform in response to the system’s Delete command, or pressing either the ⌫ (backspace) or ⌦ (forward delete) keys while the view has focus.
- **onExitCommand(perform:)**: Sets up an action that triggers in response to receiving the exit command while the view has focus.
- **onPlayPauseCommand(perform:)**: Adds an action to perform in response to the system’s Play/Pause command.
- **onCommand(_:perform:)**: Adds an action to perform in response to the given selector.
- **MoveCommandDirection**: Specifies the direction of an arrow key movement.

