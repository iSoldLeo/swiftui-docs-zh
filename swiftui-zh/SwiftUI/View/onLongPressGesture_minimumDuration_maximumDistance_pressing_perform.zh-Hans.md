--- 来源：https://developer.apple.com/documentation/SwiftUI/View/onLongPressGesture(minimumDuration:maximumDistance:pressing:perform:)

抓取时间：2025-12-01T10:24:56Z

---

# onLongPressGesture(minimumDuration:maximumDistance:pressing:perform:)

**实例方法**

添加一个操作，当此视图识别到长按手势时执行。

## 声明

```swift
nonisolated func onLongPressGesture(minimumDuration: Double = 0.5, maximumDistance: CGFloat = 10, pressing: ((Bool) -> Void)? = nil, perform action: @escaping () -> Void) -> some View

```

## 输入和事件修饰符

- **onChange(of:perform:)**：添加一个操作，当给定值发生变化时执行。

- **onTapGesture(count:coordinateSpace:perform:)**：添加一个操作，当此视图识别到点击手势时执行，并为该操作提供交互位置。

- **onLongPressGesture(minimumDuration:pressing:perform:)**：添加一个操作，当此视图识别到长按手势时执行。

- **onPasteCommand(of:perform:)**：添加一个操作，响应系统的“粘贴”命令。

- **onPasteCommand(of:validator:perform:)**：添加一个操作，响应系统的“粘贴”命令，并包含您验证过的项目。

- **onDrop(of:delegate:)**：定义一个拖放操作的目标位置，该位置的大小和位置与此视图相同，其行为由指定的委托控制。

- **onDrop(of:isTargeted:perform:)**：定义一个拖放操作的目标位置，该位置使用您指定的闭包处理拖放的内容。

- **focusable(_:onFocusChange:)**：指定视图是否可聚焦，如果可聚焦，则添加一个操作，当视图获得焦点时执行。

- **onContinuousHover(coordinateSpace:perform:)**：添加指针进入、移动到视图边界内以及离开视图边界时要执行的操作。


---
source: https://developer.apple.com/documentation/SwiftUI/View/onLongPressGesture(minimumDuration:maximumDistance:pressing:perform:)
crawled: 2025-12-01T10:24:56Z
---

# onLongPressGesture(minimumDuration:maximumDistance:pressing:perform:)

**Instance Method**

Adds an action to perform when this view recognizes a long press gesture.

## Declaration

```swift
nonisolated func onLongPressGesture(minimumDuration: Double = 0.5, maximumDistance: CGFloat = 10, pressing: ((Bool) -> Void)? = nil, perform action: @escaping () -> Void) -> some View

```

## Input and events modifiers

- **onChange(of:perform:)**: Adds an action to perform when the given value changes.
- **onTapGesture(count:coordinateSpace:perform:)**: Adds an action to perform when this view recognizes a tap gesture, and provides the action with the location of the interaction.
- **onLongPressGesture(minimumDuration:pressing:perform:)**: Adds an action to perform when this view recognizes a long press gesture.
- **onPasteCommand(of:perform:)**: Adds an action to perform in response to the system’s Paste command.
- **onPasteCommand(of:validator:perform:)**: Adds an action to perform in response to the system’s Paste command with items that you validate.
- **onDrop(of:delegate:)**: Defines the destination for a drag and drop operation with the same size and position as this view, with behavior controlled by the given delegate.
- **onDrop(of:isTargeted:perform:)**: Defines the destination of a drag-and-drop operation that handles the dropped content with a closure that you specify.
- **focusable(_:onFocusChange:)**: Specifies if the view is focusable and, if so, adds an action to perform when the view comes into focus.
- **onContinuousHover(coordinateSpace:perform:)**: Adds an action to perform when the pointer enters, moves within, and exits the view’s bounds.

