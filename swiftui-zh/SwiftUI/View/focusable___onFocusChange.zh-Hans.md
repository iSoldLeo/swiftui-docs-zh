--- 来源：https://developer.apple.com/documentation/SwiftUI/View/focusable(_:onFocusChange:)

抓取时间：2025-12-01T10:25:00Z

---

# focusable(_:onFocusChange:)

**实例方法**

指定视图是否可聚焦，如果可聚焦，则添加一个视图获得焦点时要执行的操作。

## 声明

```swift
nonisolated func focusable(_ isFocusable: Bool = true, onFocusChange: @escaping (Bool) -> Void = { _ in }) -> some View

```

## 参数

- **isFocusable**：一个布尔值，指示此视图是否可聚焦。

- **onFocusChange**：一个闭包，当此视图获得或失去焦点时调用。当视图获得焦点时，`onFocusChange` 的布尔参数为 `true`；否则，则为 `false`。

## 返回值

一个用于设置视图是否可聚焦的视图，并在视图获得或失去焦点时触发 `onFocusChange`。

## 输入和事件修饰符

- **onChange(of:perform:)**：添加一个在给定值更改时要执行的操作。

- **onTapGesture(count:coordinateSpace:perform:)**：添加一个在此视图识别到点击手势时要执行的操作，并为该操作提供交互位置。

- **onLongPressGesture(minimumDuration:maximumDistance:pressing:perform:)**：添加一个在此视图识别到长按手势时要执行的操作。

- **onLongPressGesture(minimumDuration:pressing:perform:)**：添加一个在此视图识别到长按手势时要执行的操作。

- **onPasteCommand(of:perform:)**：添加一个响应系统“粘贴”命令的操作。

- **onPasteCommand(of:validator:perform:)**：添加一个响应系统“粘贴”命令的操作，该操作会验证粘贴的内容。

- **onDrop(of:delegate:)**：定义一个拖放操作的目标位置，该位置的大小和位置与当前视图相同，其行为由指定的委托控制。

- **onDrop(of:isTargeted:perform:)**：定义一个拖放操作的目标位置，该位置使用您指定的闭包处理拖放的内容。

- **onContinuousHover(coordinateSpace:perform:)**：添加一个操作，当指针进入、移动到视图边界内以及离开视图边界时执行。


---
source: https://developer.apple.com/documentation/SwiftUI/View/focusable(_:onFocusChange:)
crawled: 2025-12-01T10:25:00Z
---

# focusable(_:onFocusChange:)

**Instance Method**

Specifies if the view is focusable and, if so, adds an action to perform when the view comes into focus.

## Declaration

```swift
nonisolated func focusable(_ isFocusable: Bool = true, onFocusChange: @escaping (Bool) -> Void = { _ in }) -> some View

```

## Parameters

- **isFocusable**: A Boolean value that indicates whether this view is focusable.
- **onFocusChange**: A closure that’s called whenever this view either gains or loses focus. The Boolean parameter to `onFocusChange` is `true` when the view is in focus; otherwise, it’s `false`.

## Return Value

A view that sets whether a view is focusable, and triggers `onFocusChange` when the view gains or loses focus.

## Input and events modifiers

- **onChange(of:perform:)**: Adds an action to perform when the given value changes.
- **onTapGesture(count:coordinateSpace:perform:)**: Adds an action to perform when this view recognizes a tap gesture, and provides the action with the location of the interaction.
- **onLongPressGesture(minimumDuration:maximumDistance:pressing:perform:)**: Adds an action to perform when this view recognizes a long press gesture.
- **onLongPressGesture(minimumDuration:pressing:perform:)**: Adds an action to perform when this view recognizes a long press gesture.
- **onPasteCommand(of:perform:)**: Adds an action to perform in response to the system’s Paste command.
- **onPasteCommand(of:validator:perform:)**: Adds an action to perform in response to the system’s Paste command with items that you validate.
- **onDrop(of:delegate:)**: Defines the destination for a drag and drop operation with the same size and position as this view, with behavior controlled by the given delegate.
- **onDrop(of:isTargeted:perform:)**: Defines the destination of a drag-and-drop operation that handles the dropped content with a closure that you specify.
- **onContinuousHover(coordinateSpace:perform:)**: Adds an action to perform when the pointer enters, moves within, and exits the view’s bounds.

